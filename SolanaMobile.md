# Building Mobile Apps on Solana
Solana Mobile Stack (SMS) is an open-source development toolkit that enables developers to build rich web3 applications natively on Android mobile devices, running on the Solana blockchain12. As a software development kit (SDK), SMS provides libraries and interfaces that enable any developer to build Solana-powered applications on Android-compatible devices. Components of SMS SDK:-
<br />•	Seed Vault: A secure environment built into a mobile device that keeps private keys, seed phrases, and secrets separated from the application layer yet still capable of interacting with apps running on the device or in a mobile browser. It accesses the highest privileged security environment available on a device, from secure operating modes of the processor to dedicated Secure Elements, which enables a secure transaction signing experience through UI components built into Android.
•	Mobile Wallet Adapter: A protocol for connecting web apps and native Android apps to wallets on mobile devices3. The open-source protocol is designed to support all mobile platforms, not just Android, and can work with wallet apps providing signing services to apps running remotely, such as other mobile devices, and on desktop or laptop computers3.
•	Solana Pay: Solana Pay is a decentralized payment rail that runs on Solana. Since it is embedded in the Solana Mobile SDK, mobile wallet apps will be able to use the system features of Android phones to allow payments through QR codes, NFT taps, messages, etc.
•	dApp Store: The dApp store is now open for app submissions. It allows easy dApp submission and distribution4.
•	Saga: Solana Mobile teamed up with OSOM to integrate the Solana Mobile Stack with a flagship quality device, Saga4. Saga delivers premium hardware, clean Android, and Web3 in a phone you’ll love to use. It has a 6.67” OLED Display, 512 GB Storage, 12 GB RAM.
The Solana Mobile Stack shows a new path forward on Solana that is open source, secure, optimized for web3, and easy to use. Developers can now bring the power of Solana to the computers in our pockets, not just our backpacks.
Mobile dApp Architecture Overview
Bird’s Eye view of Mobile DApp’s interaction with mobile wallet and Solana Network.
The Mobile Wallet Adapter (MWA) protocol is what defines the communication exchange between a dApp and a mobile wallet. In the protocol, the dApp sends requests (i.e: authorization or signing), while the wallet is responsible for displaying these requests to the user and responding to the dApp if approved.
Development Setup
Before starting you need the following perquisite for Android Mobile Development:-
Install Android Studio:- You need to install Android Studio to build apps and manage your device/emulator.  While on Android Studio installation wizard, make sure the boxes next to all of the following items are checked:
•	Android SDK
•	Android SDK Platform
•	Android Virtual Device
1-	Setup Device/Emulator:- To test and preview your app as you develop, you can build and deploy your app to an Android device or emulator in Android Studio
2-	Install a wallet App:- The Mobile Wallet Adapter (MWA) library allows your dApp to connect and interface with Wallet Apps that implement the MWA protocol. For testing, you want to have an MWA-compatible wallet on the same device or emulator as your dApp.
The fakewallet app is a 'fake' Mobile Wallet Adapter compliant wallet. Install it on your Android emulator or device. It does not store persistent keypairs, and the wallet is "reset" each time the app is exited.
Installation steps
1.	Clone the Mobile Wallet Adapter repo, containing the fakewallet app from the GitHub repository
git clone https://github.com/solana-mobile/mobile-wallet-adapter.git
2.	In Android Studio, Open project > Navigate to the cloned directory > Select mobile-wallet-adapter/android/build.gradle
3.	After Android Studio finishes loading the project, select fakewallet in the build/run configuration dropdown in the top right
 
4.	After it builds successfully, you should see the app on your Android device or emulator.
Install real wallet apps:- fakewallet was created for implementation reference and quick testing purposes. You should also test your dApp with popular MWA-compatible wallet apps like Phantom, Solflare, and Ultimate.
 If you're planning on developing with React Native, then follow the following prerequisite:- 
If you are new to mobile development, the easiest way to get started is with Expo Go. Expo is a set of tools and services built around React Native and, while it has many features, the most relevant feature for us right now is that it can get you writing a React Native app within minutes but it only includes native modules. If you are building production-level Dapp, you need a specific tool that might not be available in Expo Go.
Perquisite:-
Node, JDK (java Development Kit):-
It is recommended to use an LTS version of Node. React Native also requires Java SE Development Kit (JDK).
choco install -y nodejs-lts microsoft-openjdk17

1. Install Android Studio
Download and install Android Studio. While on Android Studio installation wizard, make sure the boxes next to all of the following items are checked:
•	Android SDK
•	Android SDK Platform
•	Android Virtual Device
Configure the ANDROID_HOME environment variable
The React Native tools require some environment variables to be set up in order to build apps with native code.
1.	Open the Windows Control Panel.
2.	Click on User Accounts, then click User Accounts again
3.	Click on Change my environment variables
4.	Click on New... to create a new ANDROID_HOME user variable that points to the path to your Android SDK:
 
 Add platform-tools to Path
1.	Open the Windows Control Panel.
2.	Click on User Accounts, then click User Accounts again
3.	Click on Change my environment variables
4.	Select the Path variable.
5.	Click Edit.
6.	Click New and add the path to platform-tools to the list.
The default location for this folder is:
%LOCALAPPDATA%\Android\Sdk\platform-tools
React Native Command Line Interface
React Native has a built-in command line interface. Rather than install and manage a specific version of the CLI globally, we recommend you access the current version at runtime using npx, which ships with Node.js. With npx react-native <command>, the current stable version of the CLI will be downloaded and executed at the time the command is run.
The fakewallet app is a 'fake' Mobile Wallet Adapter compliant wallet. Install it on your Android emulator or device. It does not store persistent keypairs, and the wallet is "reset" each time the app is exited.
Installation steps
2.	Clone the Mobile Wallet Adapter repo, containing the fakewallet app from the github repository
git clone https://github.com/solana-mobile/mobile-wallet-adapter.git
4.	In Android Studio, Open project > Navigate to the cloned directory > Select mobile-wallet-adapter/android/build.gradle
5.	After Android Studio finishes loading the project, select fakewallet in the build/run configuration dropdown in the top right
 
5.	After it builds successfully, you should see the app on your Android device or emulator.

![image](https://github.com/adi99/Building-Mobile-Apps-on-Solana/assets/6312889/404e7130-4798-4ec4-8a49-6f0b26f1e9ed)
React Native dApp Setup
Now you have setup Android Device/Emulator and  install a MWA-compatible wallet, like fakewallet.
Solana Mobile dApp Scaffold
The fastest way to start building React Native on Solana is building off our React Native Template dApp:
The scaffold is a ready-to-go React Native dApp that comes with:
•	The Mobile Wallet Adapter SDK and @solana/web3.js.
•	Required polyfills like react-native-get-random-values and Buffer installed.
•	Wallet authorization/connecting and airdrop request functionality.
•	Premade React UI Components like ConnectWalletButton, RequestAirdropButton, SignMessageButton.
Building Your first React Native dApp
A complete React Native Solana dApp that allows the user to select a photo from their gallery and mint it as an NFT on the blockchain.
Prerequisites
•	a running Android emulator or device to build and launch your app.
•	an MWA-compatible wallet installed on the same device.
•	an IDE/Editor of your choice.
This tutorial will be using the fakewallet app to test your app's integration with Mobile Wallet Adapter.
Clone the React Native dApp Scaffold
This dApp will build off the React Native Scaffold dApp which already has a simple user interface that allows you to connect to a mobile wallet, request an airdrop, and sign transactions.
Initialize a template app and Enter the directory and install the project dependencies.
npx react-native init FirstDappTutorial --template https://github.com/solana-mobile/solana-mobile-dapp-scaffold.git
cd FirstDappTutorial && yarn install
Make sure your emulator/device is running, then build and launch the app.
npx react-native run-android
At this point, your app should build, install into your device, and launch automatically. You should also see the Metro Bundler console window pop up.
Scaffold dApp Components
Now lets quickly go over the features of the dApp Scaffold.
Connect Button
Clicking on the Connect Wallet button will 'connect' you to a locally installed MWA-compatible wallet. It uses the Mobile Wallet Adapter SDK to request authorization from the wallet and receives your wallet account's info, like the public key.
On click, it starts a wallet session with transact and calls authorizeSession from the AuthorizationProvider class.
await transact(async wallet => {
    await authorizeSession(wallet);
});
AuthorizationProvider is a helper class that manages wallet authorization. It calls wallet.authorize() on first connect, and for subsequent connects it re-uses the authToken in wallet.reauthorize().
const authorizeSession = useCallback(
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
Account Info
This is a simple component takes a balance in lamports and converts it to units of SOL for display.
Balance fetching
In the MainScreen.tsx component, we fetch the user's wallet balance when its available, and pass it into the AccountInfo component. To do so, we use the connection class and just call the getBalance function, which is part of the API spec.
const {connection} = useConnection();
const fetchAndUpdateBalance = useCallback(
    async (account: Account) => {
        const fetchedBalance = await connection.getBalance(account.publicKey);
        setBalance(fetchedBalance);
    },
    [connection],
);
Airdrop Button
This component takes in a user's wallet publicKey and requests an airdrop of lamports to that address on click. Again, we use the connection class and call the requestAirdrop RPC method, as part of the API spec.
const requestAirdrop = useCallback(async () => {
    const signature = await connection.requestAirdrop(
        selectedAccount.publicKey,
        LAMPORTS_PER_AIRDROP,
    );
    return await connection.confirmTransaction(signature);
}, [connection, selectedAccount]);
Sign Transaction/Message Button
The SignMessageButton component takes in a messageBuffer byte array and calls wallet.signMessages(). This requests the connected wallet to sign the message with the user's private key.
The SignTransactionButton component does several things on click. Within the wallet session, it constructs a Transaction with a SystemProgram.transfer instruction, then requests the wallet to provide a signature in the transaction.
const signMessage = useCallback(
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

Now that we've gone over the existing scaffold, lets add some new functionality to it.
Let’s Build Mobile NFT Minter:-
For this you need additional perquisite for the Dapp:-
•	@metaplex-foundation/js for a client API to interact with on chain programs, for minting/creating NFTs.
•	IPFS for a decentralized storage provider to host NFT image and metadata.
Install Metaplex JS SDK
The next step is to install the @metaplex-foundation/js package. This is the Metaplex JS SDK that provides a developer friendly API to interact with onchain programs.
yarn add @metaplex-foundation/js
The Metaplex JS SDK was originally written for a Browser/Node environment, so certain dependencies aren't immediately available on React Native. These polyfill libraries will fill in the missing libraries and enable React Native compatibility.
yarn add \
    assert \
    crypto-browserify \
    readable-stream \
    zlib \
    react-native-url-polyfill
Add polyfills to resolver in metro.config.js
Adding the resolver property lets the Metro know which packages to substitute with when seeing a require
module.exports = {
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
import 'react-native-url-polyfill/auto'; // Add this before the 'App' import!
import {AppRegistry} from 'react-native';
import App from './App';
import {name as appName} from './app.json';
AppRegistry.registerComponent(appName, () => App);
Install other dependencies
In addition to the Metaplex JS SDK, the app will use several other libraries that handle other usecases, like file reading, IPFS, and others. Some of these are opinionated, so feel free to swap out a library with one of your choice.
yarn install \
    rn-fetch-blob \
    react-native-image-picker \
    react-native-config \
    multiformats
4. Launch the app
npx react-native run-android
At this point, your app should build, install into your device, and launch automatically.

How does minting work?
The end to end procedure of minting a photo NFT roughly follows these steps:
1.	Select a photo and upload it to a storage provider.
2.	Upload a JSON object containing metadata that conforms to the Metaplex NFT Standard, to a storage provider.
3.	Submit a transaction to the network that creates your NFT on chain.




