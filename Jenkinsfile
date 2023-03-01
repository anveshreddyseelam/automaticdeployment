pipeline {
    agent any
    tools {
        maven 'maven'
        git 'Default'
    }
   
    stages{
        stage('git Repo Pull'){
            steps{
                
                 git credentialsId: 'Github-login', url: 'https://github.com/anveshreddyseelam/automaticdeployment.git'
            }
        }
        stage('maven clean'){
            steps{
                sh 'mvn clean'
                sh 'mvn install'
            }
        }
        stage('tomcat1'){
            steps {
                echo 'this stage is for deploying app into tomcat'
                sh 'ansible-playbook tomcat_playbook.yaml --syntax-check'
                sh 'ansible-playbook tomcat_playbook.yaml'
            }
       }
    }
}
