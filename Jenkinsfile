pipeline {
    agent any
    stages {
        stage("Matrix") {
            matrix {
                axes {
                    axis {
                        name 'CPU'
                        values "arm", "mips"
                    }
                }
                agent {
                    // agentagent
                    node {
                        label "win"
                        customWorkspace "$WORKSPACE$CPU"
                    }
                }
                stages {
                    stage("MatrixBuild") {
                        steps {
                            script {
                                stage("A") {
                                    print "A"
                                    writeFile(file: "a.txt", text: "aaa")
                                }
                                stage("B") {
                                    print "B"
                                }
                                stage("C") {
                                    print "C"
                                }
                            }
                        }
                    }
                }
            } 
        }
    }
}
