# Xchain
> _Encrypt Files with Shared Keys_

I've heard lots of stories about special key ceremonies in corporations, where physical or software keys get handed out to a group of people, so that the lock or the encrypted file can only be retrieved back if all the shared keys are placed together. This may seem like an extra-step of security for individuals because it unnecessarily increases the time of getting the original file back, but you have to admit that the idea is rather cool.

**For example imagine the following scenario:**  
You create a deadswitch and encrypt a file with shared keys and send them to a group of people. When the deadswitch gets activated (hopefully not) the script makes the encrypted file available and notifies the keyholders. Now, those people can gather together to decrypt the encrypted file and be sure that the file wasn't modified. You got the idea.

The algorithm is actually very basic. `xchain` generates cryptographically secure random bit sequences using the `secrets` library from python's standard library and uses the `XOR` operation to create a chain of keys. It starts by reading the input file in binary mode. Then, it generates a random key with the `same length as the input file` and uses the xor operation on the input file and the key. We take the result with the key and add it to a keys list. Now, we can iteratively generate a new key, xor it with the last key in the list, remove the last key in the list and add the newly generated key and the result of the xor operation to the keys list. This way we can increase the number of shared keys by 1 on each step.

The encryption also stores the basename of the file `e.g. main.py` and adds to the beginning of the input file as a 256 character header. After decrypting the keys, the script can use the `first 256 characters` of the decrypted data to save the file in the correct form.

XChain has a graphical user interface and uses GTK3. Here are some screenshots:

<img class="img-fluid" src="https://raw.githubusercontent.com/kgbzen/archive/main/images/xchain_1.png">
<img class="img-fluid" src="https://raw.githubusercontent.com/kgbzen/archive/main/images/xchain_2.png">
<img class="img-fluid" src="https://raw.githubusercontent.com/kgbzen/archive/main/images/xchain_3.png">

You can check the latest release yourself and as always, you can find the source code down below.

* [Latest Release](https://github.com/kgbzen/xchain-pub/releases)
* [Source Code](https://github.com/kgbzen/xchain-pub)

---
Feel free to [email me](mailto:kaangiray26@protonmail.com) your comments!
