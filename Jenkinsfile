pipeline {
    agent any
    
  environment {
        TIME_ZONE = 'Asia/Seoul'
        
        // GitHub 계정정보. 본인껄로 넣으세요!!
        GIT_TARGET_BRANCH = 'main'
        GIT_REPOSITORY_URL = 'https://github.com/Plerandase/app-com'
        GIT_CREDENTIONALS_ID = 'git_cre'


        // AWS ECR
        AWS_ECR_CREDENTIAL_ID = 'aws_cre'
        AWS_ECR_URI = '029290955601.dkr.ecr.ap-northeast-2.amazonaws.com'
        AWS_ECR_IMAGE_NAME = 'app'
        AWS_REGION = 'ap-northeast-2'
        
    }

    stages {
        // 첫번째 스테이지 : 초기화.

        stage('1.init') {
            steps {
                echo '1.init stage'
                deleteDir()
            }
        }

        // 두번째 스테이지 : 소스코드 클론

        stage('2.Cloning Repository') {
            steps {
                echo '2.Cloning Repository'
                git branch: "${GIT_TARGET_BRANCH}",
                    credentialsId: "${GIT_CREDENTIONALS_ID}",
                    url: "${GIT_REPOSITORY_URL}"

                // 깃플러그인 설치하면 마치 함수쓰듯 사용가능.
            }
        
        }
