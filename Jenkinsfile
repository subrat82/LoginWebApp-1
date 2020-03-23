node{
  def Namespace = "default"
  def ImageName = "subratit/projects-mar-22-login-app"
  def ImageTag = "latest"
  def Creds	= "076eed1a-ddda-4fcc-b8bd-5fbf6fa738fd"


    stage('Deploy on K8s'){
       // sh "/usr/local/bin/ansible localhost -m ping"
       // sh "echo ansible ran successfully"
       
        //sh "/usr/bin/kubectl version"
        sh "/usr/bin/kubectl get pods"
        sh "/usr/bin/kubectl get namespaces"
        sh "/usr/bin/kubectl get deployments"
       // sh "/usr/local/bin/kubectl apply -f deployment.local.yaml"
      
        // sh "/usr/local/bin/kubectl apply -f kubernetes-deployment.yaml --validate=false"
        //sh "/usr/local/bin/ansible-playbook -v /Users/subrat/.jenkins/workspace/pipeline_dfly-app/deploy2.yml  --extra-vars ansible_ssh_user=root --extra-vars ImageName=${ImageName} --extra-vars imageTag=${ImageTag} --extra-vars ansible_sudo_pass=Sasmita123* "
        //sh "/usr/local/bin/ansible-playbook -vvv /Users/subrat/.jenkins/workspace/pipeline_dfly-app/deploy1.yml --extra-vars ImageName=${ImageName} --extra-vars imageTag=${ImageTag}"

    }
}
