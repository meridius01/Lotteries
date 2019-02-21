# Design Patterns for Ethereum and Hyperledger Lottery

## Table of Contents
<!-- TOC -->
- [1. Simple Lottery](#1-simple-lottery)
    - [1.1. Ethereum](#11-ethereum)
    - [1.2. Hyperledger](#12-hyperledger)
- [2. Recurring Lottery](#2-recurring-lottery)
    - [2.1. Ethereum](#21-ethereum)
    - [2.2. Hyperledger](#22-hyperledger)
- [3. RNG Lottery](#3-rng-lottery)
    - [3.1. Ethereum](#31-ethereum)
    - [3.2. Hyperledger](#32-hyperledger)
- [4. Powerball](#4-powerball)
    - [4.1. Ethereum](#41-ethereum)
    - [4.2. Hyperledger](#42-hyperledger)
- [Reference](#reference)
<!-- /TOC -->

## I. Simple Lottery
In this type of lottery the winner will be selected from all participants who bought a lottery ticket randomly. In this type of lottery the players can only buy one ticket per transaction and there is no winning number or combination to draw to select the winner.
### 1.1 Ethereum
 * Change the version to 4.15 from settings tab before running the smart contract.
 * Enter the time duration in seconds upon deploying the smart contract.
 * Once deployed, you can choose any account to buy a ticket worth 0.01 ether until the duration expires.
 * Five minutes after duration expires, the account who deployed the smart contract can only draw the winner.
 * The jackpot which is the total amount of the tickets from the accounts can be withdraw by the winner.
### 1.2 Hyperledger
 * Enter the duration before deploying the chain code.
 * Participats must register their chain code before joining the lottery to recognized each peer.
 * Unlike Ethereum, Hyperledger does not use an own crypto currency but they can use digital money to buy tickets.
 * Same with Ethereum, the only user who deployed the chain code can only draw the winner.
 * The jackpot is the total sum of the tickets from participants, which can be withdraw by the winner.
## II. Recurring Lottery
This kind of lottery is also similar with the simple lottery, but more realistic. The difference is that this lottery will occur in rounds so that a new prize pool is started every time the old one closes, and users are allowed to purchase multiple tickets in one transaction.
### 2.1 Ethereum
 * In Ethereum, after deploying the smart contract, the owner must set the ticket’s price and the duration of lottery.
 * After that, the owner can start the lottery.
 * The first thing that the user needs to do is to buy a one or multiple ticket in order to join a round in lottery.
 * The owner will close the ticket for the round, then draw winner in the current round.
 * If the user is the winner, the user can withdraw the price.
 * If the user didn’t win, he can join again in the next round. Repeat step in buying ticket.
### 2.2 Hyperledger
 * In recurring lottery in Hyperledger, you need first to set the duration before deploying the chain code. That is similar to simple lottery.
 * After that, participants must register their chain code before joining the lottery to recognized each peer.
 * Unlike Ethereum, Hyperledger does not use an own crypto currency but they can use digital money to buy tickets.
 * Multiple tickets can be bought by users.
 * Same with Ethereum, the only user who deployed the chain code can only draw the winner.
 * If the user win, he can withdraw the prize. If not, he can join again in the next lottery round by repeating first step in buying tickets.
## III. RNG Lottery
RNG Lottery is a lottery variant, where the owner of the contract will draw a number and checks it if who have won the lottery. First, the contract owner will deploy the contract with the given transaction blocks to determine the state if the buying phase ends and the reveal phase ends. After deployment, the participants will create commitment with their number and pay. When the buying phase ends, the reveal phase starts. During the reveal phase, the participants will reveal their numbers. If they have not reveal their number within the duration, their ticket will be forfeited. When the reveal phase ends, the owner will draw a number to check if anyone have that number. The participants can view who have won the lottery. If it is a winning number, the participant of the winning number can withdraw its winnings, thus ending the whole lottery.
### 3.1 Ethereum
  * Should work at least with ver. 4.15 of Solidity.
  * Enter the transaction block prior to deployment.
  * Participants can create commitment with their number and pay it for 0.01 ether.
  * Wait for the buying phase to end. 
  * Reveal your number during reveal phase or your number will be forfeited.
  * Wait for the owner to draw a number when the reveal phase ends.
  * View the details of that user who have won the lottery.
  * The winner will withdraw the winnings.
### 3.2 Hyperledger
  * Enroll an admin and at least 3 users.
  * Run their apps. 
  * As a participant, pen the port of the admin to make a commitment with your number, and pay for it.
  * Wait for the buying phase to end. 
  * While on the reveal phase, reveal your number or your number will be forfeited.
  * After the reveal phase, wait for the admin to draw a number. 
  * The participants can view who have won the lottery.
  * If it was a winning number, the winner can withdraw its winnings.
## IV. Powerball Lottery
Powerball is a type of lottery that a user picks 6 numbers per ticket. The first 5 numbers are the standard numbers from 1-69 and the sixth number are the special number from 1-26 that offers extra rewards. Every 15 seconds, a drawing of tickets is held and a winning ticket that consists of 6 numbers is picked. Prizes are paid out based on the number of winning numbers that matched on your ticket. 
### 4.1 Ethereum
 * Before compiling the smart contract, go to Settings and change the Solidity version to 0.4.15.
 * Go to the Compile tab and click the "Start to compile" button to compile the smart contract.
 * Go to the Run tab and change the Environment to "JavaScript VM".
 * Click the "Create" button below to deploy the smart contract.
 * In order to buy a ticket, you must pay 0.002 ether and pick 6 numbers, the first 5 number must between 1-69 and the sixth number must     between 1-26. (ex. [[1,2,3,4,5,6]])
 * Click the buy button to buy the ticket.
 * To draw the winning numbers, enter the round number and click the "drawNumbers" button.
 * To know the winning numbers, enter again the round number and click the "winningNumbers" button. Click the details button and you will     see the winning numbers.
 * Prizes are paid out based on the number of winning numbers matched on your ticket
### 4.2 Hyperledger
 * To buy a ticket, the participants must register themselves first before joining in the lottery.
 * In Hyperledger, there are no cryptocurrency unlike other blockchain platforms but you can use digital money to buy tickets.
 * Once you've registered in the game, pick 6 numbers, the first 5 number must between 1-69 and the sixth number must between 1-26.
 * In every 15 seconds, a drawing is held and a winning ticket consist of six numbers is picked.
 * The prizes are paid out based on the number of winning numbers matched on your ticket.
Authors :

Marvin Clyde Custodio, Joshua Malabanan, Joshua Pentinio, Paolo Syd Ruiz, Ronnel Galag

## Reference

Ethereum reference: Iyer, K. & Dannen, C. (2018). _Building Games with Ethereum Smart Contracts_ (pp. 171-209). Brooklyn, New York: Apress
