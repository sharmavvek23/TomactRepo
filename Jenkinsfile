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
      sh "ansible -i /var/lib/jenkins/my_targets /var/lib/jenkins/app-container.yml"   
     }
}


     }
  post {
     always {
          sh "echo 'I did It'"
     }
}
}
