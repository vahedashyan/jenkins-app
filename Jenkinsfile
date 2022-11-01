pipeline {
    agent any;
    parameters {
        choice(name: 'host_name', choices: ['f01', 'f02', 'f03'], description: 'Please choose environment to deploy');
        gitParameter name: 'BRANCH_TAG',
                     type: 'PT_BRANCH_TAG',
                     defaultValue: 'master'
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
                checkout([$class: 'GitSCM',
                          branches: [[name: "${params.BRANCH_TAG}"]],
                          doGenerateSubmoduleConfigurations: false,
                          extensions: [],
                          gitTool: 'Default',
                          submoduleCfg: [],
                          userRemoteConfigs: [[url: 'https://github.com/vahedashyan/jenkins-app']]
                          ]);
                    sh '''bash ./print.sh'''
                    echo "${params.host_name}";
                    echo "Done!";
                }
            }
        }
    }
}