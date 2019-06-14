# ZEC - Zepio Cold Storage 
### on a password protected, AES encrypted, hidden volume, cold storage USB 

This is a method to store your ZEC wallet on a password protected, AES encrypted, hidden volume, cold storage USB. This guide will use Mac or Windows & the Zepio wallet which will can run a full ZEC node and utilize shielded addresses. 

When I first installed the ZECwallet & then Zepio on my desktop, I was unsettled that the wallet was not protected with a password or seed phrase. The wallet file being stored on my local machine is all anyone needs to access my ZEC. I also have a ledger but I'm unable to use shielded addresses or run a full node using it, among other hardware/software issues.


## What you'll need (the hardware/software I will be focusing on): 
1. Computer - Windows or Mac
2. ZEPIO wallet software - https://zepiowallet.com/ (ZECWALLET also works)
3. VeraCrypt encryption software - https://www.veracrypt.fr/en/Downloads.html
      If using a Mac then you'll also need to install OSXFuse as noted on the VeraCypt website
4. USB drive
	You'll want to get one with at least 50+ GB for blockchain storage. I'm using a 126GB USB drive for future storage needs.

## Installation & Configuration Steps:

1. Set up VeraCrypt encrypted USB - 

Format your drive for your OS if it is not already done so. 

Install & Open VeraCrypt, select "Create a volume within a partition or drive" (2nd option).

Next select "Create a Volume" > select "Standard or Hidden volume" (2nd option).

I would recommend creating an entire hidden VeraCrypt volume as I described. This creates an outer and inner volume and allows for plausible deniability of the data. This way, if you are somehow forced to open this volume for someone for any reason be it LE or extortion, etc. - you can provide them the password for the outer volume (honey pot) and they cannot prove that anything else is installed on that drive.

Follow the prompts for encryption, selecting AES (or whatever your preference) and setting up a password for the Outer Volume.

Once the Outer volume is complete, open it and add a few non-confidential files that look like they may be of importance. You can go as far as to set up a brand new wallet and add those private keys or other details in there for plausible deniablility.

Next continue the prompt and select create inner hidden volume. Follow the prompts as before to create and password protect this inner volume. Be sure to select a correct size for the inner volume that you'll need (and be sure to change the size to GB instead of MB).

You can select whether to make the VeraCrypt volume cross platform (which may require third party software to access from another platform) and if you're going to store files larger than 4GB (in this case we will). 

Once created, you can open either drive by connecting your USB & opening Veracrypt. Select "Mount All Devices" in VeraCrypt and type the password for the drive you wish to access. It may take up to 5 minutes to fully connect. 


2. Set up Zepio on your OS (if it is already set up then skip to b. move files & configure to use new wallet dir)

	a. Install Zepio and upon first opening, configure your wallet dir (matador) to use your connected encrypted drive. It should create a new folder within your encrypted drive and will only be accessible from Zepio when the USB be is connected and the VC drive has been mounted.


	b. If you already have Zepio installed, make sure the app is closed. Open your encrypted drive and your current zecwallet dir. You can find this dir by finding your zcash.conf file and checking the directory listed there. Copy all files over to your encrypted drive (and keep your old one until you know it is working from the new USB). Next open your zcash.conf file and update the datadir to point to your encrypted drive. On a Mac, it would be something like "/Volumes/DRIVENAME/zecwallet". Once the files are copied over, and zcash.conf file is updated then you can open Zepio and let it resync any blocks it needs to. You are now running your Zepio ZEC wallet/full node with shielded addresses from an encrypted, password protected, cold storage USB.

