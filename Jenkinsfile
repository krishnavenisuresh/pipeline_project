pipeline {
  agent any
  stages {
   stage('unit Tests') {
      steps {
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
             }
                        }
   stage("build"){
   steps   {
   sh 'ant -f build.xml -v'
           }
          }
stage('deployment'){
 steps {
    sh "cp dist/rectangle_${env.BUILD_NUMBER}.jar /var/www/html/rectangles/all/"

}
}
stage('running on centos'){
steps {
sh "wget http://192.168.122.1/rectangles/all/rectangle_${env.BUILD_NUMBER}.jar"
sh "java -jar rectangle_${env.BUILD_NUMBER}.jar 5 6"
      }
                          }
}
post {
 always {
  archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
        }
     }
}
