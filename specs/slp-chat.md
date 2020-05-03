# SLP Chat

SLP chat is a d-app protocol that allows users to create chat groups, the creator of a chat group controls who can join the group.

Each chat group is represented by an NFT1 Group token.  The implementer of this specification can decide on who is allowed to create new chat group tokens.

Details of message transport and use of encryption are left to the specific d-app implementation and have no association with the token GENESIS data.

## Specification

Each chat group token shall be created as an NFT1 Group token using the following GENESIS form:
```
    ticker: '<ANY STRING>' (optional)
    name: '<ANY STRING>'   (optional)
    doc url: '<registry website URI (including https:// or other protocol)>'
    doc hash: '<SLP-CHAT REGISTRY NFT ID>'
    Initial issuance: <any quantity>
    Initial issuance type: fixed OR flexible supply
```

Chat group users shall be represented by the holder of an NFT created from a chat group.  The user's NFT GENESIS shall have the following form:

```
    ticker: '<ANY STRING>' (optional)
    name: '<ANY STRING>'   (optional)
    doc url: '<for message transport resolution>' (e.g., IPNS peer ID multi-hash)
```

The document URL should be specified by the specific d-app implementation.
