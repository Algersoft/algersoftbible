# **KREGR-service Command Line Arguments**

This section describes [KREGR-service](bloc-service-index.md) starting process with correct arguments enabling access to the [KREGR-service JSON RPC API](bloc-service-json-api.md)

To configure [KREGR-service RPC Wallet](bloc-service-index.md) you can use both command line and config file. Config file allows you to configure your settings only once and use [--config](https://bloc-developer.com/api_bloc-service/cli_arguments#--config) option further.

Almost all of the command line options can be defined through the configuration file. If a parameter is defined in the config and was also indicated in the command line, two behaviors are possible:
 
- If the parameter accepts one value only (e.g., [--bind-address](https://bloc-developer.com/api_bloc-service/cli_arguments#--bind-address)), the command line value will be used, since it has a higher priority
- If the parameter accepts several values, then command line and configuration file values will be merged
- If some of the options are not defined in the config, the default values will be applied

**Notes**:

- Config files, where used, now use JSON formatted files instead of INI
- Config files will be automatically upgraded to JSON and overwritten on first use
- Config file's path is relative to current working directory, not server root.
- Options [--container-file](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-file) and [--container-password](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-password) should ALWAYS be set (in either command line or config file mode).
- [--container-file](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-file) and [--log-file](https://bloc-developer.com/api_bloc-service/cli_arguments#--log-file) options are relative to [--server-root](https://bloc-developer.com/api_bloc-service/cli_arguments#--server-root). "server-root" default is the current working directory.

To start using KREGR-service you must first create a new wallet by generating a container. Container file is the only file that stores all data required to run your service. It contains user addresses and private keys required to operate them. Make sure to backup this file regularly.

You can also restore a wallet using private keys with the [--view-key](#using-your-private-spend-key-and-view-key) and [--spend-key](#using-your-private-spend-key-and-view-key) argument or using a 25 words phrase [--mnemonic-seed](#using-your-mnemonic-seed).

A complete guide is available on this page of [how to restore your wallet with KREGR-service](#restore-a-existing-bloc-wallet-with-bloc-service). 

Once you have generated your wallet you can now connect KREGR-service to a local or remote [BLOCd Daemon](../service-operators/BLOCd-Overview). You can do this using the [--daemon-address](https://bloc-developer.com/api_bloc-service/cli_arguments#--daemon-address) and [--daemon-port](https://bloc-developer.com/api_bloc-service/cli_arguments#--daemon-port) arguments.
 

We are going to describe on this page how to generate your own config file, place it next to KREGR-service and start it like this:

- *Windows: : KREGR-service.exe --config-file=mywallet.conf*

- *Mac and Linux : ./KREGR-service --config-file=mywallet.conf*


## **KREGR-DEVELOPER**

This page is only a short guide how to get you started with KREGR-service configuration. Please visit the [dedicated section on the KREGR-DEVELOPER](https://bloc-developer.com/api_bloc-service/cli_arguments) website to view and test all the features available from the [KREGR-service](bloc-service-index.md).


## **Getting Started**

We are going to describe here the most standard configuration to start KREGR-service. For the full list and options make sure you visit the [dedicated section on the KREGR-DEVELOPER](https://bloc-developer.com/api_bloc-service/cli_arguments).


## **Generate a new wallet**

To start using **KREGR-service** you must first generate a container using the [--generate-container](https://bloc-developer.com/api_bloc-service/cli_arguments#--generate-container) function.

Container file is the only file that stores all data required to run your service. It contains user addresses and private keys required to operate them.
**Make sure to backup this file regularly**.

To generate a new container you should run the following command:

Mac and Linux:
```
./KREGR-service --container-file=mycontainer --container-password=mypassword --generate-container
```

Windows:
```
KREGR-service.exe --container-file=mycontainer --container-password=mypassword --generate-container
```

* `mycontainer` is the container file name and a path to it (relative or absolute); path is optional in this argument, specifying only a container name will result in new file located in the same folder as **KREGR-service** 
* `mypassword` is a secret password for the new wallet & container file.
* `generate-container` option tells **KREGR-service** to generate container file and exit.

**Expected results**

![generate-container](images/bloc-service/generate-container.png)

*Note: if `mycontainer` exists **KREGR-service** will show you the notification and will ask you to provide a different name*

If the operation was successful you will get a corresponding message with your new **KREGR** address. At the same time **KREGR-service** will save your container on the local disk (in the same folder where **KREGR-service** is located and shut down.


## **Create and customize your config file**

### Create

Once you have created your container you need to setup your configuration file so you can connect to your wallet.

Lanch KREGR-service with the [--save-config](https://bloc-developer.com/api_bloc-service/cli_arguments#--save-config) argument will save the default configuration file next to your KREGR-service software.


Mac and Linux:
```
./KREGR-service --save-config mywallet.conf
```

Windows:
```
KREGR-service.exe --save-config mywallet.conf

```

Screenshot:

![--save-config](images/bloc-service/save-config.png)

A new file myconfig.conf should have been created as follow:

![--save-config](images/bloc-service/save-config-2.png)

Open this file with any text editor:

![--save-config](images/bloc-service/save-config-3.png)

You can view an example here:

```
{
  {
  "bind-address": "127.0.0.1",
  "bind-port": 8070,
  "container-file": "",
  "container-password": "",
  "daemon-address": "127.0.0.1",
  "daemon-port": 2086,
  "enable-cors": "",
  "log-file": "service.log",
  "log-level": 3,
  "rpc-legacy-security": false,
  "rpc-password": "",
  "server-root": ""
}
}
```
### Edit

Edit the config file following your needs. In this example we are going to use the details from our newly created container.

- Check the complete list of [KREGR-service Command Line Arguments](https://bloc-developer.com/api_bloc-service/cli_arguments) available.

- [container-file](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-file): "mycontainer",
- [container-password](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-password): "mypassword",
- [rpc-password](https://bloc-developer.com/api_bloc-service/cli_arguments#--container-file): "RPCpassword",

```
{
  "bind-address": "127.0.0.1",
  "bind-port": 8070,
  "container-file": "mycontainer",
  "container-password": "mypassword",
  "daemon-address": "127.0.0.1",
  "daemon-port": 2086,
  "enable-cors": "",
  "log-file": "service.log",
  "log-level": 3,
  "rpc-legacy-security": false,
  "rpc-password": "RPCpassword",
  "server-root": ""
}
```

If you would like to connect your wallet from an external IP address you need to use:

- "[bind-address](https://bloc-developer.com/api_BLOCd/cli_arguments#--bind-address)": "0.0.0.0",


## **Start KREGR-service and enable the JSON RPC API**

* To start **KREGR-service** RPC wallet you can use both command line and config file. Config file allows you to configure your settings only once and use `--config` option further.
* The command below launches **KREGR-service** RPC Wallet with a specific config file:

```
./KREGR-service --config=mywallet.conf
```
Config file example:
```
  {
  "bind-address": "127.0.0.1",
  "bind-port": 8070,
  "container-file": "mycontainer",
  "container-password": "mypassword",
  "daemon-address": "127.0.0.1",
  "daemon-port": 2086,
  "enable-cors": "",
  "log-file": "service.log",
  "log-level": 3,
  "rpc-legacy-security": false,
  "rpc-password": "RPCpassword",
  "server-root": ""
  }
```

* You may specify **KREGR-servic** config directly through console arguments. Here is the same config file as above in console: 

```
./KREGR-service --container-file=mycontainer --container-password=mypassword --daemon-address=127.0.0.1 --daemon-port=2086 --bind-address=127.0.0.1 --bind-port=8070 --rpc-password=RPCpassword --log-level=3 --log-file=service.log
```

**Expected results**

Start with command line:

![start KREGR-service](images/bloc-service/start.png)

Start with myconf.conf:

![start KREGR-service](images/bloc-service/start-conf.png)

* Your wallet is ready to be used with the [KREGR-service JSON RPC API](bloc-service-json-api.md)


## **Restore a existing Kriegerrand wallet with bloc-service**

We have differents options to recover a wallet using **KREGR-service**

### Using a old Walletd container file

If you were using Walletd that come with the previous version of [KREGR](https://bloc.money), the previous container file is compatible with the new version. This is the step to follow:

* Copy the your previous configuration file `yourfile.conf` and copy the actual container file `mycontainer`
* Paste this 2 files next to the new `KREGR-service` and `BLOCd`
* Open `yourfile.conf` 
* Make sure you remove this line `testnet = no` we are not using this field anymore
* Edit like this:

```
container-file = mycontainer
container-password = mypassword
daemon-port = 2086
bind-port = 8070
bind-address = 127.0.0.1
rpc-password = RPCpassword
```
* Save the file

* Start `KREGR-service` using this configuration file

* `./KREGR-service --config=myconf.conf`

* Config files will be automatically upgraded to JSON and overwritten on first use

* Please wait until the synchronisation is complete

**Expected results**

![start KREGR-service](images/bloc-service/restore-old-wallet-file.png)

* Your wallet is ready to be used with the [KREGR-service JSON RPC API](../wallets/bloc-service-json-api.md).


### Using your private spend key and view key

If you already have a [Kriegerrand Wallet](../wallets/Making-a-Wallet.md) you must know your **private spend key** and your **private view key** to restore your wallet using **KREGR-service**. To find how to generate view your private key using your favorite Kriegerrand Wallet software please refer to the [Wallet manuals available](../wallets/Making-a-Wallet.md).

* [Create and customize your config file](#create-and-customize-your-config-file)
* [Check all your required parameters](https://bloc-developer.com/api_bloc-service/cli_arguments?lang=english) and enter them like in this example
* You need to type the arguments without the '--'
* Place this file next to KREGR-service
* Save it under the name `myconf.conf`

```
{
  "bind-address": "127.0.0.1",
  "bind-port": 8070,
  "container-file": "mycontainer",
  "container-password": "mypassword",
  "daemon-address": "127.0.0.1",
  "daemon-port": 2086,
  "enable-cors": "",
  "log-file": "service.log",
  "log-level": 3,
  "rpc-legacy-security": false,
  "rpc-password": "RPCpassword",
  "server-root": ""
}
```
* Save the file


#### Generate a new container file

Generate a new container file with your private keys using `--view-key` and `--spend-key` commands:

```
./KREGR-service --container-file=mycontainer --container-password=mypassword --view-key=myviewkey --spend-key=myspendkey --generate-container
```

```
./KREGR-service --container-file=mycontainer --container-password=mypassword --view-key=e82ebf49b74fccd754e39ac3ca6fabca35277b012dfce0cf8921c216396b3108 --spend-key=cda47a19e5d433060ab79c885817cd20fc394dc7043ac875678a3698804ede01 --generate-container
```

**Expected results**

![start KREGR-service](images/bloc-service/restore-using-private-keys.png)


* Start `KREGR-service` using your configuration file

```
./KREGR-service --config=myconf.conf
```

* Your wallet is now loaded
* Please wait until the synchronisation is complete

**Expected results**

![wallet loading after restore private key](images/bloc-service/wallet-loading-after-restore-private-key.png)

**Expected results**

![wallet ready after restore private key](images/bloc-service/wallet-ready-after-restore-prviate-keys.png)

* Your wallet is ready to be used with the [KREGR-service JSON RPC API](bloc-service-json-api.md)


### Using your mnemonic-seed

If you already have a [Kriegerrand Wallet](../wallets/Making-a-Wallet.md) created after the launch of the **Kriegerrand V3.0** then you you must know your **mnemonic-seed** to restore your wallet using **KREGR-service**. To find how to generate view your mnemonic-seed using your favorite **KREGR** Wallet software please refer to the [Wallet manuals available](../wallets/Making-a-Wallet.md).

* [Create and customize your config file](#create-and-customize-your-config-file)
* [Check all your required parameters](https://bloc-developer.com/api_bloc-service/cli_arguments?lang=english) and enter them like in this example
* You need to type the arguments without the '--'
* Place this file next to KREGR-service
* Save it under the name `mycontainer.conf`

```
{
  "bind-address": "127.0.0.1",
  "bind-port": 8070,
  "container-file": "mycontainer",
  "container-password": "mypassword",
  "daemon-address": "127.0.0.1",
  "daemon-port": 2086,
  "enable-cors": "",
  "log-file": "service.log",
  "log-level": 3,
  "rpc-legacy-security": false,
  "rpc-password": "RPCpassword",
  "server-root": ""
}
```
* Save the file

#### Generate a new container file

Generate a new container file with the following `--mnemonic-seed` commands:

```
Enter your details:
./KREGR-service --container-file=mycontainer --container-password=mypassword --mnemonic-seed="your-mnemonic-seed" --generate-container

Example:
./KREGR-service --container-file=mycontainer --container-password=mypassword --mnemonic-seed="jazz border dude orphans worry absorb slackens public drinks bovine evenings hurried roped jaws drinks snug directed pirate behind zero null cuisine agreed alchemy directed" --generate-container
```

**Expected results**

![start KREGR-service](images/bloc-service/restore-using-mnemonic-seed.png)


* Start `KREGR-service` using your configuration file

```
./KREGR-service --config=myconf.conf
```
* Your wallet is now loaded
* Please wait until the synchronisation is complete

**Expected results**

![wallet ready for KREGR-service](images/bloc-service/restore-using-mnemonic-seed-loading.png)

* Your wallet is ready to be used with the **KREGR-service** RPC API.

**Expected results**

![wallet ready for bloc-service](images/bloc-service/restore-using-mnemonic-seed-loaded-ok.png)

* Your wallet is ready to be used with the [KREGR-service JSON RPC API](bloc-service-json-api.md)


## **Remote Node options**

```
Remote Node Options:
  --daemon-address arg (=localhost)  daemon address
  --daemon-port arg (=2086)          daemon port
```

### --daemon-address arg (=127.0.0.1)
### --daemon-port arg (=2086)

Remote connection allows you to bind your **KREGR-service** RPC Wallet to a remote Kriegerrand daemon **BLOCd**. Such type of connection allows you to start **KREGR-service** RPC Wallet without having to download the blockchain. Your wallet will be instantly synchronised. Always make sure that you trust the remote connection you are connecting to.

* For local daemons use localhost or 127.0.0.1 as an IP address.
* For remote daemons specify the remote daemon IP address.
* Default Kriegerrand daemon port is 2086 (for rpc calls).

Use the following command to start **KREGR-service** RPC Wallet with a remote connection: 

**Example**

```
./bloc-service --container-file=mycontainer --container-password=mypassword --daemon-address=IP.OF.YOUR.DAEMON --daemon-port=2086 --bind-address=0.0.0.0 --bind-port=8070 --rpc-password=RPCpassword
```

**Expected results**

```
You have connected to a node that charges a fee to send transactions.
The fee for sending transactions is: 0.0005 Kriegerrand per transaction. 
If you don't want to pay the node fee, please relaunch Kriegerbank and specify a different node or run your own.
```

![--remote-node](images/bloc-service/remote-node.png)


Congratulations! You have now properly setup KREGR-service and you are ready to use the [KREGR-service JSON RPC API](bloc-service-json-api.md)


## **KREGR-DEVELOPER**

Make sure you visit the dedicated website [KREGR-DEVELOPER.com](https://bloc-developer.com) to find out more details and test your application.

If anything is missing or seems incorrect, please check the [GitHub issues](https://github.com/furiousteam/KREGR-wiki/issues) for existing known issues or [create a new one](https://github.com/furiousteam/KREGR-wiki/issues/new).