# Add your own tasks in files placed in lib/tasks ending in .rake,
# for example lib/tasks/capistrano.rake, and they will automatically be available to Rake.

require_relative 'config/application'

if ENV['RAILS_ENV'] == 'development' || ENV['RAILS_ENV'] == 'test'
  require 'ci/reporter/rake/minitest'
end

Rails.application.load_tasks
# Replace yarn with npm
Rake::Task['yarn:install'].clear if Rake::Task.task_defined?('yarn:install')
Rake::Task['webpacker:yarn_install'].clear
Rake::Task['webpacker:check_yarn'].clear
Rake::Task.define_task('webpack:verify_install' => ['webpacker:check_npm'])
Rake::Task.define_task('webpacker:compile' => ['webpacker:npm_install'])