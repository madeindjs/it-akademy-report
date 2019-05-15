require 'asciidoctor'
require 'asciidoctor-pdf'
require 'asciidoctor-pdf'
require 'combine_pdf'

MASTER_FILE = File.join __dir__, 'src', 'dossier-validation.adoc'
OUTPUT_DIR = File.join __dir__, 'build'
ANNEXES_DIR = File.join __dir__, 'annexes'
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
     pdf = CombinePDF.load File.join(OUTPUT_DIR, 'dossier-validation.pdf')

     Dir.glob(File.join(ANNEXES_DIR, '*.pdf')).each do |f|
       pdf << CombinePDF.load(f)
     end

     pdf.save File.join(OUTPUT_DIR, 'dossier-validation-with-annexes.pdf')
  end

  desc 'Build an HTML version'
  task :html do
    Asciidoctor.convert_file MASTER_FILE,
                             safe: :unsafe,
                             to_dir: OUTPUT_DIR,
                             mkdirs: true
  end
end
