pipeline {
    agent { label 'ruby' }
    stages {
        stage('build') {
            steps {
                withEnv(['PATH+RUBY=/usr/local/rvm/rubies/ruby/bin']) {
                    sh 'echo $PATH'
                    sh 'gem install bundler'
                    sh 'bundle install --path vendor'
                    sh 'bundle exec jekyll build'
                }
            }
        }
    }
}