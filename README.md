# Module 11 - Beginner Lab: Ethereum Pet Shop DApp Case Study

## Background
After having gone through the [Ethereum Pet Shop Truffle tutorial][pet-shop-tutorial] (1 hour), we will take a closer look at the data flow in the Ethereum Pet Shop DApp.

## Meta Information
| Attribute | Explanation |
| - | - |
| Summary | A case study examining the data flow in the operation of a simple DApp |
| Topics | Ethereum, DApps, blockchains, transactions, and web3. |
| Audience | CS1 or later. |
| Difficulty | Beginner. |
| Strengths | Looks at the use of blockchain technology in a simple, decentralized application. |
| Weaknesses | Relies on separate tutorial having been successfully completed. |
| Dependencies | Truffle, Ganache, MetaMask, and a computer with suitable browser (Chrome, Firefox, etc.). |
| Variants | No. |

## Assignment Instructions
1. Reset everything.
    * Open your browser with MetaMask installed.
    * Click the **MetaMask icon**.
    * Click on the **account icon** in the top-right corner.
    * Click **Log out**.	![metamask_account_logout](screenshots/connecting_to_metamask/metamask_account_logout.PNG)
    * Close your browser.
    * Launch the Ganache GUI.
    * Click the **gear icon** in the top-right corner.
    * Select the **ACCOUNTS & KEYS** tab.
    * Enable **AUTOGENERATE HD MNEMONIC**.
	![enable autogenerate HD](screenshots/connecting_to_metamask/enable_autogenerate_HD_mnemonic.PNG)
    * Click **SAVE AND RESTART** in the top-right corner.
	![save and restart](screenshots/connecting_to_metamask/save_and_restart_ganache.PNG)
    * Click the **gear icon** in the top-right corner.
	![ganache_restart_settings](screenshots/connecting_to_metamask/ganache_restart_settings.PNG)
    * Select the **ACCOUNTS & KEYS** tab.
    * Disable **AUTOGENERATE HD MNEMONIC**.
	![disable autogenerate HD](screenshots/connecting_to_metamask/disable_autogenerate_and_restart.PNG)
    * Click **SAVE AND RESTART** in the top-right corner.
	![save and restart](screenshots/connecting_to_metamask/save_and_restart_ganache.PNG)
    * Open a Git Bash prompt.
    * Change directory into the pet-shop-tutorial folder.
    * Run `truffle networks --clean`.
	![truffle clean](screenshots/connecting_to_metamask/truffle_clean.PNG)
2. Make initial observations.
    * Select the **ACCOUNTS** tab.
    * Observe that all accounts have 100.00 ETH.
	![accounts](screenshots/clean_blockchain_screenshots/accounts.PNG)
    * Switch to the **BLOCKS** tab.
    * Observe the newly created genesis block.
	![block0](screenshots/clean_blockchain_screenshots/block0.PNG)
    * Switch to the **TRANSACTIONS** tab.
    * Observe that there are no transactions.
	![transactions](screenshots/clean_blockchain_screenshots/no_transactions.PNG)
3. Initialize the pet shop DApp.
    * Open a Git Bash prompt.
    * Change directory into the pet-shop-tutorial folder.
    * Run `truffle migrate`.
	![truffle migrate](screenshots/setup_commands_screenshots/truffle_migrate.PNG)
4. Observe the output.
    * Switch window back to the Ganache GUI and select the **ACCOUNTS** tab.
    * Observe that the first account balance has changed.
	![accounts changed](screenshots/setup_commands_screenshots/accounts_after_migrate.PNG)
    * Switch to the **BLOCKS** tab.
    * Observe 4 newly created blocks.
	![blocks changed](screenshots/setup_commands_screenshots/blocks_after_migrate.PNG)
    * Switch to the **TRANSACTIONS** tab.
    * Observe the 4 new transactions.
	![transactions changed](screenshots/setup_commands_screenshots/transactions_after_migrate.PNG)
5. Run the pet shop DApp
    * Switch back to the Git Bash prompt.
    * Run `npm run dev`.
	![npm run dev](screenshots/setup_commands_screenshots/npm_run.PNG)
    * A new tab in your browser should open displaying the pet shop.
6. Sign in to MetaMask using the mnemonic phrase in Ganache.
    * In MetaMask, click **Import using account seed phrase**.
	![metamask](screenshots/connecting_to_metamask/login.PNG)
    * Switch to the Ganache GUI.
    * Select and copy (`CTRL+C`) the **MNEMONIC** phrase.
    * Switch back to your browser and paste (`CTRL+V`) the phrase into the _Wallet Seed_ box in MetaMask.
    * Create and confirm a new password in MetaMask.
	![import using ganache](screenshots/connecting_to_metamask/wallet_mnemonic.PNG)
7. Confirm the connection to Pete's Pet Shop.  
	![connection_request](screenshots/connecting_to_metamask/connection_request.PNG)
8. Adopt a dog.
    * Choose a dog, and click **Adopt**.
    * In the MetaMask pop-up, click **Confirm**.
        * If all went well, `Adopt` will have changed to `Success`.
	![Adopting a dog](screenshots/connecting_to_metamask/adoption_dialog.PNG)
9. Observe the output.
    * Switch to the Ganache GUI.
    * Select the **BLOCKS** tab.
    * Observe 1 newly created block.
	![6 blocks](screenshots/connecting_to_metamask/six_blocks.PNG)
    * Select the **TRANSACTIONS** tab.
    * Observe the new `CONTRACT CALL` transaction, which brings the count to 5.
	![5 transactions](screenshots/connecting_to_metamask/five_transactions.PNG)

## Questions
1. Why do we run `truffle migrate`?
    * It deploys the smart contracts, which are the backend of the DApp.
2. Why are we using Ganache instead of the Ethereum Main Network?
    * Ganache creates a local blockchain, which is free and doesn’t require interacting with a test-currency faucet.

## Credits
Dr. Debasis Bhattacharya  
Mario Canul  
Saxon Knight  
https://www.trufflesuite.com/tutorials/pet-shop  

[pet-shop-tutorial]: https://www.trufflesuite.com/tutorials/pet-shop
