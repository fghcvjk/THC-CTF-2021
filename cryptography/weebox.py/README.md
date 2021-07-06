
# weebox.py

Usage:

```py
% python weebox.py weeeehihihihi
signature: 4ce5e78c681c34e316bb13ef3d57d3b18a7902f3f941638f4e6620ef0be0ad92ad3825e2461e3060edac7fc1189c78ca35637d242ac20a913788120f72b76571
public key: 9274d0bb1bd842d732a3ddc415032e45efa0130d8140a4fa77e67e284224968e
```

Once extracted, the flag is the private key deciphered with the AES null key:
```
from cryptography.hazmat.primitives.ciphers import Cipher, algorithms, modes

cipher = Cipher(algorithms.AES(bytes(32)), modes.ECB())
decryptor = cipher.decryptor()
print(decryptor.update(private_key) + decryptor.finalize()) # THCon21{.......................}
```

Made with love by Quarkslab™ :)
