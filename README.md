# **VeChain “CrowdSale” dApp Overview**

## About CrowdSale:
CrowdSale is a decentralized marketplace for users to make online purchases of non-physical products. Being decentralized, CrowdSale records all transaction history on the **VeChain** blockchain network. Cryptocurrency is used for transfer of funds, without the hassle of credit cards.

CrowdSale’s vision is to be the go-to marketplace for online assets sales. It is able to onboard products from many categories, including media, software keys, e-books, news, freelance services, and many more.

**Features of CrowdSale:**
CrowdSale is a beautifully designed marketplace that provides the option to sell and also to auction products. On CrowdSale, users can easily view all buy and bid history for each product recorded securely on blockchain and make trusted decisions.

In the near future, CrowdSale will take advantage of VeChain's multi-party-payment system to allow either buyer/seller to pay the transaction fees.

**CrowdSale’s Seller Traceability:**
You can see a Seller’s history easily with the assurance that it has not been doctored. Furthermore, all sellers must first be approved by the CrowdSale Admin before they can begin selling their products. This adds an additional layer of confidence for the user.

**CrowdSale’s Auction Feature:**
The auction seller puts up "x" number of his/her product for sale. Bidders bid for the particular product, and each bid is recorded on the blockchain. Take note that when submitting a bid, the bidder will need to pay the respective number of tokens. When the number of bids equals or exceeds the total number of products available, the seller has the option to finish the Auction. Upon the seller's finish auction confirmation, CrowdSale will send the blockchain tokens of the successful bidders over to the seller, and return the blockchain tokens of the failed bidders back to them.

## Technology Summary of CrowdSale:
This app is for crowd sale with both sale and auction functions leveraging VeChain blockchain.

The app consists of a Web App, APIs and Smart contracts. The Web App is implemented using Vue.JS framework, APIs are RESTful APIs using Node.js which integrates with smart contracts using VeChain APIs. The smart contracts are written using Solidity.

The Web App and APIs will be hosted on a trusted platform or a hosting platform, such as Morpheuslabs BPaaS, GoDaddy, and the smart contracts will be running on VeChain MainNet.

All amount, price and bids referred in this App is based on the blockchain native token. (VET in this case)

### Core Technology Stacks

#### Vue.JS frontend
* Vue, Vuex, Vue Router
* Vuetify Material Component Framework
* Firebase web application development platform (User authentication and authorization)

#### Middle Client API
* Connex 

#### Backend Smart Contracts and Blockchain Technology
* Solidity
* Truffle Framework v4.1.15
* VeChain web3-gear
* VeChain Thor
* VeChain Sync Browser

### Technical Features of CrowdSale
CrowdSale smart contracts are written in Solidity and deployed on VeChain as backend infarstructure. And front applications can use Connex Client to interact with the smart contracts.

CrowdSale dApp supports two kinds of sales for now: normal sale and auction sale. In near future, more functions will be added.

The followings are the main functions provided by the CrowdSale smart contracts (refer to ABI for detailed spec of smart contract functions).
* registerSeller: register a seller to be able to sell products on dApp
* getSellers: return list of sellers
* getAllProductList: get a list of all products
* getProductListOfSeller: get list of products of one seller
* createNewProduct: create a new product for sale (it requires seller permission)
* getBuyRequests: get all the buying requests of a product
* finishSale: finish sale of a product, then users are not able to buy the project any more, and tokens are released to the seller.
* createAuctionProduct: create an auction product
* getListBiders: get the list of all bidders
* finishAuction: settle auction sale, tokens will be refunded to people who did not win the auction.


## UI/UX Features and Walkthrough

Refer to the details in "CrowdSaleReadme.pdf".

## Customize and Deploy CrowdSale dApp on Morpheus Labs BPaaS

The CrowdSaleApp has been be published into the Application Library on ML BPaaS. Developers can use the application as a reference and leverage the platform to quickly build and test VeChain dApps.

1.  Download CrowdSaleApp application from the Application Library. Deploy the application into a new workspace. Then start and open the workspace. Then you can use CDE to modify and test the application. Note that you can create a VeChain Solo node from Bloclchain Ops on ML BPaaS.
2.  Open new terminal, go to the project folder `cd /projects/CrowdSaleApp`
3.  Start web3-gear `web3-gear --endpoint {vechain internal network url}` (internal URL of the Solo node if you are using the Solo node on ML BPaaS)
4.  Open another new terminal, go to vechain-backend folder `cd /projects/CrowdSaleApp/vechain-backend` and deploy contracts to network `truffle migrate` or `truffle migrate --reset` if you want to redeployed again.
5.  In the CDE, Get CrowdSaleFactory contract address and update it to "address" variable in `public/client/CrowdSaleFactory.js` file (example `CrowdSaleFactory: 0x855eb86c45d79f8899ad100b0f32633d2882e8bd`)
6.  Go to the project root folder `cd ..` and run install node modules `npm install`
7.  Run node app `npm run serve`
8. VeChain Sync Browser (https://electronjs.org/apps/vechain-sync) to install, run and sign transaction.The Sync browser contains connex APIs that are used to invoke smart contracts on the VeChain network.
9. Configure the end point in the Sync wallet to the target network, e.g. testnet, mainnet, or the solo node on the ML BPaaS platform. You should use the external URL of the Solo node when you configure the custom end point to connect to the solo node. Refer to the ML BPaaS document to see how to find out internal and external URL of the Solo node : https://docs.morpheuslabs.io/docs/blockchain-networks.
10. The CrowdSaleApp application will be launched in the Sync browser. Refer to the "CrowdSaleReadme.pdf" for the functions provided in the application.

## About the Author

This application is designed and developed by Bruce Wen who is a super intern in Morpheus Labs and Duong Van Sang who is a senior Blockchain specialist and developer with Morpheus Labs. Great thanks for their contribution!

