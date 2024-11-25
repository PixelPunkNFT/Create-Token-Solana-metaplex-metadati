# Solana Token Creation with Metaplex

## Project Description
Create custom SPL tokens on Solana blockchain with Metaplex metadata using TypeScript. This project provides a comprehensive solution for token generation and metadata management.

## Key Features
- SPL Token creation
- Metaplex metadata integration
- TypeScript implementation
- Solana blockchain deployment

## Setup dependencies
```bash
npm install 
```

## Run
we will make a token  account

```bash
solana-keygen grind --starts-with bos:1 
```
```bash
solana config set --keypair wallet-generate.json
```

Let's create one more address that we will use for our Mint Account - the factory that makes our specific token. We'll make it start with mnt to help us remember it's the token mint account.

It will save a new keypair named after the public key: mntTymSqMU4e1NEDdxJ9XoPN4MitCgQ7xxGW6AuRAWQ.json

```bash
solana-keygen grind --starts-with mnt:1
```

We will use our mnt... address as the token mint account for our new token:

```bash
spl-token create-token --program-id TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb --enable-metadata MINT-WALLET.json
```
## We created a wallet account address, a mint address, and minted the token without metadata. The next step will be to upload the metadata using Metaplex.

## Metadata JSON Structure
```json
{
  "name": "Token Name",
  "symbol": "TOKEN",
  "description": "Token description",
  "image": "https://example.com/token-image.png"
}
```
Set up the `mpl_metadata.ts` file with the two created addresses, set the metadata, and we are almost done.


```bash
ts-node .\mpl_metadata.ts
```
