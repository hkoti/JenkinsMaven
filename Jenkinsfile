pipeline {
      agent any
      stages {
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

pipeline {
    agent any
    stages {
        stage('Check Branch') {
            steps {
                script {
                    def branchName = sh(script: 'git rev-parse --abbrev-ref HEAD', returnStdout: true).trim()
                    if (branchName == 'develop') {
                        echo "Building on Develop branch"
                        // Add your build steps for the develop branch here
                    } else {
                        echo "Not on Develop branch. Skipping build."
                    }
                }
            }
        }
    }
}

