# simple-keycloack-static-node
A sample of using keycloak with a static page based in static-server.

Required installations: 
- nodejs 6 or latter
- docker
- git/ has a github account

This sample is using a keycloak 3.4.0.Final / docker /nodejs 6, but you can donwload it manualy if you like.

For simplicity below are the commands you should use to run the wildfly in docker(remember to install the docker machine).

  #pull the image of the keycloak of the 
  
  docker pull keycloak-base:3.2.0.Final

  #identify the hash of the image from the list 
  
  docker images

  #running the image - remember the user will be admin and the password admin, as the variables are defined below replace <imageId> with
  the id of the hash got above

  docker run -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin -p 18080:8080 <imageId>

After installed the keycloak you should do the below steps:

  - got to the ip of the docker using the port 18080 to access the keycloak console with the user (admin/admin)
  - import the nodejs-example-realm.json file
  - it will create the realm with the client configurations


If everything is correct as above , you should then clone the repository from git
  #getting the project from git
  
  git clone https://github.com/leonardocregis/simple-keycloack-static-node.git
  
  #got to the directory created
  
  cd simple-keycloack-static-node
  
  #install using npm the dependencies
  
  npm i
  
  #then run the app and try
  
  npm start
  
  #go to the url
  
  http://localhost:3001/


Known eventual problems:
  Using the windows 10 pro with the hyper-v , will run with localhost, so you need to update keycloak.json regarding that
  change the entry "auth-server-url": "http://192.168.99.100:18080/auth", to "auth-server-url": "http://localhost:18080/auth",
  
  
