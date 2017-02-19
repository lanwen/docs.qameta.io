node('ruby') {

    checkout scm

    dir('_site') {
        checkout([
                $class           : 'GitSCM',
                branches         : [[name: 'gh-pages']],
                userRemoteConfigs: scm.userRemoteConfigs,
        ])
    }

    sh 'gem install bundler'
    sh 'bundle install --path vendor'
    sh 'bundle exec jekyll build'
}