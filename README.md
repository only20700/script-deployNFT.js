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
