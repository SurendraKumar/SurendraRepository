# A sample Guardfile
# More info at https://github.com/guard/guard#readme

# NOTE: When using watch with a block, you must return all files that should be reloaded.
guard :rspectacle, :cli => '--format nested --color' do
  watch('spec/spec_helper.rb')                        { %w(spec/spec_helper spec) }
  watch('config/routes.rb')                           { %w(config/routes.rb spec/routing) }
  watch('app/controllers/application_controller.rb')  { 'spec/controllers' }

  watch(%r{^spec/.+_spec\.rb$})

  watch(%r{^app/(.+)\.rb$})                           { |m| ["app/#{m[1]}.rb", "spec/#{m[1]}_spec.rb"] }
  watch(%r{^lib/(.+)\.rb$})                           { |m| ["lib/#{m[1]}.rb", "spec/lib/#{m[1]}_spec.rb"] }
  watch(%r{^app/controllers/(.+)_controller\.rb$})    { |m| [
    "app/controllers/#{m[1]}_controller.rb",
    "spec/controllers/#{m[1]}_spec.rb",
    "spec/routing/#{m[1]}_routing_spec.rb",
    "spec/acceptance/#{m[1]}_spec.rb"
  ]}
end
