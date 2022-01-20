pipeline{
    agent any
    
    environment{
        PATH = "/opt/maven/bin:$PATH"
    }
    
        stages{
            stage('Git checkout'){
                steps{
                    git credentialsId: 'Git-Credentials', url: 'https://github.com/Vinayaka445/Hello-World-latest.git'
                }
            }
            stage('Maven Build'){
                steps{
                 sh "mvn clean install"
                 sh "mv target/*.war target/myapp.war"
                }
            }
            stage('Deploy to tomcat'){
                steps{
                    sshagent(['23862d44-7b59-479e-b4c9-0135f6ff77ec']) {
                     sh "scp -o StrictHostKeyChecking=no target/myapp.war ec2-user@15.206.168.236:/opt/tomcat/webapps/"
                      
                     
                     
                    }
                }
            }
        }
 }
