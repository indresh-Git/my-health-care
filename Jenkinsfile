pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/indresh-Git/my-health-care/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with indrsh'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with indresh'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with inresh'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with indresh'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg1 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8082:8082 --name c001 myimg'
            }
        }   
    }
}
