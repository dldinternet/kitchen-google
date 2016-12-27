# -*- coding: utf-8 -*-

require "bundler/gem_tasks"
require "rspec/core/rake_task"

RSpec::Core::RakeTask.new(:spec)

require "chefstyle"
require "rubocop/rake_task"
RuboCop::RakeTask.new(:style) do |task|
  task.options << "--display-cop-names"
end

require 'rubygems/package_task'
Gem::PackageTask.new(Gem::Specification.load('kitchen-google.gemspec')) do |pkg|
  pkg.need_tar = true
  pkg.need_zip = false
end

task default: [:spec, :style]
