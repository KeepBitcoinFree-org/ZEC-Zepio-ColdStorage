# ZEC - Zepio Cold Storage solution
### A password protected, AES encrypted, hidden volume, cold storage USB drive

When I first installed the ZECwallet & then Zepio on my desktop, I was a little unsettled that the wallet was not protected with a password or seed phrase. The wallet file, being stored on my local machine, is all anyone needs to access all the ZEC in the wallet. I also have a ledger but I'm unable to use shielded addresses or run a full node with it. This guide can also be found at: https://github.com/jigsawcrew/ZEC-Zepio-ColdStorage

This is a method to store your ZEC wallet on a password protected, AES encrypted, hidden volume, cold storage USB. This guide will use Mac or Windows & the Zepio wallet which will run a full ZEC node and utilize shielded addresses.


## What you'll need (the hardware/software I will be focusing on): 
1. Windows or Mac OS
2. ZEPIO wallet software - https://zepiowallet.com/ (ZECWALLET also works)
3. VeraCrypt encryption software - https://www.veracrypt.fr/en/Downloads.html (On Mac you'll also need to install OSXFuse as noted on the VeraCrypt website)
4. USB drive - Get one with at least 50+ GB for blockchain storage. I'm using a 126GB USB drive for future storage needs.

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

Once created, you can open either drive by connecting your USB & opening Veracrypt. Select "Mount All Devices" in VeraCrypt and type the password for the drive you wish to access. It may take up to 5 minutes to finish mounting the device and it may seem unresponsive during that time.

      2.    (a) Set up Zepio on your OS or (b) configure already installed Zepio to use your encrypted USB 

a.  Download & install Zepio. When first opening & setting it up, configure your wallet directory (datadir) to use your connected encrypted drive. Zepio should then create both a Zcash folder on your local machine (that stores your zcash.conf file) & a zecwallet folder within your encrypted drive to store your wallet. Your funds will only be accessible from Zepio when the USB  is connected and the VeraCrypt drive has been mounted. If you have any issues here then go to the next step and check the zcash.conf file for the path to your datadir.

b.  If you already have Zepio installed, you'll need to copy your files to the USB & point your zcash.conf file to this new directory. First make sure Zepio is closed. Open your encrypted drive and your current zecwallet dir. You can find this dir by finding your zcash.conf file and checking the directory listed there. Copy all  zecwallet files over to your encrypted drive (and keep your old one until you know it is working from the new USB). Next open your zcash.conf file and update the datadir to point to your encrypted drive. On a Mac, it would be something like "/Volumes/DRIVENAME/zecwallet". Once the files are copied over, and the zcash.conf file is updated then you can open Zepio and let it resync any blocks it needs to. You are now running your Zepio ZEC wallet/full node with shielded addresses from an encrypted, password protected, cold storage USB.

*Bonus: get another small USB and install another VeraCrypt hidden volume in order to store your wallet.dat file separately for backup purposes. If you lose this file, you lose your funds as far as I know. Let me know if you have any comments or questions!
