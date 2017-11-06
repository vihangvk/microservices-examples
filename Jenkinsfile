pipeline {
    podTemplate(label: 'docker-slave', containers: [
        containerTemplate(name: 'gradle', image: '', command: 'cat')
    ]){
        node('docker-slave'){
            stages{
                stage('Build'){
                    container('gradle'){
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
    }
}