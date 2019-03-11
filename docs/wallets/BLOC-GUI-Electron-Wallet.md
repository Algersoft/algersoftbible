# **Kriegerrand Electron Wallet for Desktop**

[Kriegerrand Electron GUI Wallet](https://github.com/furiousteam/KREGR-electron-wallet) - GUI Stands for Graphical User Interface. It makes it easy for you to use Kriegerrand with a friendly user interface. The Kriegerrand Electron Wallet client allow you to create your wallet, store and send your [Kriegerrand money](https://bloc.money), view your transactions and much more. Kriegerrand Electron GUI Wallet is available for Windows, macOS and linux desktop and laptop computers.

## **Screenshot**

![Kriegerrand Electron Wallet - Welcome screen](images/KREGR-gui-wallet/V3/welcome.png)

**Notes**

Kriegerrand Electron Wallet relies on KREGR-service to manage wallet container & rpc communication.

Release installer & packaged archived includes a ready to use KREGR-service binary, which is unmodified copy Kriegerrand release archive.

If you don't trust the bundled KREGR-service file, you can download and use the binary from official Kriegerrand release, which is available here: https://github.com/furiousteam/BLOC/releases or compile it yourself. Then, make sure to update your KREGR-service path setting.

## **Source Code**

* [Kriegerrand Electron Wallet on GitHub](https://github.com/furiousteam/KREGR-electron-wallet)

## **Download**

You can download the Kriegerrand Electron Wallet from two places

* Kriegerrand Electron Wallet from [GitHub](https://github.com/furiousteam/KREGR-electron-wallet/releases)
* Kriegerrand Electron Wallet from [BLOC.MONEY](https://bloc.money/download)

Once you have downloaded the file, go to your computer and double click the installation package to install the Kriegerrand wallet.
Select the Kriegerrand wallet application and put in where you like

## **Lanch the app**

#### Windows:

1. Download the latest installer here: https://github.com/furiousteam/KREGR-electron-wallet/releases
2. Run the installer (KREGR-Electron-Wallet-<version>-win-setup.exe) and follow the installation wizard.
3. Run as Administrator KREGR-Electron-Wallet via start menu or desktop shortcut. (right click on the app icon and select run as Administrator)

#### GNU/Linux (AppImage):

1. Download latest AppImage bundle here: https://github.com/furiousteam/KREGR-electron-wallet/releases
2. Make it executable, either via GUI file manager or command line, e.g. `chmod +x KREGR-Electron-Wallet-<version>-linux.AppImage`
3. Run/execute the file, double click in file manager, or run via shell/command line.

See: https://docs.appimage.org/user-guide/run-appimages.html

#### macOS

1. Download latest archive here: https://github.com/furiousteam/KREGR-electron-wallet/releases
2. Extract downloaded zip archived into your home folder
3. Open terminal and Run: `cd /Users/YOURNAME/KREGR-Electron-Wallet.app/Contents/MacOS && ./KREGR-Electron-Wallet`


## **Settings**

![Kriegerrand Electron Wallet](images/KREGR-gui-wallet/V3/settings.png)

The settings screen will appear the 1st time you are launching the Kriegerrand Electron Wallet. On first launch, Kriegerrand Electron Wallet will try to detect location/path of bundled KREGR-service binary, but if it's failed, you can manually set path to the KREGR-service binary on the Settings screen.

If you are happy to use the bundled KREGR-service simply click the `SAVE` button.

## **Welcome Screen**

![Kriegerrand Electron Wallet - Welcome screen](images/KREGR-gui-wallet/V3/welcome.png)

Welcome to your Kriegerrand wallet. There is 4 differents options available.

1. Create new wallet
2. Open an existing wallet already created by the Kriegerrand Electron Wallet Client
3. Import private keys to restore a wallet
4. Import Mnemonic seed words to restore a wallet

## **1. Create new wallet**<a name="create-wallet"></a>

![Kriegerrand Electron Wallet - Create a new wallet](images/KREGR-gui-wallet/V3/create-a-new-wallet.png)

If this is your 1st time using Kriegerrand or you just need to create a new wallet use this option.

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Click the button `CREATE A NEW Kriegerrand WALLET`
4. Wallet file is saved with the following extension: `yourwallet.money`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/KREGR-GUI-Electron-Wallet.md#open-wallet).

## **2. Open an existing wallet file .money**<a name="open-wallet"></a>

Kriegerrand Electron Wallet require a connection to a Kriegerrand node to be able to work. We have two possibilities:

![Kriegerrand Electron Wallet - Open an existing wallet file .money](images/KREGR-gui-wallet/V3/OPEN-a-wallet.png)

1. Create your own node - Download and start BLOCd on your machine locally or remotely then connect to it with Kriegerrand Electron Wallet.
2. Use a public remote Kriegerrand node and do not bother with the tech. Select your favorite Kriegerrand public node and connect to it.

*Note:* Public remote node may charge extra fees per transaction.

Find out more about [Kriegerrand remote nodes](../wallets/Using-remote-nodes.md) and how you could make extra passive income.

1. Click on the folder icon to open your system explorer and select your wallet file `(.money)`
2. Type the password for this wallet
3. Type hostname or IP address of the Kriegerrand daemon or public node to connect to*
4. Enter RPC port number of the Kriegerrand daemon or public node
5. Click the button `OPEN THE WALLET`

* To use a local Kriegerrand node running on the same machine as the Kriegerrand Electron wallet enter `127.0.0.1` as Daemon address with RPC Port: `2086`

![Kriegerrand Electron Wallet - Open an existing wallet file .money](images/KREGR-gui-wallet/V3/opening-wallet.png)

* if you are using Kriegerrand public remote node, you might get a notification displaying the node fee price.

![Kriegerrand Electron Wallet - Public Node Fee notification](images/KREGR-gui-wallet/V3/node-fee-notification.png)

You are now ready to use your wallet. Please follow the next instructions on how to use your wallet.

## **3. Import Private Keys to restore a wallet**<a name="import-private-keys"></a>

If you already have Kriegerrand wallet address you can import your private keys using this method.

If you were using the previous Kriegerrand Wallet v2.0.2 you can checkout [this guide to find out how to export your wallet private keys](../wallets/KREGR-GUI-Desktop-Wallet-V2.md#1-export-key-best-solution) and follow this procedure to restore your wallet:

This will restore your wallet address, funds present on it but also the complete history of your transactions. All you need is your private view key & spend key.

![Kriegerrand Electron Wallet - Import private keys to restore a wallet](images/KREGR-gui-wallet/V3/import-private-keys.png)

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Select the block number from where to start scanning the blockchain for transactions contains into your wallet.
4. Enter the private view key of the wallet to be imported
5. Enter the private spend key of the wallet to be imported
6. Click the button `IMPORT PRIVATE KEYS AND RESTORE THE WALLET`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/KREGR-GUI-Electron-Wallet.md#open-wallet).

## **4. Import Mnemonic seed words to restore a wallet**<a name="import-mnemonic-seed"></a>

If you already have Kriegerrand wallet created since the Kriegerrand V3.0 you should already have a Mnemonic seed. You can import it using this method.

This will restore your wallet address, funds present on it but also the complete history of your transactions. All you need is your Mnemonic seed words list.

![Kriegerrand Electron Wallet - Import Mnemonic seed to restore a wallet](images/KREGR-gui-wallet/V3/import-Mnemonic-seed.png)

1. Select where the wallet file will be stored. Click on the folder icon, choose where you woud like to save your wallet, enter the name of the file and click save.
2. Set the required password to open this wallet file
3. Select the block number from where to start scanning the blockchain for transactions contains into your wallet.
4. Enter the Mnemonic seed words of the wallet to be imported
5. Click the button `IMPORT MNEMONIC SEED AND RESTORE THE WALLET`

You should see a message: Wallet has been imported. You can now [open the wallet](../wallets/KREGR-GUI-Electron-Wallet.md#open-wallet).


## **Wallet Overview**

We will have to wait for the wallet synchronisation to finish in order to use the wallet.

![Kriegerrand Electron Wallet - Wallet Overview](images/KREGR-gui-wallet/V3/wallet-overview.png)

The overview display all the important informations about your wallet such as:

1. `Balance` (Available and Locked)
2. `Status` gives you the synchronisation state of the wallet. (The 1st number is the actual block synched to this wallet and the second number is last known top block on the network)
3. `Connected To` display the current node you are connected to use your wallet
4. `Node fee` shows the fee amount used by this node for each transaction.
5. `Your wallet address` that can be shared to your customers/friends so they can pay you
6. `QR Code` makes it even easier to share your Kriegerrand address. Scan to share.


## **Send KREGR**

Send/Transfer BLOC.MONEY to any other Kriegerrand wallet address.

![Kriegerrand Electron Wallet - Send KREGR](images/KREGR-gui-wallet/V3/send-bloc.png)

1. Type the amount you would like to send
2. Enter the recipient address
3. The fees are set automatically to 0.0001 BLOC
1. You can enter a payement ID if you have one, it must contain 64 caracters
5. Once you are ready click. `PROCEED Kriegerrand PAYMENT`


## **Transactions**

Transactions list all incomming and outgoing transactions from this wallet.

![Kriegerrand Electron Wallet - Transactions](images/KREGR-gui-wallet/V3/transactions.png)

The BLOCK Explorer shows you blocks details from the blockchain including the transaction that it contains.

![Kriegerrand Electron Wallet - Transactions](images/KREGR-gui-wallet/V3/transaction-details.png)