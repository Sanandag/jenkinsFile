pipeline {
    agent {label 'master'}

   // tools {
        // Install the Maven version configured as "M3" and add it to the path.
   //     jdk "myJava"
    //    maven "myMaven"
    //}
options([parameters([string(defaultValue: '-Xms512m -Xmx1024m -Xss1024k -XX:MaxPermSize=1024m -Dmaven.test.failure.ignore=false', name: 'MAVEN_OPTS')])])
    stages {
        stage ('Git-Repo'){
            steps{
                // Get some code from a GitHub repository
                git 'https://github.com/Sanandag/test.git'
               // git credentialsId: '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', url: 'https://github.com/Sanandag/cip-partner-api.git'
                ///app_src/cip-partner-api/pom.xml'
            }
        }
        stage('Build') {
            steps {
                // Run Maven on a Unix agent.
                //sh "mvn -Dmaven.test.failure.ignore=true clean package"
               // sh "mvn -Ddir = /var/lib/jenkins/workspace/SamplePipeline/app_src/cip-partner-api/pom.xml"
                //sh 'mvn  -f /var/lib/jenkins/workspace/SamplePipeline/app_src/cip-partner-api/pom.xml clean compile'
		    
                sh "mvn compile"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
           
            }
        
        stage('Code Review') {
            steps {
                // Run Maven on a Unix agent.
               // sh "mvn -f /var/lib/jenkins/workspace/SamplePipeline/app_src/cip-partner-api/pom.xml pmd:pmd"
                sh "mvn pmd:pmd"
                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('Package') {
            steps {
                // Run Maven on a Unix agent
              //  "set MAVEN_OPTS=-Xmx1024m -XX:MaxPermSize=128m"
               //"mvn -DXms512m -DXmx1024m -DXX:MaxPermSize=512m"
                //sh "mvn -f /var/lib/jenkins/workspace/SamplePipeline/app_src/cip-partner-api/pom.xml clean package"
                    sh "mvn package"
                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }

           // post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
          //      success {
            //        junit '**/target/surefire-reports/TEST-*.xml'
              //      archiveArtifacts 'target/*.jar'
                // }
        //    }
        
    }
	}
