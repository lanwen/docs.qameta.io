pipeline {
    agent { label 'ruby' }
    stages {

        stage('Checkout gh-pages branch') {
            steps {
                sh 'git worktree add -B gh-pages _site origin/gh-pages'
                sh 'rm -rf _site/*'
            }
        }

        stage('Build site') {
            steps {
                withEnv(['PATH+RUBY=/usr/local/rvm/rubies/ruby/bin']) {
                    sh 'echo $PATH'
                    sh 'gem install bundler'
                    sh 'bundle install --path vendor'
                    sh 'bundle exec jekyll build'
                }
            }
        }
        stage('Publish site') {
            steps {
                dir('_site') {
                    sh 'git add --all && git commit -m "Publishing to gh-pages" && git push'
                }
            }
        }
    }
}