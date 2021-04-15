  
pipeline
{
agent any
stages
{
  stage('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/afsana27/maven-pipeline'  } }
  stage('code build')
  {
    steps{   
  withMaven(jdk: 'java_home', maven: 'local_maven') {
    sh 'clean package'}}
}
}
}
