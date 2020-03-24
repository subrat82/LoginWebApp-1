node{
 
    stage('Deploy on K8s'){
       // sh "/usr/local/bin/ansible localhost -m ping"
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
