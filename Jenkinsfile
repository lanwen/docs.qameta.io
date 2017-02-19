node('ruby') {
    checkout scm

    env.PATH="/usr/local/rvm/rubies/ruby/bin:${env.PATH}"

    sh 'echo $PATH'

    sh 'gem install bundler'
    sh 'bundle update --path vendor'
    sh 'bundle exec jekyll build'
}