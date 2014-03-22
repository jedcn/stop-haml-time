
task :default => :build

desc 'build presentation'
task :build => [:get_images, :get_code] do
  `reveal-ck generate`
end

#
# Normally I check all of my images and code in together so that the
# presentation content is bundled and tracked together.
#
# I'm using this approach (where images are downloaded via rake) as an
# example of an alternative for situations where you might not own the
# images or don't want to check them in for another reason.
#
task :get_images => [
                     'images/mc-hammer-jdlasica.jpg',
                     'images/tom-brady-high-five-fail.gif'
                    ]

task :get_code => 'code/eval-buffer.el'

file 'code/eval-buffer.el' => 'code' do
  #
  # This excellent code of Jim's that I use almost every day can be
  # found here:
  url = 'https://raw.github.com/jimweirich/emacs-setup-esk/master/eval-buffer.el'
  `wget #{url}`

  #
  # Remove chunks of file so that I only focus on certain part
  require 'reveal-ck'
  RevealCK::Changers::Slicer.remove!('eval-buffer.el', 0..10)
  RevealCK::Changers::Slicer.remove!('eval-buffer.el', 15..39)

  mv 'eval-buffer.el', 'code'
end

file 'images/mc-hammer-jdlasica.jpg' => 'images' do
  #
  # Thanks for these great shots, JD!
  #
  # Here's the official set:
  #
  # http://www.flickr.com/photos/jdlasica/sets/72157640574674874/
  #
  `wget http://farm8.staticflickr.com/7293/12338376683_7397b563da_o.jpg`
  mv '12338376683_7397b563da_o.jpg', 'images/mc-hammer-jdlasica.jpg'
end

file 'images/tom-brady-high-five-fail.gif' => 'images' do
  #
  # My friend Sean taunted me with this photo the other day. I'm
  # pretty sure he's a regular reader of
  # http://blog.zap2it.com/pop2it.
  #
  `wget http://blog.zap2it.com/pop2it/tom-brady-high-five-fail.gif`
  mv 'tom-brady-high-five-fail.gif', 'images/tom-brady-high-five-fail.gif'
end

require 'rake/clean'

#
# images/ contains jpegs and gifs used in the presentation
directory 'images'
CLOBBER.include 'images'

#
# code/ contains code snippets used in the presentation
directory 'code'
CLOBBER.include 'code'

directory 'slides'
CLOBBER.include 'slides'
