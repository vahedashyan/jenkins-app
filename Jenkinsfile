pipeline {
    agent any
    parameters {
        choice(name: 'host_name', choices: ['f01', 'f02', 'f03'], description: 'Please choose environment to deploy');
    }
    stages {
        stage('Env build') {
            steps {
                script {
                    echo "prepare to build";
                }
            }
        }
        stage('Deploy to choice') {
            steps {
                script {
                    echo "${params.host_name}";
                    echo "Done!"
                }
            }
        }
    }
}