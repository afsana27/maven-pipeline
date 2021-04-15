  
pipeline
{
agent any
stages
{
  stage('scm checkout')
  { steps {  git branch: 'master', url: 'https://github.com/afsana27/maven-pipeline'  } }
  stage('code complile')
  {
    steps{   
         withMaven(jdk: 'java_home', maven: 'local_maven') {
           sh 'mvn complile'}}}
  stage('code test') {
    steps{   
          withMaven(jdk: 'java_home', maven: 'local_maven') {
            sh 'mvn test'}}}
  stage('build my job') {
    steps{   
          withMaven(jdk: 'java_home', maven: 'local_maven') {
    sh 'mvn build'}}    
}
}
}
