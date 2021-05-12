http://15.206.81.210:8081/
admin
admin123

How to download a Package from nexus using Maven?
==================================================
Scnario  - There are 2 projects. CHAT and MAIL. Mail is dependent on chat, this while building Mail, we need to have a latest lib of chat.

Step 1 - We need to build CHAT project and deploy(Upload) to nexus.

Step 2 - We need to Modify pom.xml of MAIL project and add a CHAT lib depedency.

Step 3- Make sure that you have a group repo in nexus which contain all the child repos where we have packages of CHAT.

Step 4 - Modify setting.xml with mirror element with group repo

Step 5 - Modify setting.xml with server element with username & pass

Step 6 - Make sure mirror element ID and server element id must match.

Step 7 - mvn compile/test/package/install/deploy of MAIL.

How to work with NPM project with Nexus?
=============================================
Step 1 - Create a npm nexus repo for 
		Hosted	http://15.206.81.210:8081/repository/npm-hosted-all/
		proxy	http://registry.npmjs.org/
		Group	http://15.206.81.210:8081/repository/nuget-group/

Step 2 - Install Node in your server

Step 3 - Create a Sample Project using NPM

309  mkdir npmprj
  310  cd npmprj/
  311  clear
  312  ls
  313  npm init
  314  ls
  315  clear
  316  ls
  317  ls
  318  vi index.js
  319  npm install express --save
  320  ls
  321  clear
  322  ls
  323  node index.js


Step 4 - Create a Nexus ID n Pass which has deploy access to npm repo in nexus.

deploy-user
deploy-user123

Step 5 - Create .npmrc with a REPO Location and Access

Step 6 - Modify package.json file with group repo name

Step 7 - Do npm publish


Refer
https://help.sonatype.com/repomanager3/formats/npm-registry#npmRegistry-Registryconfigurationin.npmrc
https://help.sonatype.com/repomanager2/node-packaged-modules-and-npm-registries
https://blog.sonatype.com/custom-node-module-management-using-private-npm-registry-configured-in-nexus-repository
https://blog.sonatype.com/using-nexus-3-as-your-repository-part-2-npm-packages

https://github.com/devopsschool-demo-labs-projects/npm-nexus-hello-world
















