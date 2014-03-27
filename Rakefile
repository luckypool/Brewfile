#!/usr/bin/env rake
require "open3"

BREW_INSTALL_COMMAND = <<"EOS"
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
EOS

BREW_UPGRADE_COMMANDS = [
  "brew update",
  "brew upgrade",
  "brew cleanup"
]

namespace :brew do
  desc "setup homebrew"
  task :setup do
    exec_and_puts BREW_INSTALL_COMMAND
  end

  desc "upgrade task (update, upgrade, and cleanup)"
  task :upgrade do
    BREW_UPGRADE_COMMANDS.each {|command| exec_and_puts command }
  end

  desc "bundle (packages will be installed by Brewfile)"
  task :bundle do
    exec_and_puts"brew bundle"
  end
end

EXPORT_PATH_MESSAGE = <<"EOS"

  Add following codes to your .bashrc (or .zshrc)
  -----

  export PATH="$HOME/.anyenv/bin:$PATH"
  eval "$(anyenv init -)"
  for D in `ls $HOME/.anyenv/envs`
  do
      export PATH="$HOME/.anyenv/envs/$D/shims:$PATH"
  done

  ----
  and do 'exec $SHELL -l'

EOS

ANYENV_INSTALL_COMMANDS = [
  "anyenv install plenv",
  "anyenv install rbenv",
  "anyenv install ndenv",
  "exec #{ENV['SHELL']} -l",
]

ANYENV_BUILD_COMMANDS = [
  "plenv install 5.14.4",
  # "plenv install 5.16.3",
  "plenv global 5.14.4",
  "plenv rehash",
  "plenv install-cpanm",
  "plenv rehash",

  "rbenv install 2.1.0",
  "rbenv global 2.1.0",
  "rbenv rehash",

  "ndenv install v0.10.26",
  "ndenv global v0.10.26",
  "ndenv rehash"
]

namespace :anyenv do
  desc "setup anyenv"
  task :setup do
    exec_and_puts "git clone https://github.com/riywo/anyenv ~/.anyenv"
    puts EXPORT_PATH_MESSAGE
  end

  desc "install plenv, rbenv, ndenv"
  task :install do
    ANYENV_INSTALL_COMMANDS.each {|command| exec_and_puts command }
  end

  desc "build perl, ruby, node.js"
  task :build do
    ANYENV_BUILD_COMMANDS.each {|command| exec_and_puts command }
  end
end

ERROR_MESSAGE = <<"EOS"
  ERROR!! did not success following command
    %s

EOS

def exec_and_puts(command)
  puts "=" * 30
  puts "[EXEC] #{command}"
  status = Open3.pipeline(command).first
  unless status.success?
    puts sprintf("#{ERROR_MESSAGE}", command)
    print 'Exit task? [y/N]: '
    answer = STDIN.gets.chomp.strip
    exit 1 if answer == 'y'
  end
  puts "[DONE] #{command}"
  puts "=" * 30
end
