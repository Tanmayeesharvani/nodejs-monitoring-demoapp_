# nodejs-monitoring-demoapp_

## Terminal
sudo git clone https://github.com/sreepathysois/nodejs-monitoring-demoapp.git
cd nodejs-monitoring-demoapp/
cd src/
sudo apt-get install npm
sudo npm install
sudo npm start
(
**if 3000 port occupied
sudo lsof -i :3000
sudo kill -9 10943
sudo npm start
)

>> to close ctrl+c

## Jenkins

1.nj_b:
>git
>build steps -> Execute shell:
                              cd src
                              sudo npm install --silent
                              sudo npm start (remove it during docker)
>Post-build Actions -> build otrher project: next_project

2.nj_d:
>git
>build steps -> Docker Build and Publish
                Execute Docker command -> create container
                Execute Docker command  -> start container


# Owner-avatar-python-demoapp-monitoring_

5000

## Terminal
*sudo git clone https://github.com/Tanmayeesharvani/python-demoapp-monitoring.git
*cd python-demoapp-monitoring/
*sudo apt-get install python3-pip
*cd src
*sudo python3 -m venv give_env_name
*source penv/bin/activate
*pip3 install -r requirements.txt
*ls -la
*sudo chown -R msis:msis give_env_name
*pip3 install -r requirements.txt
*cd ..
*black --check src/
*cd src
*python3 run.py

## Jenkins
1. p_b
   *>git
   *>build step -> Execute command:make lint
                                  make lint-fix
                                  make test
                                  #make run
   *>Post-build Actions -> build other project -> p_d
2. p_d:
*>git
*>build steps -> Docker Build and Publish
                Execute Docker command -> create container (5002:5000)
                Execute Docker command  -> start container
*>Post-build Actions -> build other project -> p_k
3. p_k:
*>git
*>build step -> Deploy to Kubernetes -> Kubeconfig -> 11(11) -> metion the .yaml

## Errors:
> Sudo permission Error:
  sudo usermod -aG sudo jenkins
  sudo visudo
  *add line in sudo group
  jenkins ALL = (ALL) NOPASSWD:ALL
> Jenkins password:

# PHP
80
## Terminal
sudo apt-get update -y
sudo apt install php libapache2-mod-php php-mysql -y
cd repo
sudo cp -r . /var/www/html/
sudo rm -f /var/www/html/index.html
sudo systemctl restart apache2
browser:http://localhost:80

