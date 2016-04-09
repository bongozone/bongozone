task :default => :build

task :build do
  jekyll = %W(jekyll jekyll22 ).find { |j| `which #{j} 2> /dev/null`.chomp != '' }
  sh "#{jekyll} build"
end
