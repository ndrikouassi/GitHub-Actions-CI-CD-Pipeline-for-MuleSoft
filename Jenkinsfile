pipeline {

agent any

stages {

stage(‘Build Application’) {

steps {

sh "mvn clean install"

}

}

stage(‘Test’) {

steps {


bat "mvn test"

}

}

stage(‘Deploy CloudHub’) {

environment {

ANYPOINT_CREDENTIALS = credentials(‘ANYPOINT_PLATFORM_CREDENTIALS’)

}

steps {


sh "mvn -X clean package deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2"

}

}

}

}