#!/usr/bin/env rake

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

def exec_and_puts(command)
  puts "  #{command}"
  puts ""
  puts `#{command}`
  puts ""
end
