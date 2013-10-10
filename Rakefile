require 'bundler'
Bundler::GemHelper.install_tasks

desc "Run all specs"
task :spec do
  system("rspec spec")
end

desc "Import deck.js"
task :import_deck_js, [:path_to_deck_js] do |t, args|
  src_dir = args[:path_to_deck_js]
  tgt_dir = "templates/generate/deck.js"
  cp_r Dir[File.join(src_dir, "jquery*js")], File.join(tgt_dir, "support")
  cp_r Dir[File.join(src_dir, "modernizr*js")], File.join(tgt_dir, "support")
  cp_r File.join(src_dir, "core"), tgt_dir
  cp_r File.join(src_dir, "extensions"), tgt_dir
  cp_r File.join(src_dir, "themes"), tgt_dir
end

task :default => :spec
