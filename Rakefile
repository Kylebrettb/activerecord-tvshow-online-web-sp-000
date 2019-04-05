require_relative 'config/environment.rb'
require 'sinatra/activerecord/rake'

namespace :db do

  task :console do
    Pry.start
  end

  desc "Migrate the db"
  task :migrate do
    connection_details = YAML::load(File.open('config/database.yml'))
    ActiveRecord::Base.establish_connection(connection_details)
    ActiveRecord::Migration.migrate("db/migrate/")
    ActiveRecord::Migrator.migrate("db/migrate/")
  end

  desc "drop and recreate the db"