def gv

pipeline {
    agent any

    parameters {
        string(name: 'name', defaultValue: 'mina', description: 'name of owner')
    }

    stages {
        stage('load') {
          steps {
            script {
              gv = load 'script.groovy'
              if (env.BRANCH_NAME == 'main') {
                echo "branch name is ${env.BRANCH_NAME}"
                    } else {
                echo 'not main branch'
          }
            }
          }
        }

        stage('build') {
            input {
              message "select env dev prod"
              ok "Done"
              parameters{
                  choice(name:"ENV", choices: ["dev", "prod"], description: "the env of project")
              }

            }
          steps {

            script {parameterDefinitions
                gv.buildApp()
                echo "deploying in ${ENV}"
            }
          }
        }
    }
}
