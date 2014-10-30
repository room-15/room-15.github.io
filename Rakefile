require 'rubygems'

desc 'Generate site from Travis CI and publish site to GitHub Pages'
task :travis do
  repo = %x(git config remote.origin.url).gsub(/^git:/, 'https:')
  deploy_branch = 'master'
  system "git remote set-url --push origin #{repo}"
  system 'git fetch -q'
  system "git config user.name '#{ENV['GIT_NAME']}'"
  system "git config user.email '#{ENV['GIT_EMAIL']}'"
  system 'git config credential.helper "store --file=.git/credentials"'
  system "git checkout #{deploy_branch}"
  
  File.open('.git/credentials', 'w') do |f|
    f.write("https://#{ENV['GH_TOKEN']}:@github.com")
  end
  
  system './build'
  system 'git add .'
  system 'git commit -am "Build"'
  system 'git push origin master'
  File.delete '.git/credentials'
end