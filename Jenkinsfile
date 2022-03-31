node
 {
    stage('ContDownload')
 {
    git 'https://github.com/venkat9822891/maven-project1.git'
}

   stage('ContBuild')
 {
   sh 'mvn package'
}

   stage('ContDeployment')
 {
     deploy adapters: [tomcat8(credentialsId: 'test-use', path: '', url: 'http://172.31.33.5:8080')], contextPath: '/test', war: '**/*.war'
}
   stage('Conttesting')
 {
    git 'https://github.com/venkat9822891/Selenium-testcases.git'
    echo "testingcases completed"
}
   stage('ContDelivery')
 {
   deploy adapters: [tomcat8(credentialsId: 'production', path: '', url: 'http://172.31.39.20:8080')], contextPath: '/test', war: '**/*.war'
}
}
