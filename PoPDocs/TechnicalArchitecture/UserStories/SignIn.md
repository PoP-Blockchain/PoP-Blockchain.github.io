# Sign in PoP Docs

<p><strong>VALUE PROPOSITION</strong></p>

> **As a** regular user

> **I want** to access my PoP Docs account

> **So that** I do my Sign in

<p><strong>ACCEPTANCE CRITERIA</strong></p>

- User must have the password for the wallet used to create the PoP Docs account

- We do not store user password

- We do not store the user's mneumonic phrase

<p><strong>SCREEN DRAFTS</strong></p>

<p align="center">
  <img width=70% src="img/signin.png">


</p>

<p><strong>USER STORY CARD</strong></p>

**Name:** Create account

**Author:** 

- [Daniela Franciscatto](https://github.com/danielaanjos) 

**Date:** Dec 15, 2020

**Actors:**  

- user with created account PoP Docs

**Main Flow:**

1. The user accesses the application via browser with the url <https://docs.popblockchain.org/>

2. Sign in
    1. User fills in the password field 'password'
    2. Click Sign in ‘button’
    3. System checks wallet on local storage
        1. If do not have a wallet in the local storage, 
            1. Display an alert message (1) and continue on the ‘Sign in’ page
        2. If wallet exists,
            1. Display Registry Smart contract address
            2. If have a Persona Smart contract created
                1. Displays the ‘dashboard’ page
            3. If not, display Create Persona smart contract  page

3. End use case

**Postcondition:**

- User logged into PoP Docs

**Messages:**

- alert message (1): Wallet do not exists, create or restore one!

<p><strong>SCENARIOS</strong></p>

```gherkin
@Sign_in
Feature: Sign in account
In order to I have a account
As a user I want to Sigin with my password

  Scenario: Sign in with a valid password
    Given I am at wallet Sign in page
    When I fill  a valid <Password>
    And I click in "Sign in"
    Then system decripty my wallet information local storage
    And I should see dashboard page

  Scenario: Sign in with a invalid password
    Given I am at wallet Sign in page
    When I fill  a invalid <Password>
    And I click in "Sign in"
    Then  should see "Incorrect Password"

```