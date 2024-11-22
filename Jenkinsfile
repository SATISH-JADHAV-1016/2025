pipeline{
        agent{
           label{
               label 'built-in'
               customWorkspace '/root/DCont-1/' 
                }
              }
    stages{
      
         stage('create container'){
             steps{
                sh "rm -rf"
                 sh "docker run -dp 80:80 --name container-1 httpd"
                  }
                                  }
     
          stage('deploy'){
             steps{
                sh "docker cp index.html container-1:/usr/local/apache2/htdocs"
                sh "docker exec container-1 chmod 755 /usr/local/apache2/htdocs/index.html"
                  }
                        }
           }
   }
