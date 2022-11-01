pipeline {
    agent any
    parameters {
        choice(name: 'host_name', choices: ['f01', 'f02', 'f03'], description: 'Please choose environment to deploy');
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'master', name: 'BRANCH', type: 'PT_BRANCH';
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
                    git branch: "${params.BRANCH}", url: 'https://github.com/vahedashyan/jenkins-app';
                    sh '''python main.py'''
                    echo "${params.host_name}";
                    echo "Done!";
                }
            }
        }
    }
}