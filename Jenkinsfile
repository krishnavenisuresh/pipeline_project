pipeline {
  agent any 
    stages {
        stage ("build") {
          steps {
            sh "ant -f build.xml -v"
                }
       stage ("postbuild") {
         steps {
         always {
            archive artifacts: 'dist /* .jar' , fingerprint: true
               }
              }
                           }
                         }
              }
           }
                 
