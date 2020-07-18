desc "Publish to yout blog"
task :publish do
  system "git add ."
  message = "Site updated at #{Time.now.utc}"
  system "git commit -m #{message.inspect}"
  system "git push origin master"
end
