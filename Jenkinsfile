pipeline{
    agent any
    
    stages{
        
        stage('git scm'){
            steps{
                git 'https://github.com/lokiharsha/java-dynamic-project-wipro.git'
            }
        }
        stage('clean'){
            
            steps{
                sh 'mvn clean'
            }
        }
        stage('compile'){
            
            steps{
                sh 'mvn compile'
            }
            
        }
        stage('package'){
            
            steps{
                sh 'mvn package'
            }
            
        }
        stage('install'){
            
            steps{
                sh 'mvn install'
            }
            
        }
        stage('deploy to tomcat'){
            
            steps{
                
                deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://54.226.103.114:8080/')], contextPath: 'end-end-end-deployment', war: '**/*.war'
            }
        }
        
    }
   
    
}
