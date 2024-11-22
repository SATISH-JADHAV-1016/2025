pipeline {  
        agent {
            label { 
                label "built-in"
                customWorkspace "/mnt/Container/"
            }
        }
     stages {
          stage ("create apache container ") {
            steps { 
                    sh " docker run -dp 80:80 --name velocity httpd "
            } 
      }
   stage ("Deploy index file ") {
            steps { 
                    sh " docker cp index.html velocity:/usr/local/apache2/htdocs "
                    sh " docker exec velocity chmod -R 777 /usr/local/apache2/htdocs/index.html" 
            }
         }
     }
