pipeline{
    agent { label 'Agent'}
    
    stages{
        stage("Code clone"){
            steps{
            clone("https://github.com/hamad-bhaloo/django-notes-app.git","main")
                echo 'bhaiyya code clone ho gaya'
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
