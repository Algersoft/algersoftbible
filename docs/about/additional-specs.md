
# **Additional KREGR Specs**
_Data for setting up KREGR mining pools, seed nodes and other "extra mile" tasks to help grow and promote the community._

Name: **KRIEGERRAND**
Website name : [KRIEGERRAND.com](https://kriegerrand.com)

* [Whitepaper](http://kriegerrand.com/wp-content/uploads/2019/02/Kriegerrand-White-Paper.pdf)
* [Source Code](https://github.com/Algersoft/Kriegerrand)
* **TICKER**: KREGR
* **ADDRESS PREFIX**: `ZkRiEGER`
* **TEST NET ADDRESS PREFIX**: `xkRiEGER`
* **MAX SUPPLY**: 26000666 Kriegerrand
* **DECIMAL PLACES**: 6 (.000000 KREGR)
* **TX FEES**: (0.00001 KREGR)
* **PROOF OF WORK ALGORITHM**: [CryptoNote](https://cryptonote.org) CRYPTONIGHT TURTLE
* Our Proof Of Work algortyhm is designed to make low end and high end hardware mining roughly equally efficient and restrict ASIC mining
* **BLOCK TIME**: 666 seconds
* **BLOCKS PER DAY**: whatever
* **PREMINE**: 666 Kriegerrand (.00001% of total supply) for mostly cocaine. [Why a premine ?] ( mostly...cocaine? ) 

* ASIC resistant
* NiceHash resistant
* Enhanced Privacy
* Elastic Blocks
* Fair Mining

* **Forked from**

* Originaly forked from the [ForkNote Project](https://github.com/forknote/forknote) which is itself a fork of [ByteCoin](https://github.com/bcndev/bytecoin)
* End of november 2018 forked to [TurtleCoin](https://github.com/turtlecoin/turtlecoin)
* How the Kriegerrand was created and why ? [Click here](../about/Background-and-History.md)


* **Mining Pool Info**

Pool host displayed in notifications and front-end
* **Pool Host**: pool.algersoft.org

Used for storage in redis so multiple coins can share the same redis instance.
* **Coin**: Kriegerrand

 Used for front-end display 
* **Symbol**: zKRiEGR

 Minimum units in a single coin see COIN constant in DAEMON_CODE/src/cryptonote_config.h 
* **Coin Units**: 100000

 Number of coin decimals places for notifications and front-end 
* **Coin Decimal Places**: 6
  
 Coin network time to mine one block see DIFFICULTY_TARGET constant in DAEMON_CODE/src/cryptonote_config.h 
* **Coin Difficulty Target**: 120

 Set daemon type. Supported values: default forknote (Fix block height + 1) bytecoin (ByteCoin Wallet RPC API w/ block height fix) turtlecoin (ByteCoin Wallet RPC API but no block height fix required)  
* **Daemon Type**: default

 Set Cryptonight algorithm settings.
   Supported algorithms: cryptonight (default). cryptonight_light and cryptonight_heavy
   Supported variants for cryptonight**: 0 (Original) 1 (Monero v7) 3 (Stellite / XTL)
   Supported variants for cryptonight_light**: 0 (Original) 1 (Aeon v7) 2 (IPBC)
   Supported blob types: 0 (Cryptonote) 1 (Forknote v1) 2 (Forknote v2) 3 (Cryptonote v2 / Masari) 
* **cn Algorithm**: cryptonight
* **cn Variant**: 1
* **cn Blob Type**: 0

# **Logging**

* **level**: info
_Specifies the level of log output verbosity. This level and anything more severe will be logged. Options are: info warn or error_

* **Directory**: logs
_Directory where to write log files._

* **Flush Interval**: 5
_How often (in seconds) to append/flush data to the log files._ 


# **CONSOLE**

* **level**: info
_Gives console output useful colors. If you direct that output to a log file
   then disable this feature to avoid nasty characters in the file._ 

* **Colors**: true


# **Modular Pool Server** 

* **Enabled**: true

* **cluster Forks**: auto
 _Set to auto by default which will spawn one process/fork/worker for each CPU
core in your system. Each of these workers will run a separate instance of your
pool(s) and the kernel will load balance miners using these forks. Optionally
the 'forks' field can be a number for how many forks will be spawned._ 

* **Pool Address**: GBqRuitSoU3PFPBAkXMEnLdBRWXH4iDSD6RDxnQiEFjVJhWUi1UuqfV5EzosmaXgpPGE6JJQjMYhZZgWY8EJQn8jQTsuTit
_Address where block rewards go and miner payments come from._

* **Int Address Prefix**: 91
 _This is the integrated address prefix used for miner login validation._ 

* **Block Refresh Interval**: 1000
 _Poll RPC daemons for new blocks every this many milliseconds._ 

* **Miner Timeout**: 900
 _How many seconds until we consider a miner disconnected._ 

* **SSL Cert**: ./cert.pem  _The SSL certificate_
* **SSL Key**: ./privkey.pem _The SSL private key_
* **SSL CA**: ./chain.pem _The SSL certificate authority chain_


# **ports**

* **Port**: 3333 _Port for mining apps to connect to_
* **Difficulty**: 2000 _Initial difficulty miners are set to_
* **Desc**: Low end hardware _Description of port_

* **Port**: 4444
* **Difficulty**: 15000
* **Desc**: Mid range hardware

* **Port**: 5555
* **Difficulty**: 25000
* **Desc**: High end hardware

* **Port**: 7777
* **Difficulty**: 500000
* **Desc**: Cloud-mining / NiceHash

* **Port**: 8888
* **Difficulty**: 25000
* **Desc**: Hidden port
* **Hidden**: true _Hide this port in the front-end_

* **Port**: 9999
* **Difficulty**: 20000
* **Desc**: SSL connection
* **SSL**: true _Enable SSL_

# **Var Diff**

_*Variable difficulty is a feature that will automatically adjust difficulty for
individual miners based on their hashrate in order to lower networking and CPU
overhead*_ 

* **Min Diff**: 100 _Minimum difficulty_
* **Max Diff**: 100000000
* **Target Time**: 60 _Try to get 1 share per this many seconds_
* **Retarget Time**: 30 _Check to see if we should retarget every this many seconds_
* **Variance Percent**: 30 _Allow time to vary this % from target without retargeting_
* **Max Jump**: 100 _Limit diff percent increase/decrease in a single retargeting_

	
# **Fixed Diff**

*_Set difficulty on miner client side by passing <address> param with +<difficulty> postfix_*
	
* **Enabled**: true
* **Separator**: + _Character separator between <address> and <difficulty>_

# **Payment Id**

*_Set payment ID on miner client side by passing <address>.<paymentID>_*



* **Address Separator**: . _Character separator between <address> and <paymentID>_

# **Share Trust**

_*Feature to trust share difficulties from miners which can significantly reduce CPU load.*_

* **Enabled**: true
* **Min**: 10 _Minimum percent probability for share hashing_
* **Step Down**: 3 _Increase trust probability % this much with each valid share_
* **Threshold**: 10 _Amount of valid shares required before trusting begins_
* **Penalty**: 30 _Upon breaking trust require this many valid share before trusting_


# **banning**

_*If under low-diff share attack we can ban their IP to reduce system/network load. *_

* **Enabled**: true
* **Time**: 600 _How many seconds to ban worker for_
* **Invalid Percent**: 25 _What percent of invalid shares triggers ban_
* **Check Threshold**: 30 _Perform check when this many shares have been submitted_


# **Slush Mining**

_*Slush Mining is a reward calculation technique which disincentivizes pool hopping and rewards 'loyal' miners by valuing younger shares higher than older shares. Remember adjusting the weight! More about it here: https://mining.bitcoin.cz/help/#!/manual/rewards *_

* **Enabled**: false _Enables slush mining. Recommended for pools catering to professional miners_
* **Weight**: 300 _Defines how fast the score assigned to a share declines in time. The value should roughly be equivalent to the average round duration in seconds divided by 8. When deviating by too much numbers may get too high for JS._


# **Payments**

_*Module that sends payments to miners according to their submitted shares.*_

* **Enabled**: true
* **Interval**: 300 _How often to run in seconds
* **Max Addresses**: 50 _Split up payments if sending to more than this many addresses
* **Mixin**: 5 _Number of transactions yours is indistinguishable from_
* **Priority**: 0 _The transaction priority_
* **Transfer Fee**: 4000000000 _Fee to pay for each transaction_
* **Dynamic Transfer Fee**: true _Enable dynamic transfer fee (fee is multiplied by number of miners)_
* **Miner Pay Fee**: true _Miner pays the transfer fee instead of pool owner when_ using dynamic transfer fee_
* **Min Payment**: 100000000000 _Miner balance required before sending payment_
* **max Payment**: null _Maximum miner balance allowed in miner settings_
* **Max Transaction Amount**: 0 _Split transactions by this amount (to prevent too big transaction error)_
* **Denomination**: 10000000000 _Truncate to this precision and store remainder_


# **Block Unlocker**
 
*_Module that monitors the submitted block maturities and manages rounds. Confirmed blocks mark the end of a round where workers' balances are increased in proportion to their shares._*

* **Enabled**: true
* **Interval**: 30 _How often to check block statuses in seconds_

_*Block depth required for a block to unlocked/mature. Found in daemon source as
the variable CRYPTONOTE_MINED_MONEY_UNLOCK_WINDOW*_

* **Depth**: 60
* **PoolFee**: 0.8 _0.8% pool fee (1% total fee total including donations)_
* **DevDonation**: 0.2 _0.2% donation to send to pool dev_
* **networkFee**: 0.0 _Network/Governance fee (used by some coins like Loki)_

_Some forknote coins have an issue with block height in RPC request to fix you can enable this option. See: https://github.com/forknote/forknote-pool/issues/48_

# **fixBlockHeightRPC**: false

# **API**

**AJAX API used for front-end website.**

* **enabled**: true
* **hashrateWindow**: 600 _How many second worth of shares used to estimate hash rate_
* **updateInterval**: 3 _Gather stats and broadcast every this many seconds_
* **bindIp**: 0.0.0.0 _Bind API to a specific IP (set to 0.0.0.0 for all)_
* **Port**: 8117 _The API port_
* **blocks**: 30 _Amount of blocks to send at a time_
* **Payments**: 30 _Amount of payments to send at a time_
* **Password**: your_password_ Password required for admin stats_
* **SSL**: false_ Enable SSL API_
* **SSLPort**: 8119_ The SSL port_
* **SSLCert**: ./cert.pem _The SSL certificate_
* **SSLKey**: ./privkey.pem _The SSL private key_
* **SSLCA**: ./chain.pem _The SSL certificate authority chain_
* **trustProxyIP**: false _Proxy X-Forwarded-For support_
* **ignoreSrcIP**: false _Silently ignore source IP when changing min payments or notification settings_


# **Daemon**

_Coin daemon connection details (default port is 18981)_

* **host**: 127.0.0.1
* **Port**: 18981

# **Wallet**

_Wallet daemon connection details (default port is 18980)_

* **host**: 127.0.0.1
* **Port**: 18982

# **Redis**

_Redis connection info (default port is 6379)_

* **host**: 127.0.0.1
* **Port**: 6379
* **auth**: null _If set client will run redis auth command on connect. Use for remote db_
* **Db**: 0 _Set the REDIS database to use (default to 0)_
* **cleanupInterval**: 15 _Set the REDIS database cleanup interval (in days)_


# **Pool Notifications** 

# **Notifications**

* **emailTemplate**: email_templates/default.txt
* **emailSubject
* **emailAdded**: Your email was registered
* **workerConnected**: Worker %WORKER_NAME% connected
* **workerTimeout**: Worker %WORKER_NAME% stopped hashing
* **workerBanned**: Worker %WORKER_NAME% banned
* **blockFound**: Block %HEIGHT% found
* **blockUnlocked**: Block %HEIGHT% unlocked
* **blockOrphaned**: Block %HEIGHT% orphaned
* **Payment**: We sent you a payment

# **Email Message**

* **emailAdded**: Your email has been registered to receive pool notifications.
* **workerConnected**: Your worker %WORKER_NAME% for address %MINER% is now connected from ip %IP%.
* **workerTimeout**: Your worker %WORKER_NAME% for address %MINER% has stopped submitting hashes on %LAST_HASH%.
* **workerBanned**: Your worker %WORKER_NAME% for address %MINER% has been banned.
* **blockFound**: Block found at height %HEIGHT% by miner %MINER% on %TIME%. Waiting maturity.
* **blockUnlocked**: Block mined at height %HEIGHT% with %REWARD% and %EFFORT% effort on %TIME%.
* **blockOrphaned**: Block orphaned at height %HEIGHT% :(
* **Payment**: A payment of %AMOUNT% has been sent to %ADDRESS% wallet.

# **Telegram Message**
* **workerConnected**: Your worker _%WORKER_NAME%_ for address _%MINER%_ is now connected from ip _%IP%_.
* **workerTimeout**: Your worker _%WORKER_NAME%_ for address _%MINER%_ has stopped submitting hashes on _%LAST_HASH%_.
* **workerBanned**: Your worker _%WORKER_NAME%_ for address _%MINER%_ has been banned.
* **blockFound**: *Block found at height* _%HEIGHT%_ *by miner* _%MINER%_*! Waiting maturity.*
* **blockUnlocked**: *Block mined at height* _%HEIGHT%_ *with* _%REWARD%_ *and* _%EFFORT%_ *effort on* _%TIME%_*.*
* **blockOrphaned**: *Block orphaned at height* _%HEIGHT%_ *:(*
* **Payment**: A payment of _%AMOUNT%_ has been sent.

 # **Email Notifications**

# **Email**
* **enabled**: false
* **fromAddress**: your@email.com _Your sender email_
* **transport**: sendmail  _The transport mode (sendmail smtp or mailgun_

 # **Configuration for sendmail transport**
 _Documentation: http://nodemailer.com/transports/sendmail/_

# **sendmail**
* **Path**: /usr/sbin/sendmail // The path to sendmail command

# **Configuration for SMTP transport**
* **Documentation:** -http://nodemailer.com/smtp/-

# **SMTP**

* **host**: smtp.example.com _SMTP server_
* **Port**: 587 _SMTP port (25 587 or 465)_
* **secure**: false _TLS (if false will upgrade with STARTTLS)_
* **auth
* **user**: username _SMTP username_
* **Pass**: password _SMTP password_

TLS

* **rejectUnauthorized**: false _Reject unauthorized TLS/SSL certificate_


# **Configuration for MailGun transport**

# **Mail Gun**

* **key**: your-private-key  _Your MailGun Private API key_
* **Domain**: mg.yourdomain _Your MailGun domain_

# **Telegram Channel Notifications**

_See Telegram documentation to setup your bot: https://core.telegram.org/bots#3-how-do-i-create-a-bot 
telegram_

* **enabled**: false
* **botName**:  _The bot user name._
* **token**:  _The bot unique authorization token_
* **channel**:  _The telegram channel id (ex: BlockHashMining)_
* **channelStats
* **enabled**: false _Enable periodical updater of pool statistics in telegram channel_
* **interval**: 5 _Periodical update interval (in minutes)_

# **Bot Commands** _Set the telegram bot commands_
* **stats**: /stats _Pool statistics_
* **enable**: /enable _Enable telegram notifications_
* **Disable**: /disable _Disable telegram notifications_


# **Monitoring RPC services**
_Statistics will be displayed in Admin panel monitoring daemon_

* **checkInterval**: 60 _Interval of sending rpcMethod request_
* **rpcMethod**: getblockcount _RPC method name_

**Wallet**

* **checkInterval**: 60
* **rpcMethod**: getbalance

_Prices settings for market and price charts_

* **source**: cryptonator _Exchange (supported values: cryptonator altex crex24 cryptopia stocks.exchange tradeogre)_
* **currency**: USD _Default currency_

**Charts**
	
_Collect pool statistics to display in frontend charts pool hashrate_

* **enabled**: true _Enable data collection and chart displaying in frontend_
* **updateInterval**: 60 _How often to get current value_
* **stepInterval**: 1800 _Chart step interval calculated as average of all updated values_
* **maximumPeriod**: 86400 _Chart maximum periods (chart points number = maximumPeriod / stepInterval = 48)_

# **Miners**
* **enabled**: true
* **updateInterval**: 60
* **stepInterval**: 1800
* **maximumPeriod**: 86400
			
# **Workers**
* ** enabled**: true
* **updateInterval**: 60
* **stepInterval**: 1800
* ** maximumPeriod**: 86400

# **Difficulty**
* **Enabled**: true
* **Update Interval**: 1800
* **Step Interval**: 10800
* **Maximum Period**: 604800

# **Price**
* **Enabled**: true
* **Update Interval**: 1800
* **Sep Interval**: 10800
* **Maximum Period**: 604800

# **Profit**
* **Enabled**: true
* **Update Interval**: 1800
* **Step Interval**: 10800
* **Maximum Period**: 604800

# **Chart data displayed in user stats**
* **Enabled**: true
* **Update Interval**: 180
* **Step Interval**: 1800
* **Maximum Period**: 86400

# **Payment chart uses all user payments data stored in DB**
* **Enabled**: true

# **Blocks**
* **Enabled**: true
* **Days**: 30 _Number of days displayed in chart (if value is 1 display last 24 hours)_

