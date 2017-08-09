2FA as Time-based One-Time Password algorithm (TOTP), what most people referring to when speaking of Google Auth (Authy ...) are based in a algorithm (simplifying) where you take a private key (auth key), and using a agreed time (T0) you hash both the spent time since T0 and auth key together, after that you take the hash as a integer and get the 6 first numbers ... that ones that appear into the app. The logic is:

**totp_code = 2FA(auth key, T0);**

So to verify a 2FA key both the **ends need to hold the auth key**, since this is a decentralized project to be local that would mean the wallet itself need to hold the 2FA auth key, so it offers zero protection from an attacker, it could just read the auth key in storage. For 2FA to work, the auth key need to be stored in a safe and trustworthy remote server, and the decryption must be done in the server so that the encryption keys are not available at the compromised computer.

So, there is no 2FA in local crypto wallets because it offers zero protection, worse than that: it could transmit a false sense of protection.

We can and will do better to hold private keys, using a new developed NEO standard, called [NEP-2](https://github.com/neo-project/proposals/blob/nep-2/nep-2.mediawiki). There is ongoing efforts on this, but this will not be perfect also - you need a safe computer, if a attacker has the ability to attach a process in the OS it can read the decryption keys. The next best solution (CoZ is also working in a solution to that) is to have a safe and completely offline computer that signs the transactions that are latter relayed by a connected computer, then there is only the window of opportunity with the data transfer. This data transfer can be made secure, but the final setup will be very limiting.

You should keep the funds you aren't going to move in a paper wallet (generate one and print the key and address), keep this paper safe, and transfer to the correspondent address - use a block explorer to monitor it assets (there is no need to use the private key in a wallet, a wallet is just a window that examines the blockchain and computes your balances, it don't hold values).
