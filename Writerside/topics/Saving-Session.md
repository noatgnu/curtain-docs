# Saving Session

If you want to share or save your data and settings, you can do so by clicking `Session` -> `Save Session`. 
This will package your data and send to the backend server to be saved. The backend will generate a unique id for the session
and give you a link that you can share with others or save for later use.

After successfully saving the session, the link will appear at the top of the page as below. You can click on the blue icon to automatically copy the link to the clipboard.

![curtain_link_share.png](curtain_link_share.png)

If you click on the `QR Code` badge with yellow background, a QR code similar to the one below will appear and allow you to share your session on poster or presentation.

![qr_code.png](qr_code.png)

If you are logged in, the session will be saved to your account and you can access it later by clicking `Session` -> `Account`.

![account_session_bound.png](account_session_bound.png)

Here you can delete session that you have created or search for them by description.

If the user are the owner of the session, they can choose to change the status of the session from private to public or vice versa in `Session` -> `Session Settings`.

![session_settings.png](session_settings.png)

By default, if the user are not logged in, the session will be saved as a public session. Unless encrypted, anyone with the link can access the public session.

If the user are logged in, the session will be saved as a private session. Only the owner and website admin can access the data unless encrypted.

If the session is encrypted, the session will require a private key file to be decrypted. The private key need to be the counterpart of the public key that was used to encrypt the session. This mean that even admin cannot access the session if they do not have the exact private key.

In order to encrypt a session, you will need to generate a public key and a private key. You can do so by clicking `Session` -> `Encryption Settings`.

![encryption_settings.png](encryption_settings.png)

By clicking `Generate RSA Key Pair`, your browser will save two files, `public_key.pem` and `private_key.pem` to your download folder. You will need to keep the private key safe and secure as it is the only way to decrypt the session after it has been encrypted.

After generating the key pair, you can check `Enable encryption` to be able to import the key pair in the `Public Key` and `Private Key` file browser respectively. If you have imported the keys, you can check their respective save key in browser local storage to have the key be saved into the browser local storage if you do not want to import them everytime you visit the website.

Then you can click save to have have the encryption enforced or disabled based on the checkbox and imported keys.

A red badge with `Encryption Enabled` will appear on the top right of the menu bar if the session encryption is being enforced

![enforced_encryption.png](enforced_encryption.png)

This red badge will be showed on any page of any encrypted session.
