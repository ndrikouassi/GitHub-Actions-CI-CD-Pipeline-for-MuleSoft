pipeline {

agent any

stages {

stage(‘Build’) {

steps {

sh "mvn clean install"

}

}

stage(‘Test’) {

steps {


sh "mvn test"

}

}

stage(‘CloudHub’) {



steps {


sh "mvn -X clean package deploy -DmuleDeploy -Dusername="alphakoua03" -Dpassword="qWenoYLiFtgG45" -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2"

}

}

}

}
