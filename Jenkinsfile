pipeline {
    agent any
    tools {
        maven 'maven'
        git 'Default'
    }
   
    stages{
        stage('git Repo Pull'){
            steps{
                sh 'git --version'
                sh 'whereis git'
                git 'https://github.com/anveshreddyseelam/automaticdeployment.git'
            }
        }
        stage('maven clean'){
            steps{
                sh 'mvn clean'
                sh 'mvn install'
            }
        }
    }
}
