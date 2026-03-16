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
