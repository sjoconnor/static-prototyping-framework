require 'zip'
require 'net/scp'
require 'highline/import'

desc "Package up the generated site into a zip file."
task :package, :filename do |t, args|
  dirname      = File.basename(Dir.getwd)
  directory    = "./_site/"
  zipfile_name = "./_#{args[:filename] || dirname}.zip"

  Zip::File.open(zipfile_name, Zip::File::CREATE) do |zipfile|
    Dir[File.join(directory, '**', '**')].each do |file|
      zipfile.add(file.sub(directory, ''), file)
    end
  end
end

desc "Deploy _site to a remote server."
task :deploy, :destination_path do |t, args|
  src         = "./_site"
  destination = args[:destination_path]
  remote      = "design-dev.sparkbase.com"
  username    = `whoami`.chomp
  password    = ask("Enter password: ") { |q| q.echo = false }

  Net::SCP.upload!(remote,
                   username,
                   src,
                   destination,
                   :recursive => true,
                   :ssh => { :password => password })
end