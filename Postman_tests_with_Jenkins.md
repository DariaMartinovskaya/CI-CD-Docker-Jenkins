## Running Postman tests with Jenkins
#### Preconditions: Node js and Newman are installed

To install Node js, run the following commands in the terminal:
```
apt-get install nodejs
```
```
Y
```
To install Newman, run the following commands in the terminal:
```
apt  install -y npm
```
```
npm install -g newman
```
#### 1. Create item with "Postman_tests" item name at Jenkins


#### 2. Click the [Freestyle project] Button

#### 3. Click the [OK] Button

#### 4. Click the "Git" Radiobutton

#### 5. Paste the URL copied from the gitHub project's repository to the "Repository URL" line

URL of the project: https://github.com/DariaMartinovskaya/CI-CD-Docker-Jenkins.git

#### 6. Change Branch from "master" to "main"

#### 7. Click "Build after other projects are built".

This option works as follows: when some other projects finish building, a new build is scheduled for this project.

#### 8. Past "Project_1" to the "Project to watch" line

#### 9. Select "Execute shell" from the "Build Steps" dropdown list

#### 10. Paste "newman run Postman_collection.json" into the "Command" window

Note: Postman_collection.json file was previously exported into the repository from Postman.

#### 11. Click the [Apply] and the [Save] Buttons

#### 12. Click the [Build now] Button
Tests are run. Console output:
```
Started by user Daria
Running as SYSTEM
Building in workspace /var/jenkins_home/workspace/Postman_tests
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/jenkins_home/workspace/Postman_tests/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/DariaMartinovskaya/CI-CD-Docker-Jenkins.git # timeout=10
Fetching upstream changes from https://github.com/DariaMartinovskaya/CI-CD-Docker-Jenkins.git
 > git --version # timeout=10
 > git --version # 'git version 2.39.2'
 > git fetch --tags --force --progress -- https://github.com/DariaMartinovskaya/CI-CD-Docker-Jenkins.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 2a7c80f40f2db8b40d74290eda22644f39afc84a (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 2a7c80f40f2db8b40d74290eda22644f39afc84a # timeout=10
Commit message: "Add files via upload"
 > git rev-list --no-walk 7daa8b427a630919fa5be1566cdea1ed3c5e9239 # timeout=10
[Postman_tests] $ /bin/sh -xe /tmp/jenkins3085684817348505714.sh
+ newman run Postman_collection.json
newman

Postman_HW_1

→ EP_1
  GET http://162.55.220.72:5007/get_method?name=Daria&age=27 [200 OK, 169B, 799ms]

→ EP_3
  GET http://162.55.220.72:5007/object_info_1?name=Daria&age=27&weight=49 [200 OK, 231B, 475ms]

→ EP_4
  GET http://162.55.220.72:5007/object_info_2?name=Daria&age=27&salary=1000 [200 OK, 464B, 340ms]

→ EP_5
  GET http://162.55.220.72:5007/object_info_3?name=Daria&age=27&salary=1000 [200 OK, 525B, 142ms]

→ EP_6
  GET http://162.55.220.72:5007/object_info_4?name=Daria&age=27&salary=1000 [200 OK, 237B, 163ms]

→ EP_2
  POST http://162.55.220.72:5007/user_info_3 [200 OK, 370B, 169ms]

→ EP_7
  POST http://162.55.220.72:5007/user_info_2 [200 OK, 464B, 154ms]

┌─────────────────────────┬─────────────────────┬────────────────────┐
│                         │            executed │             failed │
├─────────────────────────┼─────────────────────┼────────────────────┤
│              iterations │                   1 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│                requests │                   7 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│            test-scripts │                   0 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│      prerequest-scripts │                   0 │                  0 │
├─────────────────────────┼─────────────────────┼────────────────────┤
│              assertions │                   0 │                  0 │
├─────────────────────────┴─────────────────────┴────────────────────┤
│ total run duration: 2.3s                                           │
├────────────────────────────────────────────────────────────────────┤
│ total data received: 1.43kB (approx)                               │
├────────────────────────────────────────────────────────────────────┤
│ average response time: 320ms [min: 142ms, max: 799ms, s.d.: 226ms] │
└────────────────────────────────────────────────────────────────────┘
Finished: SUCCESS
```
#### 13. Link to screen recording of Postman tests running: https://drive.google.com/file/d/1gRFwmx_Oup1Vi1T2RsQ3Pd-KQrySo91I/view?usp=sharing
