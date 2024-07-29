# Customized Subnet Using HyperSDK

<p >launching the subnet using the following command.</p>

```bash
./scripts/run.sh;
```


if we don't need 2 Subnets for the testing, we can run 
 
 ```bash
MODE="run-single" ./scripts/run.sh
```



By default, this allocates all funds on the network to `token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp`.

The private key for this address is
`0x323b1d8f4eed5f0da9da93071b034f2dce9d2d22692c172f3cb252a64ddfafd01b057de320297c29ad0c1f589ea216869cf1938d88c9fbd70d6748323dbf2fa7`.
this key has is also stored at `demo.pk`




To  interact with the `tokenvm`, implement the `token-cli`.
Next, we'll need to build this. by using this command

```bash
./scripts/build.sh
```

This command will put the compiled CLI in `./build/token-cli`._

Lastly, we'll need to add the chains that we created and the default key to the
`token-cli`. we can use the following commands

```bash
./build/token-cli key import demo.pk
./build/token-cli chain import-anr
```


`chain import-anr` connects to the Avalanche Network Runner server running in
the background and pulls the URIs of all nodes tracking each chain we
created.

### Mint and Trade
#### Step 1: Create our Asset
let's create our own asset. You can do so by running the following command:

```bash
./build/token-cli action create-asset
```

_`txID` is the `assetID` of your new asset._

The "loaded address" here is the address of the default private key (`demo.pk`). We
use this key to authenticate all interactions with the `tokenvm`.

#### Step 2: Mint our Asset
After we've created our own asset, we can now mint some of it. You can do so by
running the following command:
```bash
./build/token-cli action mint-asset
```

#### Step 3: View our Balance
Now, let's check that the mint worked right by checking our balance. we can do
so by running the following command:

```bash
./build/token-cli key balance
```

After all this we can stop our running subnet network by using: 
 to stop the network we started using
`killall avalanche-network-runner`._

# Author
Dikshant @DkRadhey

