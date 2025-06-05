pipeline{
agent any

tools{
maven 'Maven'
}

stages{
stage('checkout'){
steps{
git branch:'master',url:'https://github.com/sowjanya2004/ansiblew.git'
}
}

stage('Build'){
steps{
sh 'mvn clean package'
}
}

stage('archive'){
steps{
archiveArtifacts artifacts:'target/*.war',fingerprint:true
}
}

stage('deploy'){
steps{
sh 'mvn clean package'
sh 'ansible-playbook playbook.yml -i hosts.ini'
}
}
}
}

