# auroraCacao

Developing proof of distribution chain for positive products

## Components
* Web Application
  * MVP may be on cloudAsAService RAD, or on SvelteKit? or a mix maybe
  * Delivered Application... SvelteKit?
* OpenDataKit
  * Central Server, with API
  * Bridge into API from Web Application
* Data Analysis and Visualisation
  * Tableu based?
    * ODK's OData ouptut is specifically tested with Tableu
      * https://odkcentral.docs.apiary.io/#reference/odata-endpoints
    * Tableu has a WebComponent widget, as well as Javascript or embed options
      * https://help.tableau.com/current/api/embedding_api/en-us/docs/embedding_api_basic.html
    * this needs further research to see if it applies to our usecase
      *  Can tableu create like ... search forms and stuff like that over data set?
* Blockchain Provenance/Chain of Custody
  * Fundamentally will be looking to create an NFT to represent each ODK Submission, linked through to an IPFS metadata. 
    * There are metadata standards for NFTs
      * OpenSea supports these two metadata standards EIPs:
        * https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md
        * https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1155.md#erc-1155-metadata-uri-json-schema
    * Probably we will roll out on top of these standards, its possible that we may add or alter depending on target spaces.
  * Currently using the Tatum open source SDK to interface with the Celo Blockchain.
    * This is an open source tooling that provides nice API abstractions for multiple blockchains.
    * Their paid service includes free IPFS pinning, which might work well for us. It is a dependency, but it is one that could easily be changed
  * Potentially could use Cosmos Contract SDK. There doesnt seem to be much difference.
  * For storing NFT metadata the options are
    * IPFS
      * Various options on IPFS
        * Set up a set of robhust pinning servers, including
          * One run by GE
          * One run by Aurora
          * Perhaps one run by a university in Columbia
          * Perhaps a paid service to provide easy robustness for money, and/or CDN edges (cloudflare might offer a free CDN gateway for IPFS already??)
    * FileCoin
