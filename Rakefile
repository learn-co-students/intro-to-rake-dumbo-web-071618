# Let's namespace both hello and hola under the greeting heading:
namespace :greeting do
  desc 'outputs "hello" to the terminal'
  task :hello do
    puts "hello from Rake!"
  end
  # Let's say we create another greeting-type Rake task, hola:
  desc 'outputs "hola" to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end
# We'll namespace this task under the db heading. This namespace will contain
# a few common database-related tasks.
namespace :db do
  # Since our Student.create_table code would require access to the
  # config/environment.rb file (which is where the student class and database
  # are loaded), we need to give our task access to this file.
  task :environment do
    require_relative './config/environment'
  end # rake db:environment
  # We'll call this task migrate, because it is a convention to say we are
  # "migrating" our database by applying SQL statements that alter that
  # database.
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end
  # Now, if we run rake db:seed in our terminal (provided we have already run
  # rake db:migrate to create the database table), we will insert five records
  # into the database.
  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end
  # We'll define a task that starts up the Pry console.
    # Where is this supposed to go? #:-s
  desc 'drop into the Pry console'
  task :console => :environment do
    Pry.start
  end
end
