node('ruby') {

    stage('Checkout') {
        checkout scm

        dir ('_site') {
            checkout([
                $class: 'GitSCM',
                branches: [[name: 'gh-pages']],
                extensions: scm.extensions,
                userRemoteConfigs: scm.userRemoteConfigs,
                doGenerateSubmoduleConfigurations: scm.doGenerateSubmoduleConfigurations
            ])
        }
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