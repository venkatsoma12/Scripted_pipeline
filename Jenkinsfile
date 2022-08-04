node {

    stage ('git'){
        git branch: '2.1-master', url: 'git@github.com:thymeleaf/thymeleafexamples-petclinic.git'
    }
     
    stage ('compile'){
        sh 'mvn compile'
    }
   
    stage ('test'){
        sh 'mvn test'
    }
    
    stage ('package'){
        sh 'mvn package'
    }
    
    stage('Publish'){
        
        junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
    }  
    
    stage('Deploy'){
        sh 'cp -r /root/.jenkins/workspace/Jenkinsfile/target/petclinic.war /root/Desktop/apache-tomcat-8.0.32/webapps/'
    }    
}   


