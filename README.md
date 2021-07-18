# NoDevFee

-p: Set the port(s) for your pool. Can be separated by ",". For Example: -p 4444,14444

-w: wallet address. For example: -w 0xdeadbeef1234. If no walletaddress is passed it will try to read the address from "wallet.txt" file

-s: searchpattern, defaults to "eth_submitLogin"

-r: replacementpattern, defaults to "0x"

## How does it work?

It intercepts network traffic on the given ports and searches every network-message for 'searchpattern'. If the message includes the pattern, it will then search for the 'replacementpattern'. If the pattern was found, the wallet address will be written at its position.

## Example:
by passing ```-w 0xdeadbeef1234 -r 0x```

"{ action: "eth_submitLogin" data: '0x1234567f1234' }"

would be replaced by

"{ action: "eth_submitLogin" data: '0xdeadbeef1234' }"

For educational purpose only
