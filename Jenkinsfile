node
{
stage ('Source code-Checkout')
{
  git 'https://github.com/yadamakanti7/Gameoflife_Pipeline.git'
}
stage ('Source code-Package')
{
  sh 'mvn package'
}
  stage ('deploy war -Tomcat Server')
  {
    sshagent(['Ec2_deploy']) 
    {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@3.16.69.238:/var/lib/tomcat7/webapps'
    }
  }
}
