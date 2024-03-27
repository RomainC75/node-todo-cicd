pipeline {
    agent { label 'ubuntu_container' }

    tools { nodejs "node-20" }

    stages {
        stage ('Code') {
            steps {
                git url: 'https://github.com/RomainC75/node-todo-cicd.git', branch: 'master'
            }
        }

        stage ('Build & Test') {
            steps {
                sh """
                    npm i
                    npm run start
                """
            }
        }

        // stage ('Deployment') {
        //     steps {
        //         // Add deployment steps here
        //         // This could be copying files to a server, starting a Docker container, etc.
        //     }
        // }

        stage('Wait for Manual Stop') {
            steps {
                // Pause the pipeline and wait for input from the Jenkins UI
                input message: 'Deployment is complete. Please stop the pipeline manually in the Jenkins UI.'
            }
        }
    }
}
