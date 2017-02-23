node('ruby') {

    checkout scm

    checkout([$class           : 'GitSCM',
              branches         : [[name: 'gh-pages']],
              extensions       : [[$class: 'RelativeTargetDirectory', relativeTargetDir: '_site']],
              submoduleCfg     : [],
              userRemoteConfigs: [
                      [credentialsId: 'qameta-ci', url: scm.getUserRemoteConfigs()[0].getUrl()]
              ]
    ])

    sh 'gem install bundler'
    sh 'bundle install --path vendor'
    sh 'bundle exec jekyll build'
}