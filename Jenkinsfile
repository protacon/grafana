library "jenkins-ptcs-library@0.6.1"

// pod provides common utilies and tools to jenkins-ptcs-library function correctly.
// certain ptcs-library command requires containers (like docker or gcloud.)
podTemplate(label: pod.label,
  containers: pod.templates + [ // This adds all depencies for jenkins-ptcs-library methods to function correctly.
  ]
) {
    def project = 'ipa-log-app'
    
    node(pod.label) {
      stage('Checkout') {
        checkout scm
      }
      stage('Deploy') {
        def publishedImage = publishContainerToGcr(project);
      }
    }
  }
