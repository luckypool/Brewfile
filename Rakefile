#!/usr/bin/env rake
require "open3"

BREW_INSTALL_COMMAND = <<"EOS"
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
EOS

namespace :brew do
  desc "setup homebrew"
  task :setup do
    exec_and_puts BREW_INSTALL_COMMAND
    exec_and_puts "brew tap Homebrew/brewdler"
  end

  desc "upgrade task (update, upgrade, and cleanup)"
  task :upgrade do
    %w{update upgrade cleanup}.each do |command|
      exec_and_puts "brew #{command}"
    end
  end

  desc "brewdle (minimal packages)"
  task :brewdle do
    exec_and_puts "brew brewdle --file=Brewfiles/minimal"
  end

  desc "brewdle (recommended packages)"
  task :brewdle_all do
    exec_and_puts "brew brewdle --file=Brewfiles/all"
  end

  desc "brewdle (only android development packages)"
  task :brewdle_android do
    exec_and_puts "brew brewdle --file=Brewfiles/android-development"
  end
end

EXPORT_PATH_MESSAGE = <<"EOS"

  Add following codes to your .bash_profile (or .zshrc)
  -----

  export PATH="$HOME/.anyenv/bin:$PATH"
  eval "$(anyenv init -)"
  for D in `ls $HOME/.anyenv/envs`
  do
      export PATH="$HOME/.anyenv/envs/$D/shims:$PATH"
  done

  ----

  then, do 'exec $SHELL -l'

EOS

ANYENV_INSTALL_COMMANDS = [
  "anyenv install plenv",
  "anyenv install rbenv",
  "anyenv install ndenv"
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
    puts ""
    puts "  do 'exec $SHELL -l'"
    puts ""
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
