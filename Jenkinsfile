pipeline{
    agent any
    
    stages{
        stage('clone'){
            steps{
                git branch: 'main', url: 'https://github.com/ashwiniganigar/b6-java.git'   
            }   
        }
        stage('build'){
            steps{
                sh 'mvn clean install'  
            }   
        }
        stage('archive'){
            steps{
               archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false  
            }   
        }
        stage('surefire-reports'){
            steps{
               archiveArtifacts artifacts: 'target/surefire-reports/*.xml', followSymlinks: false 
            }   
        }
        stage('deploy'){
            steps{
               sh 'java -jar target/*.jar' 
            }   
        }
        
    }
}
