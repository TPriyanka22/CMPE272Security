Below are the Steps followed to build PKI infrastructure that includes Root CA, Signing CA and TLS certificate:
•	Firstly clone the repo into a new directory ‘pki-example’ using the below command

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201594150-e6cf5247-d9e9-4a58-85b1-1b490ad07f54.png">

1.	Create Root CA :

1.1	Create directories: Create the directories as shown in the below screenshot 


<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201594199-db81f0bc-3193-4859-b09d-41acae50ec01.png">

And also checked that the CA directory holds CA resources, the crl directory holds CRLs and the certs directory hold user certificates.

1.2	Create Database :  Created the database and made sure that database files exist as shown in the above screenshot.

1.3	Create CA Request : Here we create a private key and certificate signing request for the root CA and also enter the passphrase when prompted.

<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594254-55a7b9ac-ebf9-49a6-af64-b50ecf190da4.png">

<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594336-d42be33f-bcaf-43d3-8e2e-a8c6f192c727.png">

1.4	Create CA certificate: With the command given below we issue a root CA certificate based on the CSR.![image](https://user-images.githubusercontent.com/111544172/201594425-0345d991-8bc7-46eb-8963-c29fd851445a.png)

<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594505-c5cf2565-a592-494c-80c4-d133df129719.png">

<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594525-2b22ae36-80c2-4c9e-bf5e-f42364959f18.png">


2.	Create Signing CA

2.1 Create Directories: The CA directory holds the CA resources and crl directory holds CRLs.
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201594626-8fb9c9d1-d26b-416a-8877-95e894d28323.png">

2.2 Create Database: Database files are created with the following command:
<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594671-cd651026-25c6-449c-a768-c69d977b0b9f.png">

2.3 Create CA request: With the below command, we create a private key and CSR for the signing CA.
<img width="470" alt="image" src="https://user-images.githubusercontent.com/111544172/201594716-2abf3abf-2798-49bf-aace-b2d129e79c8f.png">

2.4 Create CA certificate: With the command given below, certificate is issued based on the CSR
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201594934-27c9220d-b56e-446b-845d-9c407ca7ad8b.png">


3.	Operate Signing CA
3.1 Create Email request: With the OpenSSL req new command, private key and CSR are created for an email – protection certificate and also enter the domain components.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201596895-83d6a3ff-5e4d-4298-bb50-65e8c93aadcc.png">

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201596912-245605f7-7fc8-4c4b-9fee-b5a2d5664fe1.png">

3.2 Create Email Certificate: Here we are using signing ca to issue the email – protection certificate. 

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201596965-3a54e6a1-a912-4970-b013-1622d55a9229.png">


<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201596984-bc31bbf5-2ef0-4540-8dcf-704ebe701b29.png">

3.3 Create TLS server request: Here we create a private key and CSR for TLS – Server certificate and enter the domain components when prompted.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201597058-513675d7-0c12-4b69-9051-5533d5517659.png">

3.4  Create TLS server certificate: Here we issue a server certificate using signing CA.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604311-f5b4e176-b41b-44d7-9391-bd19d2411619.png">

3.5 Revoke Certificate: The command used below will help to revoke the certificate.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604402-add22128-8907-4bc7-9190-df3e40ec6223.png">

3.6 Create CRL: The command below helps to create a Certification Revocation List.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604505-39ad9c93-a3af-403a-af7b-392fb0a973ef.png">

4.	Output Formats
4.1 Create DER certificate: All the published certificates will be in DER format 
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604814-57b03195-95b5-48ae-afed-9248b91f3e59.png">

4.2 Create DER CRL: All the published CRLs must be in DER Format.![image](https://user-images.githubusercontent.com/111544172/201604829-0fcc20d0-5f10-4719-8c6a-dabf1df705a2.png)
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604877-1c14e9a6-2553-4872-a35b-cc66a9db0ef0.png">

4.3 Create PKCS#7 bundle: Here we can bundle two or more certificates!
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201604965-514507c6-bbd7-4b6c-a02c-f6a9f506f8ef.png">

4.4 Create PKCS#12 bundle: Is used to bundle a certificate and private key.
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201605434-0f78a487-c905-4936-8d9e-c566e97d099b.png">

4.5 Create PEM bundle: These bundles are created by combining other PEM files.
<img width="468" alt="image" src="https://user-images.githubusercontent.com/111544172/201605545-6b718551-4c3f-4288-bfec-5b36bb4c12b3.png">





















