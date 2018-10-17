env.dockerimagename="devopsbasservice/buildonframework:buildon-v1.0"
node {
   stage ('Build') {
   //If some other Repository is to be given apart from current repo, provide git URL as below demo...
    checkout scm
    sh 'mvn clean package -DskipTests=True'
  }     
 
}
