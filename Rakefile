task :default => [:show]

task :show do
    puts 'build:html'
    puts 'build:css'
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
        sh "java -jar vendor/htmlcompressor-1.5.3.jar --type html ./*.html --output dist/"
        #   -o output folder
    end
    task :css do
        sh 'cp -r fonts dist/fonts/'
        # sh 'sass scss/app.scss:css/app.css --style watch'
        # sh 'sass scss/app.scss:css/app.css --style nested'
        sh 'sass scss/app.scss:css/app.css --style compact'
        # sh 'sass scss/app.scss:css/app.css --style expanded'
        # sh 'sass scss/app.scss:css/app.css --style compressed'
        sh 'cp -r css dist/css/'
    end
    task :js do
        sh 'webpack --config=webpack.dev.js'
        # sh 'mkdir -p dist/js'        
        sh '[ -d dist/js ] || mkdir-p dist/js'
        sh 'cp js/app-bundle.js dist/js/app-bundle.js'
    end
    task :all => ["html", "css", "js"] do
        puts "Task Ends"
    end
    
    task :watch do
    end

    task :clean do
        'sh rm -rf ./dist/*'

    end
end



namespace :server do
    task :dev do

    end
    task :production do

    end
end