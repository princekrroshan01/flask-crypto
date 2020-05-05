# flask-hedcrypt
     
      
  	A flask extension which provide interface( set of APIs) having implemenation of some of the use cases of cryptography.  
      
      
      
**features**
-----------

*  Key Derivation in accordance with PKCS7.
*  The derived key is used as a password. 
*  Derived Key is always inserted in every file you upload onto the server into the metadata of file(currently only pdf encryption is tested manualy)
*  No one is ever able to see the files (e.g documents) except you as the file is stored as an encrypted file onto the server.
*  You can use the APIs like key_derive and key_verify for password. But you also had an option to decerote the Model class in future for that you  had to provide ssid and username into the model so that a key is derived from it (use this method if you want to use more funtionality of the extension).


**Prerequisites**
------------------

know how to use flask extensions
<br>
pip3 install -r requirements.txt



**using** 
--------  

 Currently under developement <br>
 Welcoming you all to contribute in any possible way.
 Please have a look at the todo.  

 
	    git clone https://github.com/princekrroshan01/flask-hedcrypt/
	    cd flask-hedcrypt
	    virtualenv venv
	    source venv/bin/activate
	    pip install -r requirements.txt

 <br>
 For now

 Key Derivation and Verification APIs
 ```
       from flask import Flask
       app=Flask(__name__)
       from flask_crypto.flask_crypto import Crypto
       crpt=Crypto(app)
       #api to calculate key using PKCS7
       key=crpt.key_derive(b'data')
       #api to verify the key 
       crpt.key_verify(b'data', key)
 
 ```
 File Encryption and Decryption APIs (currently only text,pdf ,...) 

 ```
      from flask_crypto.file_encryt_decrypt import FileEncryptDecrypt
      file_ecd=FileEncryptDecrypt(key)
      #api to encrypt file
      file_edc.encrypt_file(file/path/to/encrypt)
      #api to decrypt file
      file_edc.encrypt_file(file/path/to/decrypt)

 ```
 
    
**TODO**
---------

- [ ] write configuration parameters for the extension.
- [x] file encryption and decryption support using symmetric key encryption
- [ ] API for PGP(preety good privacy)
- [ ] coming up with the use case for API support to use asymmetric key encryption
- [ ] write UnitTest for file encryption and decryption
- [ ] Writing deceroter class for flask-sqlalchemy model class.
- [ ] Store Derived Key in metadata of the every file uploaded (For now PDF files). 

**Contributing**
----------------
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


