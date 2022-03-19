# JFrog
JFrog Home Assignment
 sudo apt-get update
 echo "jfrog ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/jfrog
 sudo usermod -aG sudo jfrog
 sudo timedatectl set-timezone Asia/Jerusalem
 echo "// Do not verify peer certificate
Acquire::https::Verify-Peer "false";
// Do not verify that certificate name matches server name
Acquire::https::Verify-Host "false";" | sudo tee /etc/apt/apt.conf.d/80ssl-execptions
 sudo apt-get install git
 git config --global user.name "shlomine"
 git config --global user.email "shlomine@gmail.com"
 sudo apt-get install openssl
 ssh-keygen -t ed25519 -C "shlomine@gmail.com"
 eval "$(ssh-agent -s)"
 ssh-add ~/.ssh/id_ed25519
 cat < ~/.ssh/id_ed25519.pub
 git clone git@github.com:shlomine/JFrog.git
 cd JFrog/
 sudo apt install openjdk-11-jre-headless
 wget http://192.168.94.142:8080/jnlpJars/agent.jar
 java -jar agent.jar -jnlpUrl http://192.168.94.142:8080/computer/JFrog%20run%20192%2E168%2E94%2E143/jenkins-agent.jnlp -secret 598f60b08e6f7ee3e85ef80c200ff5723eece72dd73dc76d2cf6d0d631063960 -workDir "/home/jfrog/JFrog" &
 sudo apt-get install -y maven
 sudo apt-get install -y docker
 sudo apt-get install -y docker.io
 wget -qO - https://releases.jfrog.io/artifactory/jfrog-gpg-public/jfrog_public_gpg.key | sudo apt-key add -
 echo "deb https://releases.jfrog.io/artifactory/jfrog-debs xenial contrib" | sudo tee -a /etc/apt/sources.list;
 sudo apt update;
 sudo apt install -y jfrog-cli-v2-jf;
 
 git add .
 git commit -m "JFrog commit"
 git push
