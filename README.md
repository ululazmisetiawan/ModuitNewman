# ModuitNewman

Note : 
trigger:
- main -> Ambil repo dengan branch main

pool:
  vmImage: ubuntu-latest -> Mengguanaan virtual machine ubuntu - latest

steps:
- task: NodeTool@0
  inputs:
    versionSpec: '10.x'
  displayName: 'Install Node.js'    -> Untuk menginstall nodejs

- script: |
    npm install
    npm run build
    npm install -g newman
  displayName: 'npm install and build'   -> Untuk running npm dan install newman

- script: |
    newman run Moduit.postman_collection.json
  displayName: 'Running File Newman' -> Untuk running file newman
