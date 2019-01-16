namespace :build do

  desc 'Build a PDF version'
  task :pdf do
    `asciidoctor-pdf src/dossier-validation.adoc --destination-dir build --out-file src/dossier-validation.pdf`
  end

  desc 'Build an HTML version'
  task :html do
    lang = parse_lang(args)
    filename = out_filename lang, 'html'
    `asciidoctor src/dossier-validation.adoc --destination-dir build --out-file src/dossier-validation.html`
  end

end
