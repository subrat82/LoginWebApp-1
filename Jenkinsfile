node{
 
 stage('Checkout'){
      
    git branch: 'master',
    credentialsId: 'cd86d294-d343-4a1b-8e19-388f2ac2f93b',
    url: 'https://github.com/subrat82/LoginWebApp-1.git'
      
      
      //git 'https://github.com/sasmita016/dfly-app.git'
      sh "git rev-parse --short HEAD > .git/commit-id"
      //imageTag= readFile('.git/commit-id').trim()



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
