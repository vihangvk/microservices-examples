podTemplate(label: 'docker-slave', cloud: 'dev-kube', namespace: 'devops', serviceAccount: 'jenkins',
containers: [
    containerTemplate(name: 'gradle', image: 'java:openjdk-8u91-jdk', ttyEnabled: true, command: 'cat')
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
                    echo 'Building Spring-boot-WebApp'
                    sh 'cd spring-boot-webapp && ./gradlew build'
                }
            }
        }
    }
}