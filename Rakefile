ssh_user = "cdmwebs@26webs.com"
remote_root = "~/sites/lookatludlow.org/current/public/"

desc "Runs preview"
task :preview do
  system "staticmatic preview ."
end

desc "Builds the site"
task :build => 'styles:clear' do
  puts "*** Building the site ***"
  system "staticmatic build ."
end

desc "Clears and generates new styles, builds and deploys"
task :deploy => :build do
  puts "*** Deploying the site ***"
  system("rsync -avz --delete site/ #{ssh_user}:#{remote_root}")
end

namespace :styles do
  desc "Clears the styles"
  task :clear do
    puts "*** Clearing styles ***"
    system "rm -Rfv site/stylesheets/*.css"
  end
  
  desc "Generates new styles"
  task :generate => :clear do
    puts "*** Generating styles ***"
    system "compass"
  end
  
end