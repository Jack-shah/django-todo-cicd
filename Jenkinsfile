

pipeline{
    agent any
    parameters{
        choice(name :'Version',choices:['1.0.0','1.0.1','1.0.2'] ,description:'describe something about this parameters')
        booleanParam(name : 'executeTestStage' ,defaultValue:true,description:'')
    }
    stages{
        stage('build'){
            steps{
                echo "command  to be executed for build of the project"
            }
        }
        stage('test'){
            when{
                expression{
                    params.executeTestStage==true   // using paramenter to apply condtition on test state
                }
            }

            steps{
                echo "command  to be executed for test of the project"
            }
        }
        stage('deploy'){
            steps{
                echo "command  to be executed for deploy of the project"
                echo " choose the version to deploy with ${params.Version} "// using parameter as variable
            }
        }
    }
}
