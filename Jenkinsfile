node('ruby') {
    checkout scm

    sh 'echo $PATH'

    sh 'gem install bundler'
    sh 'bundle update'
    sh 'bundle exec jekyll build'
}