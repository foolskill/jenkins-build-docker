node {
  def app

  stage('Clone') {
    checkout scm
  }

  stage('Build') {
    app = docker.build('tanou/tanou')
  }

  stage('Run') {
    docker.image('tanou/tanou').withRun('-p 80:80') { c ->
      sh 'docker ps'
      sh 'curl localhost'
    }
  }
}
