node{
 
 stage('Checkout'){
      
    git branch: 'master',
    credentialsId: 'cd86d294-d343-4a1b-8e19-388f2ac2f93b',
    url: 'https://github.com/subrat82/LoginWebApp-1.git'
      
      
      //git 'https://github.com/sasmita016/dfly-app.git'
      sh "git rev-parse --short HEAD > .git/commit-id"
      //imageTag= readFile('.git/commit-id').trim()



  }
 
 stage('Maven Build'){ 
      sh '/usr/bin/mvn clean package -f "/var/lib/jenkins/workspace/my-login-webapp/pom.xml"'
     //sh 'ng build'
  }

  stage('Docker Build, Push'){
      sh "/usr/bin/docker --version"
      sh "echo docker login localhost:8080"
      //withDockerRegistry([credentialsId: "${Creds}", url: 'https://index.docker.io/v1/']) {
    
    //withDockerServer([uri: "tcp://127.0.0.1:2375"]) {
    //withDockerRegistry([credentialsId: "${Creds}", url: "https://index.docker.io/v1/"]) {

     //withDockerRegistry(credentialsId: "076eed1a-ddda-4fcc-b8bd-5fbf6fa738fd", url: '') {
      //sh 'docker login -u "subratit" -p "Sasmita123*" docker.io'
      //sh 'docker login --username=subratit --email=subratit@gmail.com docker.io'
     // sh 'docker login -u subratit docker.io'
     // sh 'docker login -u "subratit" -p "Sasmita123*" docker.io'
      sh "/usr/bin/docker build -t projects-mar-22-login-webapp ."
      sh "/usr/bin/docker tag projects-mar-22-login-webapp subratit/projects-mar-22-login-webapp:latest"
      sh "echo build successfully"
      sh "/usr/bin/docker push subratit/projects-mar-22-login-webapp:latest"
      //  }
    //}

    }
 
    stage('Deploy on K8s'){
        sh "/usr/bin/ansible all -m ping"
       // sh "echo ansible ran successfully"
       
        //sh "/usr/bin/kubectl version"
        //sh "/usr/bin/kubectl get pods --extra-vars ansible_ssh_user=root "
        //sh "/usr/bin/kubectl get namespaces"
       // sh "/usr/bin/kubectl get deployments"
       // sh "/usr/local/bin/kubectl apply -f deployment.local.yaml"
      
        // sh "\\\\\\\\\\\]]]]]]/usr/local/bin/kubectl apply -f kubernetes-deployment.yaml --validate=false"
     
        sh "/usr/bin/ansible-playbook -v /var/lib/jenkins/workspace/my-login-webapp/kubectl-test-playbook.yaml" 
     //--extra-vars ansible_ssh_user=root --extra-vars ansible_sudo_pass=Sasmita123* "
        //sh "/usr/local/bin/ansible-playbook -vvv /Users/subrat/.jenkins/workspace/pipeline_dfly-app/deploy1.yml --extra-vars ImageName=${ImageName} --extra-vars imageTag=${ImageTag}"

    }
}
