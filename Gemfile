
# In order to leverage Gemfile functionality, install bundler:
# gem install bundler

# Create a Gemfile for a project:
# bundle init

# Install gems according to the Gemfile definition (rerun this after any
# modifications are made to this Gemfile):
# bundle config set path 'vendor/bundle'
# bundle install

# Alternatively, if Jekyll is already installed, initialize a new Jekyll
# repository as follows:
#
# jekyll new <directory_name>
#
# This will auto-generate a Gemfile with default versions of several other
# common project files.

# Declare the Rubygems source containing the gems listed in the Gemfile.
source 'https://rubygems.org'

# Enforce minimum required Ruby version and patch level.
# NOTE: Each application may specify a Ruby patchlevel. This option was
# implemented in Bundler 1.4.0 for Ruby 2.0 or earlier.
# WARNING: Specifying the patchlevel has been meaningless since Ruby 2.1.0 was
# released as the patchlevel is now uniquely determined by a combination of
# major, minor, and teeny version numbers.
ruby '3.3.4'

# Groups exist for test, development, production...
# group :development do
#     # Jekyll
#     # A simple, blog-aware, static-site generator.
#     # Mandate the version of Jekyll to be run.  Run Jekyll as follows:
#     # bundle exec jekyll serve
#     gem 'jekyll', '~> 3.10.0'
# end
gem 'jekyll', '~> 3.10.0'

# Groups exist for test, development, production...
group :production do
    # github-pages
    # Bootstrap the GitHub Pages Jekyll environment locally.  If you want to use
    # GitHub Pages, remove the "gem 'jekyll'" above and uncomment the line
    # below.
    # To upgrade, run `bundle update github-pages`.  Up to version 232.
    # gem 'multipart-post', '~> 2.1', '>= 2.1.1'
    # gem 'sassc', '~> 2.3'
    # WARNING: The GitHub Pages plugin does not support newer versions of Jekyll
    # gem 'github-pages', '~> 232', group: :jekyll_plugins #, :platforms => :x64_mingw32
end

# If you have any plugins, put them here!
group :jekyll_plugins do
    # jekyll-commonmark-ghpages
    # A CommonMark generator for Jekyll
    gem 'jekyll-commonmark-ghpages', '~> 0.5.1'

    # jekyll-feed
    # A Jekyll plugin to generate an Atom feed of your Jekyll posts.
    gem 'jekyll-feed', '~> 0.17.0'

    # jekyll-livereload
    # The Jekyll LiveReload plugin adds additional command line options to the
    # server command to provide Livereloading capabilities.
    # NOTE: The jekyll-livereload plugin is no longer required as of Jekyll
    # 3.7.0 at which point it was built-in to Jekyll
    # gem 'jekyll-livereload', '~> 0.2.2'

    # EventMachine
    # EventMachine implements a fast, single-threaded engine for arbitrary
    # network communications.
    # NOTE: Required for live-reload functionality
    # WARNING: There is an issue on Windows in which attempting to use the
    # livereload feature will cause calls to jekyll serve to fail.  As a
    # workaround, install the EventMachine library manually under the ruby
    # platform as follows:
    # 1. Add the ruby platform to the bundle to support the ruby version of
    # EventMachine:
    # bundle lock --add-platform ruby
    # 2. Uninstall the existing x64-mingw32 build of EventMachine:
    # gem uninstall eventmachine # May require: --force
    # 3. Install the ruby build of EventMachine:
    # gem install eventmachine --platform ruby
    # gem 'eventmachine', :platforms => :ruby # Version 1.2.7

    # jekyll-seo-tag
    # A Jekyll plugin to add metadata tags for search engines and social
    # networks to better index and display your site's content.
    # NOTE: SEO => Search Engine Optimization
    gem 'jekyll-seo-tag', '~> 2.8.0'
end

# WDM - Windows Directory Manager
# Performance-booster for watching directories on Windows, this C library which
# monitors directories for changes leverages the Win32 API for enhanced
# performance.
# NOTE: [Required to?] support Jekyll's watch functionality.
gem 'wdm', '~> 0.2.0' if Gem.win_platform?

# Groups exist for test, development, production...
group :development do
    # Rouge
    # A simple, easy-to-extend, drop-in replacement for the pygments syntax
    # highlighter.
    # NOTE: Only required for development.
    gem 'rouge', '~> 3.30.0'
end

# Minima
# A beautiful minimal theme for Jekyll.  This is the default theme for new
# Jekyll sites. You may change this to anything you like.
gem 'minima', '~> 2.5.1'

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data
# gem and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
    # TZInfo
    # TZInfo provides access to time zone data and allows times to be converted
    # using time zone rules.
    gem 'tzinfo', '~> 2.0.6'

    # TZInfo::Data
    # TZInfo::Data contains data from the IANA Time Zone database packaged as
    # Ruby modules for use with TZInfo.
    gem 'tzinfo-data', '~> 1.2025', '>= 1.2025.1', :platforms => [:mingw, :mswin]
end
