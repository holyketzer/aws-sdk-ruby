source 'https://rubygems.org'

gem 'rake', require: false
gem 'jmespath'

group :test do

  gem 'rspec'
  gem 'cucumber'

  if RUBY_VERSION == '1.9.3'
    # webmock depends on addressable, but the latest version of addressable
    # has a dependency on ~> 2.0 of public_suffix which is not compatible
    # with Ruby 1.9.3
    gem 'addressable', '2.4.0'
    # webmock dropped support for Ruby 1.9.3 after version 2.2.0
    gem 'webmock', '2.2.0'
    # oj drop support for Ruby under 2.0 since 3.3.5
    gem 'oj', '<= 3.3.4'
  else
    gem 'addressable'
    gem 'webmock'
  end
  gem 'json-schema'
  gem 'multipart-post'

  # faster xml libraries
  gem 'libxml-ruby' unless ENV['PURE_RUBY']
  gem 'nokogiri', '1.6.8.1' unless ENV['PURE_RUBY']
  gem 'oga'

  # faster json libraries
  if !ENV['PURE_RUBY']
    gem 'json', '1.8.3' if RUBY_VERSION == '1.9.3'
    if ENV['OLD_OJ']
      gem 'oj', '1.3.0'
    else
      gem 'oj' unless RUBY_VERSION == '1.9.3'
    end

    # Ox after 2.4.12 has a change in default behavior. Test both.
    if ENV['OLD_OX']
      gem 'ox', '2.4.12'
    else
      gem 'ox'
    end
  end

end

group :build do
  gem 'kramdown' # using this to fix poorly formatted HTML in API docs
  gem 'mustache', '0.99.8' # pinned to support Ruby 1.9.3
end

group :docs do
  gem 'yard', '0.9.5'
  gem 'yard-sitemap', '~> 1.0'
  gem 'rdiscount'
end

group :repl do
  gem 'pry'
end
