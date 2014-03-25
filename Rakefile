#!/usr/bin/env rake

namespace :brew do
  desc 'Setup homebrew'
  task :setup do
    `ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"`
  end

  desc 'Upgrade'
  task :upgrade do
    `brew update`
    `brew upgrade`
    `brew cleanup`
  end

  desc 'Bundle'
  task :bundle do
    `brew bundle`
  end
end

