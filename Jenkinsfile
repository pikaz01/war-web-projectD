pipeline{
    agent{
        label 'velakaran'
    }

    tools {
        maven 'maven_3.9.0'
    }

    stages{
        stage('SCM Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/pikaz01/war-web-projectD.git']])
            }

        }

        stage('Maven-Build'){
            steps{
                sh 'mvn clean install'
            }
        }

        // stage('Sonar Scan'){
        //     steps{
        //         withSonarQubeEnv("SonarQube") {
        //             sh "${tool("Sonar_4.8")}/bin/sonar-scanner \
        //             -Dsonar.host.url=http://ec2-13-232-201-247.ap-south-1.compute.amazonaws.com:9000/ \
        //             -Dsonar.login=sqp_0c07fd0d029a2928a7f9a656ce9486e029a7affa \
        //             -Dsonar.java.binaries=target \
        //             -Dsonar.projectKey=java-maven-app"
        //         }
        //     }
        // }

        // stage('Nexus Upload'){
        //     steps{
        //         sh 'mvn -s settings.xml clean deploy'
        //     }
        // }

        // stage('deployment'){
        //     steps{
        //         sh 'ansible-playbook -i inventory deployment_playbook.yml -e "build_number=${BUILD_NUMBER}"'
        //     }
        // }

    }
}
