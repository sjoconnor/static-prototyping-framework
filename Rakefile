require 'zip'

desc "Package up the generated site into a zip file."
task :package do
  directory    = "./_site/"
  zipfile_name = './prototype.zip'

  Zip::File.open(zipfile_name, Zip::File::CREATE) do |zipfile|
    Dir[File.join(directory, '**', '**')].each do |file|
      zipfile.add(file.sub(directory, ''), file)
    end
  end
end