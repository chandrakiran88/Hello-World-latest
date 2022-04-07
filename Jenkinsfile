pipeline {
    agent any
        stages {
            stage('checkout'){
                steps{
                    git credentialsId: 'secretecredentialsgit', 
                    url: 'https://github.com/chandrakiran88/Hello-World-latest.git'
                }
            }
        }
    
}
