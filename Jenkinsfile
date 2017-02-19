node('ruby') {

    checkout scm

    dir('_site') {
        checkout([
                $class                           : 'GitSCM',
                branches                         : [[name: 'gh-pages']],
                extensions                       : scm.extensions,
                userRemoteConfigs                : scm.userRemoteConfigs,
                doGenerateSubmoduleConfigurations: scm.doGenerateSubmoduleConfigurations
        ])
    }

    sh 'gem install bundler'
    sh 'bundle install --path vendor'
    sh 'bundle exec jekyll build'
}