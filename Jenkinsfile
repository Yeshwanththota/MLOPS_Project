pipeline{
    agent any
    environment{
        VENV_DIR = 'venv'
    }
    stages{
        stage('cloning github repo to jenkins'){
            steps{
                script{
                    echo 'Cloning the GitHub repository to Jenkins workspace'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_token', url: 'https://github.com/Yeshwanththota/MLOPS_Project1.git']])


                }
            }
        }
        stage('Setting up our Virtual Environment and Installing dependancies'){
            steps{
                script{
                    echo 'Setting up our Virtual Environment and Installing dependancies............'
                    sh '''
                    python -m venv ${VENV_DIR}
                    . ${VENV_DIR}/bin/activate
                    pip install --upgrade pip
                    pip install -e .
                    '''
                }
            }
        }
    }
}