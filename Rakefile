namespace :build do

  desc 'Build a PDF version'
  task :pdf do
    `asciidoctor-pdf src/dossier-validation.adoc --destination-dir build --out-file dossier-validation.pdf`
  end

  desc 'Build an HTML version'
  task :html do
    `asciidoctor src/dossier-validation.adoc --destination-dir build --out-file dossier-validation.html`
  end

end
