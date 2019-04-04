desc "Build the JSON files"
task :build do
  sh "bundle exec blog-generator.rb generate content"
end

desc "Build the JSON files with the drafts included"
task 'build:drafts' do
  sh "bundle exec blog-generator.rb generate content --include-drafts"
end

task default: :build
