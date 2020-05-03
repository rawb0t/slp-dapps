# SLP D-App Registries

This repository contains specifications for d-apps that utilize SLP and instructions for how to design and register your own SLP d-app for public discovery and interoperability purposes.  

Registration with a registry is obviously optional, but it will provide a way for the SLP community to see what d-apps are available and which specification the D-App is using.  Registration involves creating a pull request to this repository to add your spec to the `dapp-specs` directory.

Once your d-app spec is accepted, a maintainer from one of the d-app registries will issue you a token which will serve as a unique idenitifier for your specific d-app implementation.  Thereafter, when you create new tokens for your d-app implementation you will include this unique ID in the document hash of your token genesis.

As mentioned above, each d-app using SLP should have a standalone specification so that anyone who wants to interact or interoperate with that particular d-app can do so.  It is up to the d-app creator to determine whether or not to allow others to interoperate with their d-app permissionlessly.

Any d-app with a spec can be implemented one or more times, and registered one or more times.  Ideally, the d-app should only be registered one time per domain name per registry.

Once you receive your d-app registry token each registry maintainer can use that token to allow you gain access to the special d-app specific sections of the registry website for you to update and provide information to your users.

## Registries

Registries are a simple way for you to publicly let everyone know that you have implemented a d-app that is following a certain d-app specification.  D-app site owners will hold an NFT from one or more d-app registries.  The token will simply have `name=<YOUR DAPP URL>` and `documentUrl=<RELATIVE SPEC FILENAME>` encoded within an NFT GENESIS.  D-app owners will use these tokens to (1) provide linkage to the d-app's specification, (2) login to the registry website(s) to make public announcements regarding the d-app, and (3) to prove to users that other token IDs has originated with the real owner of a d-app implementation.

Let's walk through each of these purposes

### 1. Linkage to d-app specification

A d-app may function using one or more tokens held by its users.  The functionality of a d-app is specific to the d-app specification.  So when a d-app owner, or possibly a user, wants to create a new token for working with a specific d-app, the new token's GENESIS will contain `documentHash=<DAPP NFT ID>`.  The d-app implementation may decide whether or not to accept a token that was created by anyone (see 3 below).

### 2. Login to the registry website(s)

D-App owners may want to provide up to date information about their app.  The token provided by a registry owner can be used as a way to authenticate with the registry website so app specific updates can be made.

### 3. Proof of d-app ownership

A third purpose for the registry token will serve in some situations to prove whether or not a new token was created by a d-app owner.  This may come in handy in a number of circumstances, but two come to mind.  The first reason may be that a d-app may only want to allow authentic tokens to interact with the d-app implementation, and not allow just anyone to create a token that is working on the d-app's website.  The second reason may be for the purpose of resale of a specific token associated with a d-app, and making sure that the token was indeed created by the d-app owner and will be honored.  Proving token authenticity is trivial is simple requires checking that the token GENESIS was sent to the same address holding the registry token at the time of Genesis.

## Registry Requirements

1. Registry owners shall create one or more unique NFT1 Groups for the purpose of issuing d-app owners their d-app implementation tokens using the following form:
```
    ticker: '<any string>'
    name: (optional)
    doc url: '<registry website URI (including https:// or other protocol)>'
    doc hash: (empty)
    Initial issuance: <any quantity>
    Initial issuance type: fixed OR flexible supply
```

2. After a d-app specification is accecpted, registry owners may issue d-app owners a child NFT from any of their registry groups in the following form:
```
    ticker: (empty)
    name: '<dapp URL>'
    doc url: '<SPEC FILENAME>'
    doc hash: (empty)
```

3. Burned D-App NFTs can optionally be not displayed on a registry website.

4. Ecosystem d-app registries are listed in `registries.json`, 
