node('ruby') {

    stage('Checkout') {
        checkout scm
    }

    stage('Dependencies') {
        sh 'gem install bundler'
        sh 'bundle install --path vendor'
    }

    stage('Build') {
        sh 'bundle exec jekyll build'
    }

    stage('Upload') {

    }
}