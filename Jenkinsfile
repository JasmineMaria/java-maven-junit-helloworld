env.dockerimagename="devopsbasservice/buildonframework:buildon-cf1"
node {
   stage ('Build') {
   //If some other Repository is to be given apart from current repo, provide git URL as below demo...
    checkout scm
    sh 'mvn clean package -DskipTests=True'
  }   
   
   stage ('Deploy to PCF') {  
    pushToCloudFoundry(
  target: 'api.system.dev.digifabricpcf.com',
  credentialsId: 'pcf-sa-creds',
  organization: 'cde-product-integration',
  cloudSpace: 'cde-product-integration',  
  manifestChoice: [
    value: 'jenkinsConfig',
    appName: 'java-maven-junit-helloworld',
    memory: 512,
    instances: 1,
    appPath: 'target/java-maven-junit-helloworld.jar'
  ]
)
  }  
}
