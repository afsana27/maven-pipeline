pipeline
{
agent any
stages
{
  stage('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/afsana27/maven-pipeline'  } }

  stage('code build')
  { steps {  withMaven(jdk: 'LocalJDK', maven: 'local_maven_3.5') {
      sh 'mvn clean package'                    // provide maven command

} } }


  stage('deploy to dev')
    { steps {
       sshagent(['cicd-pipeline']) {
       sh 'scp -o StrictHostKeyChecking=no */target/*.war  ec2-user@3.223.195.21:/var/lib/tomcat/webapps'
    }
            }
         }

}
}
