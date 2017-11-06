pipeline {

    stages{
        stage('Build'){
            steps{
                echo 'Building Eureka-Server'
                sh 'cd eureka-server && ./gradlew build'
                echo 'Building Zipkin-Server'
                sh 'cd zipkin-server && ./gradlew build'
                echo 'Building Spring-boot-RESTful-Service'
                sh 'cd spring-boot-restful-service && ./gradlew build'
                echo 'Building Zipkin-Server'
                sh 'cd zipkin-server && ./gradlew build'
            }
        }
    }
}