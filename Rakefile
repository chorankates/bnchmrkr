require 'jeweler'
require 'rake/testtask'

$LOAD_PATH << File.join([File.dirname(__FILE__), 'lib'])
$LOAD_PATH << File.dirname(__FILE__)
require 'benchmarker'

Jeweler::Tasks.new do |gem|
  gem.name        = 'benchmarker'
  gem.summary     = 'compare execution time'
  gem.description = 'given a hash of lambdas, runs and compares the amount of time each implementation takes'
  gem.email       = 'conor.code@gmail.com'
  gem.homepage    = 'http://github.com/chorankates/benchmarker'
  gem.authors     = ['Conor Horan-Kates']
  gem.licenses    =  'MIT'

end
Jeweler::RubygemsDotOrgTasks.new

namespace :test do
  Rake::TestTask.new do |t|
    t.name = 'unit'
    t.libs << 'lib'
    t.test_files = FileList['test/unit/**/test_*.rb']
    t.verbose = true
  end

end

desc 'run all tests'
task :test => ['test:unit'] do
end

desc 'run all examples'
task :examples do
  Dir.glob('examples/*.rb').each do |file|
    sh "time ruby #{file}"
    puts
  end
end