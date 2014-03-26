#!/usr/bin/env rake
require "open3"

namespace :brew do
  desc 'Setup homebrew'
  task :setup do
    exec_and_puts 'ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"'
  end

  desc 'Upgrade'
  task :upgrade do
    exec_and_puts 'brew update'
    exec_and_puts 'brew upgrade'
    exec_and_puts 'brew cleanup'
  end

  desc 'Bundle'
  task :bundle do
    exec_and_puts'brew bundle'
  end
end

namespace :anyenv do
  desc 'setup anyenv'
  task :setup do
    exec_and_puts 'git clone https://github.com/riywo/anyenv ~/.anyenv'
    puts <<"EOS"

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
  end

  desc 'install perl, ruby, node.js'
  task :install do
    exec_and_puts 'anyenv install plenv'
    exec_and_puts 'anyenv install rbenv'
    exec_and_puts 'anyenv install ndenv'
    exec_and_puts "exec #{ENV['SHELL']} -l"

    exec_and_puts 'plenv install 5.14.4'
    exec_and_puts 'plenv install 5.16.3'
    exec_and_puts 'plenv global 5.14.4'
    exec_and_puts 'plenv rehash'
    exec_and_puts 'plenv install-cpanm'
    exec_and_puts 'plenv rehash'

    exec_and_puts 'rbenv install 2.1.0'
    exec_and_puts 'rbenv global 2.1.0'
    exec_and_puts 'rbenv rehash'

    exec_and_puts 'ndenv install v0.10.26'
    exec_and_puts 'ndenv global v0.10.26'
    exec_and_puts 'ndenv rehash'
  end
end

def exec_and_puts(command)
  puts "  #{command}"
  puts ""
  Open3.pipeline command
  puts ""
end
