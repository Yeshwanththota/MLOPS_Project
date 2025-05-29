pipeline{
    agent any
    stages{
        stage('cloning github repo to jenkins'){
            steps{
                script{
                    echo 'Cloning the GitHub repository to Jenkins workspace'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_token', url: 'https://github.com/Yeshwanththota/MLOPS_Project1.git']])
                    

                }
            }
        }
    }
}