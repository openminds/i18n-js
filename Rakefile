require 'rake'
require 'rake/testtask'

desc 'Default: run unit tests.'
task :default => :test

desc 'Test the i18n-js plugin.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end

begin
  require 'hanna/rdoctask'
  
  desc 'Generate documentation for the i18n-js plugin.'
  Rake::RDocTask.new(:rdoc) do |rdoc|
    rdoc.rdoc_dir = 'doc'
    rdoc.title    = 'I18n for JavaScript'
    rdoc.options << '--line-numbers' << '--inline-source'
    rdoc.rdoc_files.include('README.rdoc')
    rdoc.rdoc_files.include('lib/**/*.rb')
  end
rescue LoadError
  puts "hanna/rdoctask not available."
end

begin
  require 'jeweler'
  
  Jeweler::Tasks.new do |gemspec|
    gemspec.name = "i18n-js"
    gemspec.summary = "It's a small library (5.2KB or 1.76KB when gzipped) to provide the Rails I18n translations on the Javascript."
    gemspec.description = "It's a small library (5.2KB or 1.76KB when gzipped) to provide the Rails I18n translations on the Javascript."
    gemspec.email = "fnando.vieira@gmail.com"
    gemspec.homepage = "http://github.com/fnando/i18n-js"
    gemspec.authors = ["Nando Vieira"]
    gemspec.add_development_dependency "activesupport", ">= 2.3.4"
  end

  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install jeweler"
end