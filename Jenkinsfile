pipeline {
     agent any
     stages {
          stage("Compile") {
               steps {
                    sh "/usr/bin/mvn compile"
               }
          }
          stage("Unit test") {
               steps {
                    sh "/usr/bin/mvn test"
               }
          }
     
    
stage("Package") {
     steps {
          sh "/usr/bin/mvn package"
     }
}
stage("Ansible deploy") {
     steps {
      sh "ansible -i my_targets app-container.yml"   
     }
}


     }
  post {
     always {
          sh "echo 'I did It'"
     }
}
}
