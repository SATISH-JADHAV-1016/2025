pipeline{
        agent{
           label{
               label 'built-in'
               customWorkspace '/root/DCont-2/' 
                }
              }
    stages{
      
         stage('create container'){
             steps{
                sh "rm -rf"
                 sh "docker run -dp 8000:80 --name container-2 httpd"
                  }
                                  }
     
          stage('deploy'){
             steps{
                sh "docker cp index.html container-2:/usr/local/apache2/htdocs"
                sh "docker exec container-2 chmod 755 /usr/local/apache2/htdocs/index.html"
                  }
                        }
           }
   }
