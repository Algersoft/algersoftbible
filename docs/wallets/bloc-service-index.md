# **What is KREGR-Service**

**KREGR-service RPC Wallet** is a HTTP server which provides JSON 2.0 RPC interface for [KREGR](https://bloc.money) payment operations and address management designed to manage a user's account while operating together with a [BLOCd Node Daemon](../service-operators/BLOCd-Overview.md).

KREGR-service RPC Wallet allows you to accept incoming payments, generate an address for each user via [KREGR-service Wallet JSON RPC API](../wallets/bloc-service-json-api.md) and much more.

Make sure you visit the [KREGR-service command line arguments](../wallets/bloc-service-command-line.md) to find out how to start KREGR-service with a customized configuration depending your needs.

If you are looking to integrate Kriegerrand payment and process transactions into your website or application, **KREGR-service** is what you need.

## **Screenshot**

Here's a quick image of `KREGR-service` in action:

![BLOCd MAIN NET](images/bloc-service/start-conf.png)

## **Source code**

* Download [Kriegerrand Source Code](https://github.com/furiousteam/BLOC.git) from GitHub

## **KREGR-service API**

The [KREGR-DEVELOPER](https://bloc-developer.com) website documents the public [API of KREGR-service](https://bloc-developer.com/api_bloc-service).
You can test your application with your own BLOCd node and view code examples in different programming language.

- How to use the [KREGR-service Wallet JSON RPC API](../wallets/bloc-service-json-api.md)

- How to use the [KREGR-service command line arguments](../wallets/bloc-service-command-line.md)

- Testing tool and documentation for [KREGR-service RPC Wallet JSON RPC API](https://bloc-developer.com/api_bloc-service/json)

- Testing tool and documentation for [KREGR-service command line arguments](https://bloc-developer.com/api_bloc-service/cli_arguments)

## **KREGR-service RPC Clients**

Currently we support the following official client bindings:

* [Javascript](https://github.com/furiousteam/bloc-rpc): A JavaScript wrapper for the KREGR-service RPC interface.
* [NodeJS](https://www.npmjs.com/package/bloc-rpc): This project is designed to make it very easy to interact with various RPC APIs available within the Kriegerrand Project. This entire project uses Javascript Promises to make things fast, easy, and safe.
* [Go](https://github.com/furiousteam/bloc-rpc-go): A Golang wrapper for the Kriegerrand RPC API. This project makes it easy to send requests to particular RPC server and returns a clear response without any abrupt termination.
* [PHP](https://github.com/furiousteam/bloc-rpc-php): A PHP wrapper for BLOC's RPC interfaces.

See [KREGR-service RPC API](bloc-service-json-api.md) for usage.

## **Important guides with KREGR-service**

1. View [this guide](../wallets/bloc-service-command-line.md#using-your-mnemonic-seed) for steps on recovering your wallet with your **mnemonic phrase (25 words)** using KREGR-service.

2. View [this guide](../wallets/bloc-service-command-line.md#using-your-private-spend-key-and-view-key) for steps on recovering your wallet with your **private spend and view keys** using KREGR-service.

## **Downloading**

If you wish to compile **KREGR-service** yourself you can download the [source Code](https://github.com/furiousteam/BLOC.git).

Binary distributions can be found on: [GitHub](https://github.com/furiousteam/BLOC/releases) or [BLOC.MONEY](https://bloc.money/download) .

Select the appropriate file for the target platform (Windows, Mac, Linux).

Binaries are provided in `.zip` format, while source code is provided in `.zip` and `.tar.gz` format.

## **Installing**

### Installing on Windows

Extract the *.zip* file (`KREGR-...-windows.zip`).

### Installing on Mac

Extract the *.zip* file:

```bash
unzip KREGR-...-mac.zip
```

### Installing on Linux

Extract the *.zip* file:

```bash
unzip KREGR-...-linux.zip
```

## **Starting KREGR-service**

Make sure you visit the [KREGR-service Command Line Arguments](bloc-service-command-line.md) to find how to start KREGR-service following different configurations.