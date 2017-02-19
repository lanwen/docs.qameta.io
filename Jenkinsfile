node('ruby') {
    checkout scm
    sh 'gem install bundler'
    sh 'bundle update'
    sh 'bundle exec jekyll build'
}