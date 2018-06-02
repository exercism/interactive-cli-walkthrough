require_relative "./viz/build_graph"
require "twee2"

desc "Graph the walkthrough"
task :graph do
  BuildGraph.()
end

desc "Compile the walkthrough"
task :compile do
  filename = "compiled.html"
  binary_name = ENV["BINARY_NAME"] || "exercism"
  release_url = ENV["RELEASE_URL"] || "https://github.com/exercism/cli/releases/latest"

  Twee2.build("main.tw2", filename, format: "Snowman")
  contents = File.read(filename).gsub("BINARY_NAME", binary_name).gsub("RELEASE_URL", release_url)
  File.open(filename, "wb") do |f|
    f.puts contents
  end
end
