require_relative "./viz/build_graph"
require "twee2"

desc "Graph the walkthrough"
task :graph do
  BuildGraph.()
end

desc "Compile the walkthrough"
task :compile do
  puts "Use rake:compile_prod to compile for production!"

  filename = "compiled.html"
  binary_name = ENV["BINARY_NAME"] || "exercism"
  walkthrough_assets_path = ENV["WALKTHROUGH_ASSETS_PATH"] || "#{Dir.pwd}/contents/assets"

  Twee2.build("main.tw2", filename)

  contents = File.read(filename).gsub("BINARY_NAME", binary_name)
  contents = contents.gsub("WALKTHROUGH_ASSETS_PATH", walkthrough_assets_path)

  File.open(filename, "wb") do |f|
    f.puts contents
  end
end

desc "Compile the walkthrough for production"
task :compile_prod do
  filename = "compiled_prod.html"
  binary_name = ENV["BINARY_NAME"] || "exercism"
  walkthrough_assets_path = "https://raw.githubusercontent.com/exercism/interactive-cli-walkthrough/master/contents/assets"
  Twee2.build("main.tw2", filename)

  contents = File.read(filename).gsub("BINARY_NAME", binary_name)
  contents = contents.gsub("WALKTHROUGH_ASSETS_PATH", walkthrough_assets_path)

  File.open(filename, "wb") do |f|
    f.puts contents
  end
end
