
# **Additional Specs for Mining Pools**

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

## **Forked from**

* Originaly forked from the [ForkNote Project](https://github.com/forknote/forknote) which is itself a fork of [ByteCoin](https://github.com/bcndev/bytecoin)
* End of november 2018 forked to [TurtleCoin](https://github.com/turtlecoin/turtlecoin)
* How the Kriegerrand was created and why ? [Click here](../about/Background-and-History.md)


## **Mining Pool Info**

/* Pool host displayed in notifications and front-end */
# **Pool Host:** https://pool.algersoft.org/

/* Used for storage in redis so multiple coins can share the same redis instance. */
# **Coin:** Kriegerrand

/* Used for front-end display */
# **Symbol:** zKRiEGR

/* Minimum units in a single coin see COIN constant in DAEMON_CODE/src/cryptonote_config.h */
# **Coin Units:** 100000

/* Number of coin decimals places for notifications and front-end */
# **Coin Decimal Places:** 6
  
/* Coin network time to mine one block see DIFFICULTY_TARGET constant in DAEMON_CODE/src/cryptonote_config.h */
# **Coin Difficulty Target:** 120

/* Set daemon type. Supported values: default forknote (Fix block height + 1) bytecoin (ByteCoin Wallet RPC API w/ block height fix) turtlecoin (ByteCoin Wallet RPC API but no block height fix required)  */
# **Daemon Type:** default

/* Set Cryptonight algorithm settings.
   Supported algorithms: cryptonight (default). cryptonight_light and cryptonight_heavy
   Supported variants for cryptonight:** 0 (Original) 1 (Monero v7) 3 (Stellite / XTL)
   Supported variants for cryptonight_light:** 0 (Original) 1 (Aeon v7) 2 (IPBC)
   Supported blob types: 0 (Cryptonote) 1 (Forknote v1) 2 (Forknote v2) 3 (Cryptonote v2 / Masari) */
# **cn Algorithm:** cryptonight
# **cn Variant:** 1
# **cn Blob Type:** 0

/* Logging */
logging

files

/* Specifies the level of log output verbosity. This level and anything
   more severe will be logged. Options are: info warn or error. */
# **level:** info

/* Directory where to write log files. */
# **Directory:** logs

/* How often (in seconds) to append/flush data to the log files. */
# **Flush Interval:** 5

console
# **level:** info
/* Gives console output useful colors. If you direct that output to a log file
   then disable this feature to avoid nasty characters in the file. */
# **Colors:** true

/* Modular Pool Server */
Pool Server
# **Enabled:** true

/* Set to auto by default which will spawn one process/fork/worker for each CPU
core in your system. Each of these workers will run a separate instance of your
pool(s) and the kernel will load balance miners using these forks. Optionally
the 'forks' field can be a number for how many forks will be spawned. */
# **cluster Forks:** auto

/* Address where block rewards go and miner payments come from. */
# **Pool Address:** GBqRuitSoU3PFPBAkXMEnLdBRWXH4iDSD6RDxnQiEFjVJhWUi1UuqfV5EzosmaXgpPGE6JJQjMYhZZgWY8EJQn8jQTsuTit

/* This is the integrated address prefix used for miner login validation. */
# **Int Address Prefix:** 91

/* Poll RPC daemons for new blocks every this many milliseconds. */
# **Block Refresh Interval:** 1000

/* How many seconds until we consider a miner disconnected. */
# **Miner Timeout:** 900

# **SSL Cert:** ./cert.pem // The SSL certificate
# **SSL Key:** ./privkey.pem // The SSL private key
# **SSL CA:** ./chain.pem // The SSL certificate authority chain

ports:** 

# **Port:** 3333 // Port for mining apps to connect to
# **Difficulty:** 2000 // Initial difficulty miners are set to
# **Desc:** Low end hardware // Description of port

# **Port:** 4444
# **Difficulty:** 15000
# **Desc:** Mid range hardware

# **Port:** 5555
# **Difficulty:** 25000
# **Desc:** High end hardware

# **Port:** 7777
# **Difficulty:** 500000
# **Desc:** Cloud-mining / NiceHash

# **Port:** 8888
# **Difficulty:** 25000
# **Desc:** Hidden port
# **Hidden:** true // Hide this port in the front-end

# **Port:** 9999
# **Difficulty:** 20000
# **Desc:** SSL connection
# **SSL:** true // Enable SSL


/* Variable difficulty is a feature that will automatically adjust difficulty for
individual miners based on their hashrate in order to lower networking and CPU
overhead. */
varDiff
# **Min Diff:** 100 // Minimum difficulty
# **Max Diff:** 100000000
# **Target Time:** 60 // Try to get 1 share per this many seconds
# **Retarget Time:** 30 // Check to see if we should retarget every this many seconds
# **Variance Percent:** 30 // Allow time to vary this % from target without retargeting
# **Max Jump:** 100 // Limit diff percent increase/decrease in a single retargeting

	
/* Set difficulty on miner client side by passing <address> param with +<difficulty> postfix */
fixedDiff
# **Enabled:** true
# **Separator:** + // Character separator between <address> and <difficulty>


/* Set payment ID on miner client side by passing <address>.<paymentID> */
paymentId
# **Address Separator:** . // Character separator between <address> and <paymentID>


/* Feature to trust share difficulties from miners which can
significantly reduce CPU load. */
shareTrust
# **Enabled:** true
# **Min:** 10 // Minimum percent probability for share hashing
# **Step Down:** 3 // Increase trust probability % this much with each valid share
# **Threshold:** 10 // Amount of valid shares required before trusting begins
# **Penalty:** 30 // Upon breaking trust require this many valid share before trusting


/* If under low-diff share attack we can ban their IP to reduce system/network load. */
banning
# **Enabled:** true
# **Time:** 600 // How many seconds to ban worker for
# **Invalid Percent:** 25 // What percent of invalid shares triggers ban
# **Check Threshold:** 30 // Perform check when this many shares have been submitted


/* Slush Mining is a reward calculation technique which disincentivizes pool hopping and rewards 'loyal' miners by valuing younger shares higher than older shares. Remember adjusting the weight!
More about it here: https://mining.bitcoin.cz/help/#!/manual/rewards */
slushMining
# **Enabled:** false // Enables slush mining. Recommended for pools catering to professional miners
# **Weight:** 300 // Defines how fast the score assigned to a share declines in time. The value should roughly be equivalent to the average round duration in seconds divided by 8. When deviating by too much numbers may get too high for JS.


/* Module that sends payments to miners according to their submitted shares. */
payments
# **Enabled:** true
# **Interval:** 300 // How often to run in seconds
# **Max Addresses:** 50 // Split up payments if sending to more than this many addresses
# **Mixin:** 5 // Number of transactions yours is indistinguishable from
# **Priority:** 0 // The transaction priority
# **Transfer Fee:** 4000000000 // Fee to pay for each transaction
# **Dynamic Transfer Fee:** true // Enable dynamic transfer fee (fee is multiplied by number of miners)
# **Miner Pay Fee : true // Miner pays the transfer fee instead of pool owner when using dynamic transfer fee
# **Min Payment:** 100000000000 // Miner balance required before sending payment
# **max Payment:** null // Maximum miner balance allowed in miner settings
# **Max Transaction Amount:** 0 // Split transactions by this amount (to prevent too big transaction error)
# **Denomination:** 10000000000 // Truncate to this precision and store remainder


/* Module that monitors the submitted block maturities and manages rounds. Confirmed
   blocks mark the end of a round where workers' balances are increased in proportion
   to their shares. */
blockUnlocker
# **Enabled:** true
# **Interval:** 30 // How often to check block statuses in seconds

/* Block depth required for a block to unlocked/mature. Found in daemon source as
the variable CRYPTONOTE_MINED_MONEY_UNLOCK_WINDOW */
# **Depth:** 60
# **PoolFee:** 0.8 // 0.8% pool fee (1% total fee total including donations)
# **DevDonation:** 0.2 // 0.2% donation to send to pool dev
# **networkFee:** 0.0 // Network/Governance fee (used by some coins like Loki)

/* Some forknote coins have an issue with block height in RPC request to fix you can enable this option.
See: https://github.com/forknote/forknote-pool/issues/48 */
# **fixBlockHeightRPC:** false


/* AJAX API used for front-end website. */
api
# **enabled:** true
# **hashrateWindow:** 600 // How many second worth of shares used to estimate hash rate
# **updateInterval:** 3 // Gather stats and broadcast every this many seconds
# **bindIp:** 0.0.0.0 // Bind API to a specific IP (set to 0.0.0.0 for all)
# **Port:** 8117 // The API port
# **blocks:** 30 // Amount of blocks to send at a time
# **Payments:** 30 // Amount of payments to send at a time
# **Password:** your_password // Password required for admin stats
# **SSL:** false // Enable SSL API
# **SSLPort:** 8119 // The SSL port
# **SSLCert:** ./cert.pem // The SSL certificate
# **SSLKey:** ./privkey.pem // The SSL private key
# **SSLCA:** ./chain.pem // The SSL certificate authority chain
# **trustProxyIP:** false // Proxy X-Forwarded-For support
# **ignoreSrcIP:** false // Silently ignore source IP when changing min payments or notification settings


/* Coin daemon connection details (default port is 18981) */
daemon
# **host:** 127.0.0.1
# **Port:** 18981


/* Wallet daemon connection details (default port is 18980) */
wallet
# **host:** 127.0.0.1
# **Port:** 18982


/* Redis connection info (default port is 6379) */
redis
# **host:** 127.0.0.1
# **Port:** 6379
# **auth:** null // If set client will run redis auth command on connect. Use for remote db
# **Db:** 0 // Set the REDIS database to use (default to 0)
# **cleanupInterval:** 15 // Set the REDIS database cleanup interval (in days)


/* Pool Notifications */
notifications
# **emailTemplate:** email_templates/default.txt
# **emailSubject
# **emailAdded:** Your email was registered
# **workerConnected:** Worker %WORKER_NAME% connected
# **workerTimeout:** Worker %WORKER_NAME% stopped hashing
# **workerBanned:** Worker %WORKER_NAME% banned
# **blockFound:** Block %HEIGHT% found !
# **blockUnlocked:** Block %HEIGHT% unlocked !
# **blockOrphaned:** Block %HEIGHT% orphaned !
# **Payment:** We sent you a payment !

email Message
# **emailAdded:** Your email has been registered to receive pool notifications.
# **workerConnected:** Your worker %WORKER_NAME% for address %MINER% is now connected from ip %IP%.
# **workerTimeout:** Your worker %WORKER_NAME% for address %MINER% has stopped submitting hashes on %LAST_HASH%.
# **workerBanned:** Your worker %WORKER_NAME% for address %MINER% has been banned.
# **blockFound:** Block found at height %HEIGHT% by miner %MINER% on %TIME%. Waiting maturity.
# **blockUnlocked:** Block mined at height %HEIGHT% with %REWARD% and %EFFORT% effort on %TIME%.
# **blockOrphaned:** Block orphaned at height %HEIGHT% :(
# **Payment:** A payment of %AMOUNT% has been sent to %ADDRESS% wallet.

telegram Message
# **workerConnected:** Your worker _%WORKER_NAME%_ for address _%MINER%_ is now connected from ip _%IP%_.
# **workerTimeout:** Your worker _%WORKER_NAME%_ for address _%MINER%_ has stopped submitting hashes on _%LAST_HASH%_.
# **workerBanned:** Your worker _%WORKER_NAME%_ for address _%MINER%_ has been banned.
# **blockFound:** *Block found at height* _%HEIGHT%_ *by miner* _%MINER%_*! Waiting maturity.*
# **blockUnlocked:** *Block mined at height* _%HEIGHT%_ *with* _%REWARD%_ *and* _%EFFORT%_ *effort on* _%TIME%_*.*
# **blockOrphaned:** *Block orphaned at height* _%HEIGHT%_ *:(*
# **Payment:** A payment of _%AMOUNT%_ has been sent.

/* Email Notifications */

email
# **enabled:** false
# **fromAddress:** your@email.com // Your sender email
# **transport:** sendmail // The transport mode (sendmail smtp or mailgun)

// Configuration for sendmail transport
// Documentation: http://nodemailer.com/transports/sendmail/

sendmail
# **Path:** /usr/sbin/sendmail // The path to sendmail command
}

// Configuration for SMTP transport
// Documentation: http://nodemailer.com/smtp/

smtp
# **host:** smtp.example.com // SMTP server
# **Port:** 587 // SMTP port (25 587 or 465)
# **secure:** false // TLS (if false will upgrade with STARTTLS)
# **auth
# **user:** username // SMTP username
# **Pass:** password // SMTP password

tls
# **rejectUnauthorized:** false // Reject unauthorized TLS/SSL certificate



// Configuration for MailGun transport
mailgun
# **key:** your-private-key // Your MailGun Private API key
# **Domain:** mg.yourdomain // Your MailGun domain

/* Telegram channel notifications.
   See Telegram documentation to setup your bot: https://core.telegram.org/bots#3-how-do-i-create-a-bot */
telegram
# **enabled:** false
# **botName:**  // The bot user name.
# **token:**  // The bot unique authorization token
# **channel:**  // The telegram channel id (ex: BlockHashMining)
# **channelStats
# **enabled:** false // Enable periodical updater of pool statistics in telegram channel
# **interval:** 5 // Periodical update interval (in minutes)

botCommands // Set the telegram bot commands
# **stats:** /stats // Pool statistics
# **enable:** /enable // Enable telegram notifications
# **Disable:** /disable // Disable telegram notifications



/* Monitoring RPC services. Statistics will be displayed in Admin panel */
monitoring
daemon
# **checkInterval:** 60 // Interval of sending rpcMethod request
# **rpcMethod:** getblockcount // RPC method name

wallet
# **checkInterval:** 60
# **rpcMethod:** getbalance



/* Prices settings for market and price charts */
prices
# **source:** cryptonator // Exchange (supported values: cryptonator altex crex24 cryptopia stocks.exchange tradeogre)
# **currency:** USD // Default currency
}
	
/* Collect pool statistics to display in frontend charts  */
charts
pool
hashrate
# **enabled:** true // Enable data collection and chart displaying in frontend
# **updateInterval:** 60 // How often to get current value
# **stepInterval:** 1800 // Chart step interval calculated as average of all updated values
# **maximumPeriod:** 86400 // Chart maximum periods (chart points number = maximumPeriod / stepInterval = 48)

		miners
# **enabled:** true
# **updateInterval:** 60
# **stepInterval:** 1800
# **maximumPeriod:** 86400
			
workers
# ** enabled:** true
# **updateInterval:** 60
# **stepInterval:** 1800
# ** maximumPeriod:** 86400

difficulty
# **Enabled:** true
# **Update Interval:** 1800
# **Step Interval:** 10800
# **Maximum Period:** 604800

price
# **Enabled:** true
# **Update Interval:** 1800
# **Sep Interval:** 10800
# **Maximum Period:** 604800

profit
# **Enabled:** true
# **Update Interval:** 1800
# **Step Interval:** 10800
# **Maximum Period:** 604800


user // Chart data displayed in user stats block
hashrate
# **Enabled:** true
# **Update Interval:** 180
# **Step Interval:** 1800
# **Maximum Period:** 86400

payments // Payment chart uses all user payments data stored in DB
# **Enabled:** true


blocks
# **Enabled:** true
# **Days:** 30 // Number of days displayed in chart (if value is 1 display last 24 hours)

