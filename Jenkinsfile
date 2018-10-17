// Allocate Build Node
node('master') {
    stage("Fetch Source Code") {
        git 'https://github.com/TrainingByPackt/Beginning-Continuous-Delivery-With-Jenkins'
    }

    dir('Lesson5') {
        printMessage('Running Pipeline')

        stage("Testing") {
            sh 'python test_functions.py'
        }
        
        stage("Deployment") {
            
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying to master branch!')
            } else {
                printMessage('No deployment configured for the selected branch')
            }
        }


        printMessage('Pipeline Complete')
    }
}

def printMessage(message) {
    echo "${message}"
}
