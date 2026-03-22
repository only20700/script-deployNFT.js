# script-deployNFT.js
script/deployNFT.js
const { ethers } = require("hardhat");

async function main() {
  console.log("Deploying NFT contract...");

  const NFT = await ethers.getContractFactory("MyNFT");
  const nft = await NFT.deploy();

  await nft.waitForDeployment();

  console.log("NFT deployed to:", await nft.getAddress());
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
## Deploy NFT

Run the following command to deploy the NFT contract:

```bash
npx hardhat run script/deployNFT.js --network base


---

bash
git add .
git commit -m "feat: add NFT deployment script for Base network"
git push origin main
