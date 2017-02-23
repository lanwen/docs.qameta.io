node('ruby') {

    checkout scm

    checkout([$class           : 'GitSCM',
              branches         : [[name: 'gh-pages']],
              extensions       : [[$class: 'RelativeTargetDirectory', relativeTargetDir: '_site']],
              userRemoteConfigs: scm.userRemoteConfigs
    ])

    sh 'echo $PATH'
    sh 'gem install bundler'
    sh 'bundle install --path vendor'
    sh 'bundle exec jekyll build'
}