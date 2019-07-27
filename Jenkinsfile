pipeline {
  agent any 
   stages {
     stage ("build") {
      steps {
         sh "ant -f build.xml -v"
            }
     stage ("postbuild") {
        always {
          archive artifacts: 'dist /* .jar' , fingerprint: true
               }
                         }
                        }
             }
            }
                 
