require "rubygems"
require "bundler"
Bundler.setup

namespace :styles do
  
  desc "Clears the stylesheets"
  task :clear do
    puts "*** Clearing the stylesheets ***"
    system "rm -Rfv public/stylesheets/*"
  end
  
  desc "Clears and compiles the stylesheets"
  task :compile => :clear do
    puts "*** Compiling the stylesheets ***"
    system "compass compile"
  end
  
end

desc "Generate a new project at dir=foo"
task :generate do
  # Generate the new 'dir' if it's not already created
  system "mkdir #{(ENV['dir'])}" unless File.exists?(ENV['dir'])
  
  # Archive the current HEAD to 'dir'
  system "git archive HEAD | (cd #{ENV['dir']} && tar -xvf -)"

  puts "\n *** A new project has been generated at: #{(ENV['dir'])} ***"
end