pipeline {  
        agent {
            label { 
                label "built-in"
                customWorkspace "/mnt/Container"
            }
        }
     stages {
          stage ("create apache container ") {
            steps { 
                    sh " docker run -dp 80:80 --name velocity httpd "
            }
      }
  }
}
