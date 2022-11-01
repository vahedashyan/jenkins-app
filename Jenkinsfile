pipeline {
    agent any
    parameters {
        choice(name: 'Host_name', choices: ['f01', 'f02', 'f03'], description: 'Please choose environment to deploy')
    }
    stages {
        stage('Env build') {
            steps {
                script {
                    ehco "prepare to build"
                }
            }
        }
        stage('Deploy to choice') {
            steps {
                script {
                    echo "${params.environment}"
                    echo "Done!"
                }
            }
        }
    }
}