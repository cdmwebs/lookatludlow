desc "deploy the site via rsync"
task :deploy do
  system %Q{middleman build}
  system %Q{rsync -rczP --delete --exclude-from .exclude --rsh=ssh build/ 26webs:sites/lookatludlow.org/current/public/}
end
