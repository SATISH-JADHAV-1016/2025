pipeline{
        agent{
           label{
               label 'built-in'
               customWorkspace "/root/Container-3/"
                }
              }
    stages{
       
         stage('create container'){
             steps{
                sh "rm -rf"
                 sh "docker run -dp 8001:80 --name container-3 httpd"
                  }
                                  }
     
          stage('deploy'){
             steps{
                sh "docker cp index.html container-3:/usr/local/apache2/htdocs"
                sh "docker exec container-3 chmod 755 /usr/local/apache2/htdocs/index.html"
                  }
                        }
           }
   }
