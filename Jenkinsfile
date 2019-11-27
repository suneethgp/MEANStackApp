node('docker') {
  stage('SCM') {
    checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: 'refs/heads/develop']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/CodeBabel/MEANStackApp.git']]]
  }
  stage('SonarQube Analysis') {
        sh "/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/SonarQube/bin/sonar-scanner -Dsonar.host.url=http://localhost:9000 -Dsonar.projectName=meanstackapp -Dsonar.projectVersion=1.0 -Dsonar.projectKey=webgoat:app -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/sonarqube_test_pipeline"
    }
  }
