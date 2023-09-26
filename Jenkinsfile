pipeline {
      agent any
      stages {
             stage('Webhook Trigger') {
            when {
                expression { 
                    def payload = JSON.parse(env.GITHUB_PAYLOAD)
                    return payload.ref == 'refs/heads/develop' && payload.repository.full_name == 'yourusername/yourrepository'
                }
            }
            steps {
                echo 'Webhook triggered for a push to the develop branch'
                // Add your pipeline steps here
            }
        }
            stage('Init') {
                  steps {
                        echo 'Hi, this is first line'
                        echo 'We are Starting the Testing'
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Building Sample Maven Project'
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Staging Area"
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}



