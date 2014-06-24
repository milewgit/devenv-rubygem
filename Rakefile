require "rake/testtask"
require "pathname"
require_relative "lib/mygem/version"


task :default => [ :test ]
task :install => [ :build ]


desc "Run test, build, and install tasks"
task :all => [ :test, :build, :install ]


Rake::TestTask.new :test do |t|
  t.test_files = FileList["test/**/*_test.rb", "req/**/*_test.rb"]
  t.warning = true
end


desc "Build gem"
task :build do
  system "gem build mygem.gemspec"
end


desc "Install gem locally (does an uninstall first)"
task :install do
  system "gem uninstall -x mygem"
  system "gem install mygem-#{MyGem::Version}.gem"
end
