library 'jenkins-ptcs-library@0.6.1'

def project = 'ipa-log-app'

pipeline {
    agent any
 
    stage('Checkout') {
	        checkout scm
      }

          
    stage('Package') {
        def published = publishContainerToGcr(project);

        if(env.BRANCH_NAME == 'master') {
            updateImageToK8sTestEnv(published);
        }
      }
    }
}