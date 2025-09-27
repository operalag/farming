# farming
TON button for farming SIXR 

Functionality 

The Flow
The process involves a series of on-chain and off-chain interactions, orchestrated by your Telegram Mini App.

User Interface: The user opens your Mini App, which presents a button (e.g., "Start Farming"). This button is the trigger for the entire sequence.

Wallet Connection: The Mini App uses the TON Connect SDK to establish a secure connection with the user's TON wallet (e.g., Wallet, Tonkeeper, MyTonWallet). This is a crucial first step that allows your app to request and sign transactions on behalf of the user, without ever handling their private keys.

Token Balance Check: The app queries the user's wallet to get their balance of the $SIXR token.

Transaction 1: Token Swap:

The Mini App calculates 50% of the user's $SIXR balance.

It then constructs a swap transaction for Ston.fi. This transaction sends the calculated amount of $SIXR to the Ston.fi router contract, with an instruction to swap it for $OFD.

The app requests the user to sign this transaction via TON Connect. The user's wallet will display the details of the transaction (amount of $SIXR to be sent, and the expected amount of $OFD to be received).

Once signed, the transaction is broadcasted to the TON blockchain.

Transaction 2: Liquidity Provision:

After the swap transaction is confirmed on-chain (which happens very quickly on TON), the user will have a combination of $SIXR and $OFD.

The app then constructs a liquidity provision transaction for the $SIXR/$OFD pool on Ston.fi. This transaction deposits the remaining 50% of the user's $SIXR and the newly acquired $OFD into the liquidity pool.

The app requests the user to sign this second transaction. The user's wallet will show the tokens being deposited.

Once signed, this transaction is also broadcasted.

Transaction 3: LP Token Staking (Farming):

Once the liquidity provision transaction is confirmed, the user's wallet receives Liquidity Provider (LP) tokens. These tokens represent their share of the $SIXR/$OFD liquidity pool.

The Mini App then constructs a staking transaction to stake these LP tokens in the farming contract on Ston.fi. This is what enables the user to earn farming rewards.

The app requests the user to sign this final transaction.

The signed transaction is broadcasted, and the user's position is now active in the farm, earning rewards.
