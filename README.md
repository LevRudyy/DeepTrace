# Blockchain Fund Tracker

This tool helps trace stolen funds through the Ethereum blockchain by recursively following transaction paths.

## Features

- Recursive tracing of funds through blockchain transactions
- Stores transaction data in JSON format
- Uses Etherscan API for blockchain data
- No depth limit for tracing
- Real-time progress updates

## Setup

1. Install the required dependencies:
```bash
pip install -r requirements.txt
```

2. Create a `.env` file in the project root with your Etherscan API key and initial transaction hash:
```
ETHERSCAN_API_KEY=your_api_key_here
TX_HASH=your_transaction_hash_here
```

You can get an API key by registering at [Etherscan](https://etherscan.io/apis).

## Usage

Run the script:
```bash
python wallet_tracker3.py
```

The script will automatically:
1. Load the transaction hash from your .env file
2. Start tracing the funds recursively
3. Save all transactions to transactions.json

## Data Storage

Transactions are stored in `all_transactions.json` with the following format:
```json
[
  {
    "tx_hash": "transaction_hash",
    "date": "YYYY-MM-DD HH:MM:SS",
    "from_address": "sender_address",
    "to_address": "receiver_address",
    "value": amount_in_eth,
    "token": "ETH"
  }
]
```

## Notes

- The script includes rate limiting to respect Etherscan API limits
- Each transaction is stored only once (no duplicates)
- Values are stored in ETH (converted from Wei)
- Currently supports ETH transactions (can be extended for ERC20 tokens)
- No depth limit - will trace until no more outgoing transactions are found 


Participant wallet: 0x9CeaC40E54573409F346257Ba941Fae408513028
