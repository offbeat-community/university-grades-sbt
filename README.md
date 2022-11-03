![OffBeat logo](media/.github/logo-banner.png)

This repository includes the specifications for developing the take-home project `University Grades SBT` by [OffBeat](https://offbeat.community).

------------------

# Instructions
- Fork this repository on your own Github profile
- Follow the project [specifications](Specifications) 
- Is up to you to accomodate this `README.md` to your result repository

# Project
This project would require you to build an application capable of minting an SBT of a university grade. To make it clear; Your application will permit to login a user with it's wallet, choose the university her/his in, fill a form with its personal information and, with a secret key, he'll be able to mint it's degree SBT to her/his wallet.  
The specifications are organized by application screens, each one with its designes and functionalities

## Specifications

You have on [this Figma](https://www.figma.com/file/YwteE14GzkoCSYXvw4CGXT/University-Grades-SBT) all the details of the screens designs. Have in mind that one thing that we check is the ability of developing precisely upon design specifications.


1. Login with your wallet
  <img src="media/Screens/login.jpg" height=400, width=600>

  For this step, you can use industry-standard tools like [MetaMask](https://metamask.io) or [WalletConnect](https://walletconnect.com/).  
  Keep in mind that if a user already minted its grade, the next time he logs in, he'll be redirected directly to the success page

2. Choose your university
  <img src="media/Screens/choose-university.jpg" height=400, width=600>  
  
  The user will be able to choose between different universities that are **provided from the backend** each one with a unique secret key that will permit later minting degrees SBTs. You will be responsible of generating this universities on the DB, but we recommend to atleast generate 10. Feel free of searching the university pictures on the internet.  
  Have in count that there can be numerous universities so the endpoint that provides them should have in count some sort of pagination to avoid serializing enourmous quantities of data.  

3. Fill your personal information
  <img src="media/Screens/fill-information.jpg" height=400, width=600> 

  The user will be able to fill its personal information to later customize the SBT metadata. The grades will be a dropdown of the different grades available **provided by the backend** (the grades are not related to a university).  

4. Minting page
  <img src="media/Screens/mint.jpg" height=400, width=600> 
  In this page the SBT will be previewed and it will be prompted an input to send the university secret key. Until the user do not prompt the correct secret key, the minting button will be disabled and he will not mint the SBT.
  We are aware that the secret key will be unique per university, and everyone who could have the secret key is gonna be able to mint as much degrees as she/he wants to, but since this is just a sample project, security is irrelevant.
  
  Since the SouldBound Token (SBT) is still a concept in development (proposed by [Vitalik Buterin](https://vitalik.ca/general/2022/01/26/soulbound.html) in this post) and it doesn't have any official ERC standard implementation. We refeer to an SBT as `any token non-transerrable once minted`. The implementation of this restriction is totally up to you.  
  The SBT will have a custom metadata based on the User preferences as the following:

  ```json
  {
    "image": "<the-url-of:media/SBT Image/SBT University image.png uploaded>"
    "name": "Your university degree"
    "description": "This SBT is a validation of your university degree"
    "attributes": [
      {
        "trait_type": "Degree",
        "value": "<user degree>"
      },
      {
        "trait_type": "Name",
        "value": "<user name>"
      },
      {
        "trait_type": "Last name",
        "value": "<user last name>"
      }
    ]
  }
  ```
  
  If the selected network is not `Mumbai`, an error popup will appear:
    
  <img src="media/Screens/error-popup.jpg" height=400, width=600>  
  
5. Success page
  <img src="media/Screens/sbt-success.jpg" height=400, width=600> 

  The success page will show the minted SBT with a redirection link to the SBT on [OpenSea](https://opensea.io/).
  

And that's it! 🔥  
We hope for you to have fun with it ❤️

-------------------
  
This repository should store all the information you need to develop the project, but if you have any blockers, don't hesitate to ask us on: info@offbeat.com.
