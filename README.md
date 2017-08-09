Why there is no 2FA for the NEON Wallet
================
2FA as a Time-based One-Time Password (TOTP), the thing most people refer to when speaking of Google Auth, is based in an algorithm where you take a private key (auth key) that is hashed together with the time since an agreed time (T0). After that you take the hash as an integer and use the 6 first numbers; the ones that appear in the app. The logic is as follows:

**totp_code = 2FA(auth key, T0);**

So in order to verify a 2FA TOTP **both ends need to hold the auth key**. Since this is a decentralized project, that would mean the wallet itself needs to hold the 2FA key, offering zero protection from an attacker, who could just read the auth key from the storage. For 2FA to work, the auth key needs to be stored in a safe and trustworthy remote server where the decryption must be done, so that the encryption keys are not available at the (possibly) compromised computer.

**So: there is no 2FA in local crypto wallets because, not only does it offer zero protection; it could transmit a false sense of protection.**

We can and will do better to hold private keys, using a new developed NEO standard, called [NEP-2](https://github.com/neo-project/proposals/blob/nep-2/nep-2.mediawiki). There are ongoing efforts on this front, but this method will also not be perfect - you need a safe computer. If an attacker has the ability to attach a process in the Operating System, it can read the decryption keys. The next best solution, and one City of Zion is working on, is to have a safe and completely offline computer that signs the transactions that are later relayed by a connected computer. This way, the only window of opportunity would be the data transfer. This data transfer can be made more secure, but the final setup will be very limiting and not many people will be able to use it.

Best practice
----
You should keep the funds you aren't going to move anytime soon in a paper wallet (generate one [here](https://snowypowers.github.io/ansy/) and print the key and address). Keep this paper safe, and transfer to the corresponding address. Use a block explorer to monitor its assets; there is no need to use the private key in a wallet, since a wallet is just a window that examines the blockchain and computes your balances; it does not actually hold anything.

Please help improve this post: https://github.com/canesin/2fa_explanation
