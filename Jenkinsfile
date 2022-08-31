pipeline {
    agent any
    
    stages {
        stage ('Build') {
            agent {
                docker {
                    image 'ubuntu:focal'
                    args '--user root --name fubuntu'
                    reuseNode true
                }
            }
                steps{
                    // sh 'ls'
                     sh ' cp Hello.cpp  / '
                    // sh 'cd / && ls '
                     sh 'apt-get update' 
                     sh 'apt install -y build-essential'
                    // sh 'apt install -y git'
                     sh 'cd / && mkdir hello_1.0-1_amd64 && cd hello_1.0-1_amd64 && mkdir DEBIAN && mkdir usr ' 
                     sh 'cd / && cd  hello_1.0-1_amd64/DEBIAN && echo "Package: hello " > control && echo "Version : 1.0 " >> control && echo "Architecture : amd64" >>control && echo "Maintainer : Gokay ">> control && echo "Description : Test" >> control  ' 
                    // sh ' cd / && cat hello_1.0-1_amd64/DEBIAN/control'
                     sh ' cd / && g++ Hello.cpp && mv a.out hello'
                     sh ' cd / && cd  hello_1.0-1_amd64/usr && mkdir bin  '
                     sh 'cd / &&  cp hello hello_1.0-1_amd64/usr/bin'
                     sh ' cd / && mv hello helo'
                     sh ' cd / && dpkg-deb --build hello_1.0-1_amd64'
                     sh ' cd / &&  dpkg -i hello_1.0-1_amd64.deb'
                     sh 'hello'
                    // sh ' cd / && ls'    
                   //  sh 'ls'
                     
                }
                }
                stage ('build2') {
                    steps {
                        echo 'done'
                    }
                }
            }
        }
    
