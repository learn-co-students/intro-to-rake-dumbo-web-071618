namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

namespace :db do
    desc 'invoke :environment task as a dependency'
    task :environment do
      require_relative './config/environment'
    end

    desc 'migrate changes to datbase'
    task :migrate => :environment do
      Student.create_table
    end

    desc 'seed the databse'
    task :seed do
      require_relative './db/seeds.rb'
    end
end
