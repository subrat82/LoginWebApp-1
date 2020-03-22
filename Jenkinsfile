node{
  def Namespace = "default"
  def ImageName = "subratit/projects-mar-22-login-app"
  def ImageTag = "latest"
  def Creds	= "076eed1a-ddda-4fcc-b8bd-5fbf6fa738fd"


  stage('Checkout'){
      
    git branch: 'master',
    credentialsId: 'cd86d294-d343-4a1b-8e19-388f2ac2f93b',
    url: 'https://github.com/subrat82/LoginWebApp-1.git'
    sh "git rev-parse --short HEAD > .git/commit-id"
      //imageTag= readFile('.git/commit-id').trim()



  }
  
  stage('Maven Build'){ 
    //sh '/Applications/apache-maven-3.6.3/bin/mvn clean install -f "/Users/subrat/.jenkins/workspace/pipeline-login-webapp-1/pom.xml"'
     //sh 'ng build'
  }
  
  stage('Install tomcat'){
    //sh "/usr/local/bin/ansible-playbook /Users/subrat/.jenkins/workspace/pipeline-login-webapp-1/install-tomcat.yaml"
    //copy zar file 
    //sh "cp -r /Users/subrat/.jenkins/workspace/pipeline-login-webapp-1/target/ /Users/subrat/apache-tomcat-9.0.33/webapps/"
  }

  stage('Docker Build, Push'){
      sh "/usr/local/bin/docker --version"
     // sh "echo docker login localhost:8080"
      sh 'docker login -u "subratit" -p "Sasmita123*" docker.io'
     // sh "/usr/local/bin/docker build -t projects-mar-19 ."
      sh "/usr/local/bin/docker tag projects-mar-22-login-webapp subratit/projects-mar-22-login-webapp:latest"
      sh "echo build successfully"
      sh "/usr/local/bin/docker push subratit/projects-mar-22-login-webapp:latest"
    }
   
    
    stage('Deploy on K8s'){
       // sh "/usr/local/bin/ansible localhost -m ping"
       // sh "echo ansible ran successfully"
        sh "/usr/local/bin/kubectl get ns"
        sh "/usr/local/bin/kubectl version"
        sh "/usr/local/bin/kubectl get pods"
        sh "/usr/local/bin/kubectl get deployments"
       // sh "/usr/local/bin/kubectl apply -f deployment.local.yaml"
      
        // sh "/usr/local/bin/kubectl apply -f kubernetes-deployment.yaml --validate=false"
        //sh "/usr/local/bin/ansible-playbook -v /Users/subrat/.jenkins/workspace/pipeline_dfly-app/deploy2.yml  --extra-vars ansible_ssh_user=root --extra-vars ImageName=${ImageName} --extra-vars imageTag=${ImageTag} --extra-vars ansible_sudo_pass=Sasmita123* "
        //sh "/usr/local/bin/ansible-playbook -vvv /Users/subrat/.jenkins/workspace/pipeline_dfly-app/deploy1.yml --extra-vars ImageName=${ImageName} --extra-vars imageTag=${ImageTag}"

    }
}
