env.dockerimagename="devopsbasservice/buildonframework:buildon-cf-plugin-1.0"
node {
   stage ('Build') {
   //If some other Repository is to be given apart from current repo, provide git URL as below demo...
    checkout scm
    sh 'mvn clean package -DskipTests=True'
  }   
   
   stage ('Archive') {  
       sh "mvn -B help:evaluate -Dexpression=project.build.finalName | grep -e '^[^[]' > finalNameFile"
          projectName=readFile('finalNameFile').trim()

          sh "mvn -B help:evaluate -Dexpression=project.packaging | grep -e '^[^[]' > packagingFile"
          packaging=readFile('packagingFile').trim()
          artifact="target/projectName.packaging"
          artifactName="target/${projectName}.${packaging}"
      echo "artifact"
      echo ${artifact}
      
      echo "artifactName"
      echo ${artifactName}
  }  
}
