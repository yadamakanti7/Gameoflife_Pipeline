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
    sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/PipeLine/gameoflife-web/target/gameoflife.war root@172.31.13.54:/var/lib/tomcat7/webapps/myApp.war'
    }
  }
}
