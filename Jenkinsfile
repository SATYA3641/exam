pipeline{
    Agent any{
        Stages{
            Stage("build"){
                steps{
                    echo "docker build"
                    bat "docker build -t mypythonflaskapp"

                }
            }
            Stage("run"){
                steps{
                    echo "run"
                    bat "docker rm -f mycontainer || exit 0"
                    bat "docker run -d -p 5000:5000 --name mycontainer mypythonflaskapp"

                }
            }
        }
    }
post{
    success{
        echo 'Pipeline success'
    }
    failure{
        echo 'Pipeline failed'}
    }
}

