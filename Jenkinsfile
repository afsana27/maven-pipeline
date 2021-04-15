  
pipeline
{
agent any
stages
{
  stage('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/afsana27/maven-pipeline'  } }
  stage('build my project')
  {
    steps{   
  withMaven(jdk: 'java_home', maven: 'local_maven') {
    sh 'mvn install'}}
}
}
}
