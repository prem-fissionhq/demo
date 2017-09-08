node{
  checkout scm
  sh 'echo $BRANCH_NAME'
 def logdata = ""
 def commitId = ""
 def repoName= ""
  def gitURL=""

 try {

  stage("Pull") {
   checkout scm
   sh 'echo $BRANCH_NAME'
   sh 'echo $printenv'
   sh 'git log -1 > logdata'
   sh 'git rev-parse HEAD > commit'
   sh 'git rev-parse --show-toplevel > repoName '
   sh 'git config --local remote.origin.url >gitURL'
   commitId = "https://github.com/prem-fissionhq/demo" + readFile('commit').trim()
   logdata = readFile('logdata')
   echo "${logdata}"

  }
  stage("Build") {
   
   sh "echo 'build'"
  }
  stage("Publish") {
   sh "echo 'publish'"
  }
  stage("deploy") {
   sh "echo 'deploy'"
  }
 } catch (e) {
  currentBuild.result = "FAILED"
  throw e
 } finally {
  
 }
}
