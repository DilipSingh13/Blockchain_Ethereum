# Blockchain Ethereum Using Ropsten Test Network
## Introduction

In this project we are performing Ethereum ERC20 token transfer from Ropsten testnet and to perform basic token distributions from contract owner account to different accounts (10 diffrent accounts). 

## Setup Guide

## Steps for Deploying Contract
Steps to deploying contract

Step1: First, download this project:

    $ git clone https://github.com/DilipSingh13/Blockchain_Ethereum.git

Step2: Open Remix * https://remix.ethereum.org/ * on browser

    1. Copy and paste the code from ERC20_dilip.sol provided in GitHub repository (To creates contract)
    
    2. Compile the ERC20_dilip.sol by selecting 0.6.6+commit.6c089d02 and click on "Complie" button
    
    3. Before proceeding further make sure that your matamast is connected and running.
    
    4. In MetaMask select network as 'Ropsten Test Network'
    
    5. Now, Deploy it on Ropsten testnet by selecting environment as "Ijected Web3" and selct the contract as "ERC20" and clcik deploy button
    
    6. Once contract is deployed you will see a link in terminal click on the link to view deployed contract.
    
    7. Now, click on intract with (to) address to publish your contract (To verify that your contract does not have any malicious code)

## Node.js Code pre-requisite

1. To install the dependencies (web3, express, big-numbers, etc):

        $npm install (Install all the required dependencies from package.json and package-lock.json)
        
2. Change the following things in method.js and contract.js file 
    a. Addresses
    b. Private key
    c. Deployed contract address
    d. Infura ropsten url
        
        Account address is your ropsten testnet account1 address i.e contract owner address
        Private key with your Ropsten testnet account1 private key
        Infura ropsten URL with your Infura procject with endpoint Ropsten
        Contract Addresss with your deployed Remix code contract address

3. Now to start transferring token using:

        $node method.js
        
4. To transfer token with rest api by running halndler.js

        $node handler.js
            or
        $curl -XPOST http://localhost:8080/transfer
        
## Create and Deploy Docker image

    1. build docker container
       $docker build -t [user/tag] .
       eg. $docker build -t dilipsingh1920/blockchain .
    
    2. Check for the docker image
       $docker image
    
    3. For cheking running container
       $docker ps
    
    4. To run docker image
       $docker run -p 49160:8080 --name dilip -d dilipsingh1920/x19208073
    
    5. Commit the docker container
       $docker commit 480695d53be2 dilipsingh1920/blockchain:999
    
    6. To push docker image
       $docker push dilipsingh1920/blockchain:999

Note: --name <folder_name> should be in lower case

## Debugging port unavailable error
There might be possibilty of port unavailable due to exisiting ystem process running on port 8080.
To stop the exisiting port 8080 process, Steps are below:

    1. Stop the docker
       $docker stop $(docker ps -a -q)
    
    2. Check current running process
       $sudo lsof -i tcp:49160
    
    3. Kill the exisiting running process
       $sudo kill -9 71

