final def IS_PULL_REQUEST_BUILD = env.BRANCH_NAME.startsWith('PR-')
final def IS_MASTER_BUILD = env.BRANCH_NAME == 'master'

pipeline {
    agent {label 'slave'}
      stages {
        stage('checkout'){
            when { expression { IS_PULL_REQUEST_BUILD }}
            steps {
                sh 'echo helloworld2'
                sh 'mvn version'
            }
        }
        stage('build'){
            steps {
                sh 'mvn -v'
            }
        }
      }
}
