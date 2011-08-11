# A sample Guardfile
# More info at https://github.com/guard/guard#readme

  #guard 'bundler' do
  #  watch('Gemfile')
  #end
	
  guard 'livereload' do
    watch(%r{^app/.+\.(erb|haml)$})
    watch(%r{^app/helpers/.+\.rb$})
    watch(%r{^/public/.+\.(css|js|html)$})
    watch(%r{^config/locales/.+\.ym$})
    watch(%r{^src/(.*)\.s[ac]ss})
    watch(%r{^sass/(.*)})
  end
	
  guard 'spork',:rspec_env => { 'RAILS_ENV' => 'test' }, :bundler => false do
    watch('config/application.rb')
    watch('config/environment.rb')
    watch(%r{^config/environments/.*\.rb$})
    watch(%r{^config/initializers/.*\.rb$})
    watch('spec/spec_helper.rb')
  end
	
  #guard 'cucumber', :cli => '--drb --format pretty --no-profile'do
  # watch(%r{features/.+\.feature})
  #  watch(%r{features/support/.+})                      { 'features' }
  #  watch(%r{features/step_definitions/(.+)_steps\.rb}) { |m| Dir[File.join("**/#{m[1]}.feature")][0] || 'features' }
  #end
  
  #--fail-fast
  guard 'rspec', :version => 2, :bundler => false, :cli => "--color --format Fuubar --drb" do
    watch(%r{^spec/(.*)_spec\.rb})
    watch(%r{^app/(.*)\.rb})                           { |m| "spec/#{m[1]}_spec.rb" }
    watch(%r{^lib/(.*)\.rb})                           { |m| "spec/lib/#{m[1]}_spec.rb" }
    watch('config/routes.rb')                          { "spec/routing" }
    watch('app/controllers/application_controller.rb') { "spec/controllers" }
    watch('spec/support/controller_spec_helpers.rb')   { "spec/controllers" }
    watch('spec/factories.rb')                         { "spec/models" }
    #watch(%r{^spec/acceptance/(.*)_spec\.rb})
    #watch(%r{spec/support/.+})    
    watch('spec/spec_helper.rb')                       { "spec" }
  end
