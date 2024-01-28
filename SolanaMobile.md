# Building Mobile Apps on Solana
Solana Mobile Stack (SMS) is an open-source development toolkit that enables developers to build rich web3 applications natively on Android mobile devices, running on the Solana blockchain12. As a software development kit (SDK), SMS provides libraries and interfaces that enable any developer to build Solana-powered applications on Android-compatible devices. Components of SMS SDK:- <br /> 
<b>•	Seed Vault :</b> A secure environment built into a mobile device that keeps private keys, seed phrases, and secrets separated from the application layer yet still capable of interacting with apps running on the device or in a mobile browser. It accesses the highest privileged security environment available on a device, from secure operating modes of the processor to dedicated Secure Elements, which enables a secure transaction signing experience through UI components built into Android.<br />
<b>•	Mobile Wallet Adapter :</b> A protocol for connecting web apps and native Android apps to wallets on mobile devices3. The open-source protocol is designed to support all mobile platforms, not just Android, and can work with wallet apps providing signing services to apps running remotely, such as other mobile devices, and on desktop or laptop computers.<br />
<b>•	Solana Pay :</b> Solana Pay is a decentralized payment rail that runs on Solana. Since it is embedded in the Solana Mobile SDK, mobile wallet apps will be able to use the system features of Android phones to allow payments through QR codes, NFT taps, messages, etc.<br />
<b>•	dApp Store :</b> The dApp store is now open for app submissions. It allows easy dApp submission and distribution.<br />
<b>•	Saga :</b> Solana Mobile teamed up with OSOM to integrate the Solana Mobile Stack with a flagship quality device, Saga4. Saga delivers premium hardware, clean Android, and Web3 in a phone you’ll love to use. It has a 6.67” OLED Display, 512 GB Storage, 12 GB RAM.<br />
The Solana Mobile Stack shows a new path forward on Solana that is open source, secure, optimized for web3, and easy to use. Developers can now bring the power of Solana to the computers in our pockets, not just our backpacks.
## Mobile dApp Architecture Overview
Bird’s Eye view of Mobile DApp’s interaction with mobile wallet and Solana Network.
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/dapp_architecture_full.svg)
<b> The Mobile Wallet Adapter (MWA) </b> protocol is what defines the communication exchange between a dApp and a mobile wallet. In the protocol, the dApp sends requests (i.e: authorization or signing), while the wallet is responsible for displaying these requests to the user and responding to the dApp if approved. <br />
## Development Setup
Before starting you need the following perquisite for Android Mobile Development:-<br />
<b1-Install Android Studio:- You need to install Android Studio to build apps and manage your device/emulator.  While on Android Studio installation wizard, make sure the boxes next to all of the following items are checked:-<br />
•	Android SDK <br />
•	Android SDK Platform <br />
•	Android Virtual Device <br />
2-	Setup Device/Emulator:- To test and preview your app as you develop, you can build and deploy your app to an Android device or emulator in Android Studio <br />
3-	Install a wallet App:- The Mobile Wallet Adapter (MWA) library allows your dApp to connect and interface with Wallet Apps that implement the MWA protocol. For testing, you want to have an MWA-compatible wallet on the same device or emulator as your dApp.<br />
The fakewallet app is a 'fake' Mobile Wallet Adapter compliant wallet. Install it on your Android emulator or device. It does not store persistent keypairs, and the wallet is "reset" each time the app is exited.<br />
Installation steps<br />
1.	Clone the Mobile Wallet Adapter repo, containing the fakewallet app from the GitHub repository<br />
``git clone https://github.com/solana-mobile/mobile-wallet-adapter.git`` <br />
2.	In Android Studio, Open project > Navigate to the cloned directory > Select mobile-wallet-adapter/android/build.gradle <br />
3.	After Android Studio finishes loading the project, select fakewallet in the build/run configuration dropdown in the top right <br />
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/fakewallet.jpg) 
	After it builds successfully, you should see the app on your Android device or emulator. <br />
4- Install real wallet apps:- fakewallet was created for implementation reference and quick testing purposes. You should also test your dApp with popular MWA-compatible wallet apps like Phantom, Solflare, and Ultimate. <br />
 If you're planning on developing with React Native, then follow the following prerequisite:- <br />
If you are new to mobile development, the easiest way to get started is with Expo Go. Expo is a set of tools and services built around React Native and, while it has many features, the most relevant feature for us right now is that it can get you writing a React Native app within minutes but it only includes native modules. If you are building production-level Dapp, you need a specific tool that might not be available in Expo Go. <br />
## Perquisite:-<br />
### Node, JDK (java Development Kit):-<br />
It is recommended to use an LTS version of Node. React Native also requires Java SE Development Kit (JDK). <br />
choco install -y nodejs-lts microsoft-openjdk17 <br />

1. Install Android Studio <br />
Download and install Android Studio. While on Android Studio installation wizard, make sure the boxes next to all of the following items are checked: <br />
•	Android SDK <br />
•	Android SDK Platform <br />
•	Android Virtual Device <br />
2. Configure the ANDROID_HOME environment variable <br />
The React Native tools require some environment variables to be set up to build apps with native code.
1.	Open the Windows Control Panel.
2.	Click on User Accounts, then click User Accounts again
3.	Click on Change my environment variables
4.	Click on New... to create a new ANDROID_HOME user variable that points to the path to your Android SDK:
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/sdk.jpg)  
3. Add platform-tools to Path <br />
1.	Open the Windows Control Panel. <br />
2.	Click on User Accounts, then click User Accounts again. <br />
3.	Click on Change my environment variables. <br />
4.	Select the Path variable. <br />
5.	Click Edit. <br />
6.	Click New and add the path to platform-tools to the list. <br />
The default location for this folder is: <br />
``%LOCALAPPDATA%\Android\Sdk\platform-tools`` <br />
## React Native Command Line Interface
React Native has a built-in command line interface. Rather than install and manage a specific version of the CLI globally, we recommend you access the current version at runtime using npx, which ships with Node.js. With npx react-native <command>, the current stable version of the CLI will be downloaded and executed at the time the command is run. <br />
The fakewallet app is a 'fake' Mobile Wallet Adapter compliant wallet. Install it on your Android emulator or device. It does not store persistent keypairs, and the wallet is "reset" each time the app is exited.<br />
### Installation steps <br />
2.	Clone the Mobile Wallet Adapter repo, containing the fakewallet app from the github repository <br />
``git clone https://github.com/solana-mobile/mobile-wallet-adapter.git`` <br />
4.	In Android Studio, Open project > Navigate to the cloned directory > Select mobile-wallet-adapter/android/build.gradle <br />
5.	After Android Studio finishes loading the project, select fakewallet in the build/run configuration dropdown in the top right <br />
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/fakewallet.jpg)  
6.	After it builds successfully, you should see the app on your Android device or emulator.<br />

# React Native dApp Setup<br />
Now you have setup Android Device/Emulator and  install a MWA-compatible wallet, like fakewallet. <br />
## Solana Mobile dApp Scaffold<br />
The fastest way to start building React Native on Solana is building off our React Native Template dApp: <br />
The scaffold is a ready-to-go React Native dApp that comes with:<br />
•	The Mobile Wallet Adapter SDK and @solana/web3.js.<br />
•	Required polyfills like react-native-get-random-values and Buffer installed.<br />
•	Wallet authorization/connecting and airdrop request functionality.<br />
•	Premade React UI Components like ConnectWalletButton, RequestAirdropButton, SignMessageButton.<br />
## Building Your first React Native dApp<br />
A complete React Native Solana dApp that allows the user to select a photo from their gallery and mint it as an NFT on the blockchain.
Prerequisites<br />
•	a running Android emulator or device to build and launch your app.<br />
•	an MWA-compatible wallet installed on the same device.<br />
•	an IDE/Editor of your choice.<br />
This tutorial will be using the fakewallet app to test your app's integration with Mobile Wallet Adapter.<br />
Clone the React Native dApp Scaffold<br />
This dApp will build off the React Native Scaffold dApp which already has a simple user interface that allows you to connect to a mobile wallet, request an airdrop, and sign transactions.<br />
Initialize a template app and Enter the directory and install the project dependencies.<br />
``npx react-native init FirstDappTutorial --template https://github.com/solana-mobile/solana-mobile-dapp-scaffold.git ``<br />
``cd FirstDappTutorial && yarn install`` <br />
Make sure your emulator/device is running, then build and launch the app.<br />
``npx react-native run-android``<br />
At this point, your app should build, install into your device, and launch automatically. You should also see the Metro Bundler console window pop up.<br />
### Scaffold dApp Components <br />
Now lets quickly go over the features of the dApp Scaffold.<br />
Connect Button<br />
Clicking on the Connect Wallet button will 'connect' you to a locally installed MWA-compatible wallet. It uses the Mobile Wallet Adapter SDK to request authorization from the wallet and receives your wallet account's info, like the public key.<br />
On click, it starts a wallet session with transact and calls authorizeSession from the AuthorizationProvider class.<br />
>     await transact(async wallet =>{<br />
    await authorizeSession(wallet);<br />
    });<br />
AuthorizationProvider is a helper class that manages wallet authorization. It calls `wallet.authorize()` on first connect, and for subsequent connects it re-uses the authToken in `wallet.reauthorize()`.<br />
>     const authorizeSession = useCallback(
    async (wallet: AuthorizeAPI & ReauthorizeAPI) => {
        const authorizationResult = await (authorization
        ? wallet.reauthorize({
            auth_token: authorization.authToken,
            identity: APP_IDENTITY,
            })
        : wallet.authorize({
            cluster: APP_CLUSTER,
            identity: APP_IDENTITY,
            }));
        console.log(authorizationResult);
        return (await handleAuthorizationResult(authorizationResult))
        .selectedAccount;
    },
    [authorization, handleAuthorizationResult],
     );
<br />
<b>Account Info</b><br />
This is a simple component takes a balance in lamports and converts it to units of SOL for display. <br />
Balance fetching<br />
In the `MainScreen.tsx` component, we fetch the user's wallet balance when it is available, and pass it into the AccountInfo component. To do so, we use the connection class and just call the getBalance function, which is part of the API spec.<br />
>     const {connection} = useConnection();
     const fetchAndUpdateBalance = useCallback(
    async (account: Account) => {
        const fetchedBalance = await connection.getBalance(account.publicKey);
        setBalance(fetchedBalance);
    },
    [connection],
     );<br />
<b>Airdrop Button</b><br />
This component takes in a user's wallet publicKey and requests an airdrop of lamports to that address on click. Again, we use the connection class and call the requestAirdrop RPC method, as part of the API spec.<br />
>     const requestAirdrop = useCallback(async () => {
       const signature = await connection.requestAirdrop(
        selectedAccount.publicKey,
        LAMPORTS_PER_AIRDROP,
    );
    return await connection.confirmTransaction(signature);
     }, [connection, selectedAccount]);<br />

<b>Sign Transaction/Message Button</b><br />
The SignMessageButton component takes in a messageBuffer byte array and calls wallet.signMessages(). This requests the connected wallet to sign the message with the user's private key.<br />
The SignTransactionButton component does several things on click. Within the wallet session, it constructs a Transaction with a SystemProgram.transfer instruction, then requests the wallet to provide a signature in the transaction.<br />

>     const signMessage = useCallback(
    async (messageBuffer: Uint8Array) => {
        return await transact(async (wallet: Web3MobileWallet) => {
        // First, request for authorization from the wallet.
        const authorizationResult = await authorizeSession(wallet);

        // Sign the payload with the provided address from authorization.
        const signedMessages = await wallet.signMessages({
            addresses: [authorizationResult.address],
            payloads: [messageBuffer],
        });

        return signedMessages[0];
        });
    },
    [authorizeSession],
     );
     const signTransaction = useCallback(async () => {
    return await transact(async (wallet: Web3MobileWallet) => {
        const connection = new Connection(clusterApiUrl('devnet'), 'confirmed');

        // First, request for authorization from the wallet and fetch the latest
        // blockhash for building the transaction.
        const [authorizationResult, latestBlockhash] = await Promise.all([
            authorizeSession(wallet),
            connection.getLatestBlockhash(),
        ]);

        // Construct a transaction. This transaction uses web3.js `SystemProgram`
        // to create a transfer that sends lamports to randomly generated address.
        const keypair = Keypair.generate();
        const randomTransferTransaction = new Transaction({
            ...latestBlockhash,
            feePayer: authorizationResult.publicKey,
        }).add(
        SystemProgram.transfer({
            fromPubkey: authorizationResult.publicKey,
            toPubkey: keypair.publicKey,
            lamports: 1_000,
        }),
        );

        // Sign a transaction and receive
        const signedTransactions = await wallet.signTransactions({
            transactions: [randomTransferTransaction],
        });

        return signedTransactions[0];
    }, [authorizeSession]);
     });

Now that we've gone over the existing scaffold, lets add some new functionality to it.<br />
<b>Let’s Build Mobile NFT Minter:-</b><br />
For this you need additional perquisite for the Dapp:- <br />
•	`@metaplex-foundation/js` for a client API to interact with on chain programs, for minting/creating NFTs. <br />
•	`IPFS` for a decentralized storage provider to host NFT image and metadata. <br />
<b>Install Metaplex JS SDK<b><br />
The next step is to install the `@metaplex-foundation/js` package. This is the Metaplex JS SDK that provides a developer friendly API to interact with onchain programs. <br />
``yarn add @metaplex-foundation/js`` <br />
The Metaplex JS SDK was originally written for a Browser/Node environment, so certain dependencies aren't immediately available on React Native. These polyfill libraries will fill in the missing libraries and enable React Native compatibility.<br />
>     yarn add \
    assert \
    crypto-browserify \
    readable-stream \
    zlib \
    react-native-url-polyfill
Add polyfills to resolver in `metro.config.js` <br />
Adding the resolver property lets the Metro know which packages to substitute with when seeing a require <br />
>     module.exports = {
    resolver: {
    extraNodeModules: {
      crypto: require.resolve('crypto-browserify'),
      stream: require.resolve('readable-stream'),
      zlib: require.resolve('browserify-zlib'),
      path: require.resolve('path-browserify'),
      url: require.resolve('react-native-url-polyfill'),
    },
       },
      transformer: {
    getTransformOptions: async () => ({
      transform: {
        experimentalImportSupport: false,
        inlineRequires: true,
      },
    }),
    },
    };
 Add imports to index.js
>     import 'react-native-url-polyfill/auto'; // Add this before the 'App' import!
      import {AppRegistry} from 'react-native';
      import App from './App';
      import {name as appName} from './app.json';
      AppRegistry.registerComponent(appName, () => App);<br />
<b>Install other dependencies</b><br />
In addition to the Metaplex JS SDK, the app will use several other libraries that handle other usecases, like file reading, IPFS, and others. Some of these are opinionated, so feel free to swap out a library with one of your choice.<br />
>     yarn install \
    rn-fetch-blob \
    react-native-image-picker \
    react-native-config \
    multiformats<br />
 <b>Launch the app </b><br />
`npx react-native run-android` <br />
At this point, your app should build, install into your device, and launch automatically.<br />

## How does minting work?<br />
The end to end procedure of minting a photo NFT roughly follows these steps:<br />
1.	Select a photo and upload it to a storage provider.<br />
2.	Upload a JSON object containing metadata that conforms to the Metaplex NFT Standard, to a storage provider.<br />
3.	Submit a transaction to the network that creates your NFT on chain.<br />

## Uploading to IPFS with NFT.storage
In this tutorial, we choose IPFS, a decentralized storage provider, to host the selected photo and the metadata object. <br />
We'll also be using `NFT.storage` to help upload directly to IPFS, through their HTTP API. You can sign up for a free API key on their website. <br />
### Selecting the photo
You need to select an existing photo from our gallery. To present a picker UI and retrieve the file path, use `launchImageLibrary` from the `react-native-image-picker` library.
>     import {launchImageLibrary} from 'react-native-image-picker';
     const photo = await launchImageLibrary({
    selectionLimit: 1,
    mediaType: 'photo',
    });
     const selectedPhoto = photo?.assets?.[0];
    if (!selectedPhoto?.uri) {
    console.warn('Selected photo not found');
    return;
     }
    const imagePath = selectedPhoto.uri;
### Upload the photo
Now that we have the image path, we need to upload the raw bytes of the file to IPFS, using the `NFT.storage /upload` endpoint.<br />

The steps:

Use the `rn-fetch-blob` library to read the image file into a Base 64 string.<br />
Convert to raw bytes by decoding the Base64 string with `Buffer`.<br />
Use `fetch` to send a request containing the image bytes to the upload endpoint.<br />

     // Read the image file and get the base64 string.
    const imageBytesInBase64: string = await RNFetchBlob.fs.readFile(
    imagePath,
    'base64',
    );

    // Convert base64 into raw bytes.
    const bytes = Buffer.from(imageBytesInBase64, 'base64');

    // Upload the image to IPFS by sending a POST request to the NFT.storage upload endpoint.
    const headers = {
    Accept: 'application/json',
    Authorization: `Bearer ${Config.NFT_STORAGE_API_KEY}`,
    };
    const imageUpload = await fetch('https://api.nft.storage/upload', {
    method: 'POST',
    headers: {
        ...headers,
        'Content-Type': 'image/jpg',
    },
    body: bytes,
    });

    const imageData = await imageUpload.json();
    console.log(imageData.value.cid);
If successful, the `imageData.value.cid` will contain a valid CID (Content Identifier). This is a string that uniquely identifies your uploaded asset.<br />

You can view your uploaded asset on an IPFS gateway by passing in the CID in the URL (e.g:` https://ipfs.io/ipfs/<cid>`). View an example of an uploaded photo on `ipfs.io`.<br />

### Uploading the metadata
Next, we need to construct a metadata object that conforms to the Metaplex NFT Standard, then upload it to the same /upload endpoint.<br />
Metadata fields: <br />

Name: The name of the NFT.<br />
Description: A description of the NFT.<br />
Image: A URL that hosts the photo. In this case, we use an ipfs.io URL with the CID of the uploaded photo.<br />

    // Construct the metadata fields.
    const metadata = JSON.stringify({ 
    name,
    description,
    image: `https://ipfs.io/ipfs/${imageData.value.cid}`,
    });
    // Upload to IPFS
    const metadataUpload = await fetch('https://api.nft.storage/upload', {
    method: 'POST',
    headers: {
        ...headers,
        'Content-Type': 'application/json',
    },
    body: metadata,
    });

    const metadataData = await metadataUpload.json();
    console.log(metadataData.value.cid);

If successful,` metadataData.value.cid` will now contain a CID that points to a JSON object representing the NFT metadata. View an example of an uploaded metadata object.

To recap, we now have two CIDs that are viewable on IPFS. First, the CID of our uploaded photo, and second, the CID of JSON Metadata (which has a reference to the photo CID in the `image` field).

## Precomputing the CID
You may notice in the example app, that during the upload step in `uploadToIPFS` we're able to precompute the CID of the photo asset before actually uploading it to IPFS. This is an optimization that allows us to construct and upload the metadata object, without waiting for the photo upload to complete and return the CID.

We take advantage of this by uploading both the photo and metadata asynchronously.
>     // Fire off both uploads aysnc
     return Promise.all([
    imageUpload.then(response => response.json()),
    metadataUpload.then(response => response.json()),
    ]);
To compute the CID from the bytes of a given asset, see the getCid function.

>     import {CID, hasher} from 'multiformats';
     const crypto = require('crypto-browserify');

    const SHA_256_CODE = 0x12;
    const IPLD_RAW_BINARY_CODE = 0x55;

    const getCid = async (bytes: Buffer) => {
    const sha256 = hasher.from({
    // As per multiformats table
    // https://github.com/multiformats/multicodec/blob/master/table.csv#L9
    name: 'sha2-256',
    code: SHA_256_CODE,
    encode: input =>
      new Uint8Array(crypto.createHash('sha256').update(input).digest()),
     });
     const hash = await sha256.digest(bytes);
     const cid = await CID.create(1, IPLD_RAW_BINARY_CODE, hash);

    return cid;
    };
## Minting the NFT
At this point we have completed the IPFS uploading steps and all that is left is to mint the NFT on chain. To do so, we'll use the Metaplex JS SDK.<br />

<b>Create a Metaplex Instance</>
To interact with Metaplex onchain programs, instantiate a `Metaplex` instance provided by the SDK.

Follow this section in the Metaplex guide, to create an MWA Identity Signer plugin. We'll need this so that the `Metaplex` instance will be able to request wallet signing through MWA.    
create the Metaplex instance with the useMetaplex hook.
``import useMetaplex from '../metaplex-util/useMetaplex';
const {metaplex} = useMetaplex(connection, selectedAccount, authorizeSession);``
## Create the NFT
With the `metaplex` instance, we can now access the `nfts()` module that provides a collection of functions that make it simple to interact with on chain programs and submit transactions.

To mint an NFT, call the `create` function which takes in a JSON object corresponding to the Token Metadata Standard.

This will prompt the user to sign a transaction using MWA, then submit the transaction to the specified RPC.

>     const {nft, response} = await metaplex.nfts().create({
    name: nftName,
    uri: `https://ipfs.io/ipfs/${metadataUploadData.value.cid}`,
    sellerFeeBasisPoints: 0,
    tokenOwner: selectedAccount?.publicKey,
    });

    console.log(nft.address.toBase58())
    console.log(response.signature)
## Launch the App    
Make sure your emulator/device is running, then build and launch the app.
`npx react-native run-android`
You DApp should be look like this
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/nftminter1.jpg)
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/nftminter2.jpg)
![Bird Eye View](https://github.com/adi99/Building-Mobile-Apps-on-Solana/blob/main/nftminter3.jpg)
    
