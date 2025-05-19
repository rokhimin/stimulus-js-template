task :info do
  puts "Stimulus.js Template"
end

task :app do
  sh "bundle exec jekyll s"
end

task :css do
  sh "npx @tailwindcss/cli -i ./assets/css/input.css -o ./assets/css/output.css --watch"
end

task :test do
  sh "bundle exec rspec"
end

task :c do
  commit_msg = ENV["msg"] || ARGV[1] || "commit"
  changed = `git status --porcelain`.strip

  if changed.empty?
    puts "No changes to commit."
  else
    sh "git add ."
    sh "git commit -m \"#{commit_msg}\""
    sh "git push -u origin main"
  end
end



task default: :info