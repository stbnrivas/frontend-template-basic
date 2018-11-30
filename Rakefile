task :default => [:show]

task :show do
    puts 'build:html'
    puts 'build:scss'
    puts 'build:js'
    puts 'build:all'
    puts ''
    puts 'dev:server:json'
    puts 'dev:server:web'    
end


namespace :dev do
    namespace :server do
        task :json do
            sh 'json-server data/db.json'
        end
        task :web do
        end
    end
end



namespace :build do
    task :html do
        # https://code.google.com/archive/p/htmlcompressor/
        # java -jar htmlcompressor.jar --type html -o /to/ /from/
        sh "java -jar vendor/htmlcompressor-1.5.3.jar --type html src/*.html -o dist/"
        #   -o output folder
    end
    task :css do
        sh 'cp vendor/Font-Awesome/web-fonts-with-css/webfonts/* dist/fonts/'
        # sh 'sass src\scss\app.scss:dist\css\app.css --style watch'
        # sh 'sass src\scss\app.scss:dist\css\app.css --style nested'
        sh 'sass src\scss\app.scss:dist\css\app.css --style compact'
        # sh 'sass src\scss\app.scss:dist\css\app.css --style expanded'
        # sh 'sass src\scss\app.scss:dist\css\app.css --style compressed'
    end
    task :js do
        #sh 'webpack --config=config/webpack.dev.js'
    end
    task :all => ["html", "css", "js"] do
    end
    
    task :watch do
    end
    task :clean do
    end
end



namespace :server do
    task :dev do

    end
    task :production do

    end
end