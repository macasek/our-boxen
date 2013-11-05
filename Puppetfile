# This file manages Puppet module dependencies.
#
# It works a lot like Bundler. We provide some core modules by
# default. This ensures at least the ability to construct a basic
# environment.

# Shortcut for a module from GitHub's boxen organization
def github(name, *args)
  options ||= if args.last.is_a? Hash
    args.last
  else
    {}
  end

  if path = options.delete(:path)
    mod name, :path => path
  else
    version = args.first
    options[:repo] ||= "boxen/puppet-#{name}"
    mod name, version, :github_tarball => options[:repo]
  end
end

# Shortcut for a module under development
def dev(name, *args)
  mod name, :path => "#{ENV['HOME']}/src/boxen/puppet-#{name}"
end

# Includes many of our custom types and providers, as well as global
# config. Required.

github "boxen", "3.3.4"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "dnsmasq",    "1.0.0"
github "foreman",    "1.0.0"
github "gcc",        "2.0.1"
github "git",        "1.2.5"
github "go",         "1.0.0"
github "homebrew",   "1.5.1"
# github "hub",        "1.0.3"   # removed in favor of gh
github "inifile",    "1.0.0", :repo => "puppetlabs/puppetlabs-inifile"
github "nginx",      "1.4.2"
github "nodejs",     "3.3.0"
github "openssl",    "1.0.0"
github "phantomjs",  "2.0.2"
github "pkgconfig",  "1.0.0"
github "repository", "2.2.0"
github "ruby",       "6.7.2"
github "stdlib",     "4.1.0", :repo => "puppetlabs/puppetlabs-stdlib"
github "sudo",       "1.0.0"
github "xquartz",    "1.1.0"

# Optional/custom modules. There are tons available at
# https://github.com/boxen.

## Apps

# github "adium" # fails???
github "alfred"         # productivity app
github "ccleaner"       # os cleanup util
github "charles"        # web debugging proxy
github "chrome"
github "dropbox"
github "firefox"
github "gimp"
github "handbrake"
github "hipchat"        # group chat
github "induction"      # db gui
github "iterm2"
github "onyx"           # osx optimization tool
github "mou"            # markdown editor
github "mysql"
github "redis"
github "screenhero"     # screen sharing
github "sourcetree"     # repo viewer
github "sublime_text_2"
github "textual"        # irc client
github "tunnelblick"    # ui for openvpn

## Utils

github "foreman"
github "freetds"        # libs for connecting to some dbs
github "gh"             # github wrapper for git
github "imagemagick"
github "licecap"        # animated screen caps
github "moreutils"
github "pow"
github "openssl"
github "osxfuse"
github "osx"            # TODO: https://github.com/boxen/puppet-osx
github "screen"



