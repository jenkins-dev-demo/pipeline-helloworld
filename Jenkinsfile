pipeline {
  agent any
  stages {
    stage('env') {
      steps {
        sh '''#!/usr/bin/env bash
	echo
	echo "ENV"
	'''
      }
    }

    stage('build') {
      steps {
        sh '''#!/usr/bin/env bash
          echo
          pwd
          echo
          ls -alrth
        '''
      }
    }

  }
  post {
    always {
      dir("${env.WORKSPACE}") {
        deleteDir()
      }

    }

    failure {
      mail(to: "$NOTIFY", subject: "Failed Pipeline: ${currentBuild.fullDisplayName}", body: "Something is wrong with ${env.BUILD_URL}")
    }

  }
}