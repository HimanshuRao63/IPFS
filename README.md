# IPFS
# IPFS Practical - Uploading a File to IPFS

## IPFS Installation

I downloaded and installed **IPFS Desktop for Windows** from the official website:  
🔗 [https://docs.ipfs.tech/install/ipfs-desktop/](https://docs.ipfs.tech/install/ipfs-desktop/)

## IPFS Setup

After the installation, I opened the IPFS Desktop application.  
The IPFS node connected automatically, and the status showed as **Online**.

![Screenshot 2025-04-08 161601](https://github.com/user-attachments/assets/20c8981f-cbb8-4a6d-8ff7-026e4df0d58b)

## File Upload

To upload a file:

1. I navigated to the **Files** section within IPFS Desktop.
2. Then, I clicked on the **Import** button.
3. I uploaded a few sample files – including a **SQL Notes**.

Once uploaded, IPFS automatically generated a unique **CID (Content Identifier)** for each file.

 ![Screenshot 2025-04-08 161448](https://github.com/user-attachments/assets/431be20b-f039-49fa-a7a5-0a5262d29bbb)
![Screenshot 2025-04-10 203333](https://github.com/user-attachments/assets/1d5bf6cf-0987-4eec-b86c-6add6c968b84)

# Assignment 5: IPFS Privacy and Encryption
This assignment demonstrates how to use the InterPlanetary File System (IPFS) along with OpenSSL to perform file encryption and ensure privacy via the command line.

# Steps
# 1. Create a file to be added to IPFS
```

echo "Hello, IPFS!" > myfile.txt
```
<br>

# 2.Add the original file to IPFS
```

ipfs add myfile.txt
```
# 3.Encrypt the file using OpenSSL (AES-256-CBC)
```

openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:yourpassword
```
# 4.Add the encrypted file to IPFS
```

ipfs add myfile_encrypted.txt
```
# 5.View the encrypted file (optional)
```

cat myfile_encrypted.txt
```
# 6.Decrypt the file
```

openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:yourpassword
```
# 7.Verify the decrypted file content
```

cat decrypted_file.txt
```
# 8.Add the decrypted file to IPFS
```

ipfs add decrypted_file.txt
```

![Screenshot 2025-05-18 163525](https://github.com/user-attachments/assets/df525435-ef5e-40d8-809b-b6bfbadcd9a2)


# Notes
● Replace `yourpassword` with a strong, secure password of your choice.
<br>
● Ensure that IPFS is properly installed and initialized before running these commands.
