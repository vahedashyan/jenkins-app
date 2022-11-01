pipeline{
    agent any
    parameters {
    choice(name: 'Host_name', choices: ['f01', 'f02', 'f03'], description: 'Please choose environment to deploy')
    }
    stages {
        stage('Env build'){
           script{
                ehco  "prepare to build"
           }
        }
        stage('Deploy to choice'){
            script{
                echo "${params.environment}"
                echo "Done!"
            }
        }
    }
}