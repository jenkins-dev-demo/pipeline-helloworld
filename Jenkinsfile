pipeline {
  agent any
  stages {
    stage('env') {
      steps {
<<<<<<< HEAD
      	def username = 'Jenkins'
      	sh '''#!/usr/bin/env bash
=======
        sh '''#!/usr/bin/env bash
>>>>>>> 7786658041872286b7eb3be6930f342c8b12fad8
	echo
	echo "ENV"
	echo "Hello Mr. ${username}"
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