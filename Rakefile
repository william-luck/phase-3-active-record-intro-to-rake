# Common rake tasks 
# rake db:migrate.. Not really sure what this does just yet... But it did create a table
# rake db:seed, seeding database with some placeholder data.
# rake console


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
  desc 'migrate changes to your database'
  # Tells Rake that it needs to run the evironment task before it can run migrate. Creates a task dependency
  task migrate: :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end

end

desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end

task :environment do
  require_relative './config/environment'
end

