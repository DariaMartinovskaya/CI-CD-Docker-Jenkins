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
#### 1. Create item with "Postman_tests" item name at Jenkins


#### 2. Click the [Freestyle project] Button

#### 3. Click the [OK] Button

#### 4. Click "Git" Radiobutton

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
