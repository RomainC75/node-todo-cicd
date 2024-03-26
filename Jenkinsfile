pipeline {
    agent { label 'ubuntu_container' }

    stages {

        stage ('Code') {
            steps {
                git url: 'https://github.com/ajitfawade/node-todo-cicd.git', branch: 'master'
            }
        }
        
        stage ('Build & Test') {
            steps {
                npm i
                npm run start
            }
        }
        

    }
}
