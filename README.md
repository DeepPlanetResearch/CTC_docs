# HI FREINDS

## DISCLAIMER
The coin you are mining is on our TEST NET. It is not on MAIN NET, and therefore, likely no one will want to buy your earned tokens for USD, or other consideration.
This is all for fun and testing of our new technology. THANK YOU

## How to mine CTC 2.0 on TESTNET for Windows, for Newbs
1. Install Docker. Follow these steps here:
https://docs.docker.com/desktop/windows/install/

2. Open up Windows Command Prompt, here are 10 ways to do it
https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/

3. In the command prompt, enter the following, exactlky, and hit enter
docker run -it docker.io/parity/subkey:latest generate --scheme Ecdsa

4. It will generate something like this  below, copy and paste it to a txt file
Secret phrase `caution juice atom organ advance problem want pledge someone senior holiday very` is account:
  Secret seed:       0xc8fa03532fb22ee1f7f6908b9c02b4e72483f0dbd66e4cd456b8f34c6230b849
  Public key (hex):  0xd6a3105d6768e956e9e5d41050ac29843f98561410d3a47f9dd5b3b227ab8746
  Public key (SS58): 5Gv8YYFu8H1btvmrJy9FjjAWfb99wrhV3uhPFoNEr918utyR
  Account ID:        0xd6a3105d6768e956e9e5d41050ac29843f98561410d3a47f9dd5b3b227ab8746
  SS58 Address:      5Gv8YYFu8H1btvmrJy9FjjAWfb99wrhV3uhPFoNEr918utyR

5. Look up your IP address, here, and save it somewhere, you'll use it later
https://whatismyipaddress.com/

6. Now, using the following text block as a template, enter all the correct values in replace of <VALUES>
You should replace BOTH <IP_ADDRESS> with yours, such as, 12.34.56.78
and you should replace <SS58Address> with yours, from step 4 above, such as 5Gv8YYFu8H1btvmrJy9FjjAWfb99wrhV3uhPFoNEr918utyR
```
docker run -p 30333:30333 -v <IP_ADDRESS>:/data gluwa/creditcoin:2.0.0-beta-1--validator--prometheus-external--telemetry-url "wss://telemetry.polkadot.io/submit/ 0"--bootnodes "/dns4/test-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH"--public-addr "/dns4/<IP_ADDRESS>/tcp/30333"--chain /testnetSpec.json--mining-key <SS58Address>--base-path /data--port 30333
```

When done, it should look like...
```
docker run -p 30333:30333 -v 12.34.56.78:/data gluwa/creditcoin:2.0.0-beta-1 --validator--prometheus-external --telemetry-url "wss://telemetry.polkadot.io/submit/ 0" --bootnodes "/dns4/test-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" --public-addr "/dns4/12.34.56.78/tcp/30333" --chain /testnetSpec.json --mining-key 5Gv8YYFu8H1btvmrJy9FjjAWfb99wrhV3uhPFoNEr918utyR --base-path /data--port 30333
```

7. Now, paste that exact one line into your Command Prompt, and hit enter

8. Boom, you are now mining TEST Creditcoin. Leave it running and there you go
Look for your dot on this map
https://telemetry.polkadot.io/#map/0xa22a0ea4b7d8e2618d0c46a86baaae9aed57759fc791cb350e9c6e48ee333b30
