require 'asciidoctor'
require 'asciidoctor-pdf'

MASTER_FILE = File.join __dir__, 'src', 'dossier-validation.adoc'
OUTPUT_DIR = File.join __dir__, 'build'
THEMES_DIR = File.join __dir__, 'themes'

namespace :build do
  desc 'Build a PDF version'
  task :pdf do
    Asciidoctor.convert_file MASTER_FILE,
                             safe: :unsafe,
                             backend: 'pdf',
                             to_dir: OUTPUT_DIR,
                             mkdirs: true,
                             attributes: {
                               'pdf-stylesdir' => THEMES_DIR,
                               'pdf-style' => 'my'
                             }
  end

  desc 'Build an HTML version'
  task :html do
    Asciidoctor.convert_file MASTER_FILE,
                             safe: :unsafe,
                             to_dir: OUTPUT_DIR,
                             mkdirs: true
  end
end
