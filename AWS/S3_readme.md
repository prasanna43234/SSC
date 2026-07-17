SSS  
<img width="1918" height="778" alt="image" src="https://github.com/user-attachments/assets/f60a7fff-c3b0-43cb-a6bd-6c918260edf1" />
<img width="1843" height="737" alt="image" src="https://github.com/user-attachments/assets/fd6a6c04-9ba2-4e0d-89dd-34db2e8e11ce" />
<img width="1868" height="748" alt="image" src="https://github.com/user-attachments/assets/09e4a0f2-1021-4b1c-a06c-dc59b7334643" />
<img width="1877" height="623" alt="image" src="https://github.com/user-attachments/assets/7095f359-3dab-4b18-9668-24d448a387d7" />
<img width="1887" height="746" alt="image" src="https://github.com/user-attachments/assets/fb632bdf-ceba-4fda-b358-32a76e1b0238" />
<img width="1902" height="673" alt="image" src="https://github.com/user-attachments/assets/7a866758-7a80-4646-be5b-b6f0f246a72c" />
<img width="1888" height="755" alt="image" src="https://github.com/user-attachments/assets/51415fe3-28ed-4b5a-ab53-0bde07b715fd" />
<img width="1877" height="730" alt="image" src="https://github.com/user-attachments/assets/40ff3933-da4c-4d15-a121-7d8a9b355426" />
<img width="1890" height="550" alt="image" src="https://github.com/user-attachments/assets/d8864317-2c07-4812-9d95-b3bf14ddb7d7" />
<img width="1877" height="496" alt="image" src="https://github.com/user-attachments/assets/9ab49ae1-064b-4952-8171-8a606757a355" />
<img width="1888" height="797" alt="image" src="https://github.com/user-attachments/assets/fdb54d95-187c-4e40-890c-2f9810a4de29" />
<img width="1890" height="655" alt="image" src="https://github.com/user-attachments/assets/e796d320-8e67-48e3-95d2-b3e0dbe8cf7f" />
https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html?icmpid=docs_amazons3_console#example-bucket-policies-anonymous-user
<img width="1888" height="750" alt="image" src="https://github.com/user-attachments/assets/69ce0410-720c-4dec-bd7e-b1e1e63317c1" />
<img width="1902" height="732" alt="image" src="https://github.com/user-attachments/assets/aa3eb61f-2afc-415c-a7b6-610c36d00f85" />
<img width="1897" height="702" alt="image" src="https://github.com/user-attachments/assets/1fa6f1c0-c520-45c0-9a70-f58b4745ab46" />
<img width="1915" height="702" alt="image" src="https://github.com/user-attachments/assets/e58a1436-64e0-4051-acdb-939d8a560073" />
<img width="1902" height="620" alt="image" src="https://github.com/user-attachments/assets/53e91e11-544a-452a-9936-24a2edafe2fa" />
Here are the **important Amazon S3 bucket policies** you should know, explained clearly and simply (very useful for DevOps / AWS interviews and real-time use).

---

# 🔐 Important S3 Bucket Policies

## 1. **Public Read Access Policy**

Used to allow anyone on the internet to read objects (commonly for static websites).

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket-name/*"
    }
  ]
}
```

👉 **Use Case:** Static website hosting
⚠️ **Risk:** Anyone can access files

---

## 2. **Allow Access to Specific IAM User**

Restricts access to only one IAM user.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "UserAccess",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::123456789012:user/dev-user"
      },
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::my-bucket-name",
        "arn:aws:s3:::my-bucket-name/*"
      ]
    }
  ]
}
```

👉 **Use Case:** Developer-specific access

---

## 3. **Allow Access from Specific IP Address**

Restricts access based on IP.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "IPAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": "arn:aws:s3:::my-bucket-name/*",
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "192.168.1.10/32"
        }
      }
    }
  ]
}
```

👉 **Use Case:** Office network restriction

---

## 4. **Deny Unencrypted (HTTP) Access**

Forces HTTPS only (important security policy).

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "EnforceSSL",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::my-bucket-name",
        "arn:aws:s3:::my-bucket-name/*"
      ],
      "Condition": {
        "Bool": {
          "aws:SecureTransport": "false"
        }
      }
    }
  ]
}
```

👉 **Use Case:** Security best practice (very important 🔥)

---

## 5. **Allow Access from Specific VPC Endpoint**

Restricts access only from a VPC.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VPCOnly",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": "arn:aws:s3:::my-bucket-name/*",
      "Condition": {
        "StringEquals": {
          "aws:sourceVpce": "vpce-123abc456"
        }
      }
    }
  ]
}
```

👉 **Use Case:** Private architecture (no internet access)

---

## 6. **Deny Delete Objects (Protect Data)**

Prevents accidental deletion.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "NoDelete",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:DeleteObject",
      "Resource": "arn:aws:s3:::my-bucket-name/*"
    }
  ]
}
```

👉 **Use Case:** Production data protection

---

## 7. **Allow Only Specific Folder (Prefix) Access**

Restricts access to a folder inside the bucket.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "FolderAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket-name/app-data/*"
    }
  ]
}
```

👉 **Use Case:** Application-specific access

---

## 8. **Cross-Account Access Policy**

Allows another AWS account to access your bucket.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "CrossAccount",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::987654321098:root"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket-name/*"
    }
  ]
}
```

👉 **Use Case:** Sharing data between accounts

---

# ⭐ Important Points to Remember

* **Bucket policy = Resource-based policy**
* Always follow **least privilege principle**
* Prefer **IAM roles** over public access
* Use **Deny rules carefully** (they override Allow)
* Enable **Block Public Access** unless required

---

# 🔥 Real-Time DevOps Tips

* Always add **HTTPS enforcement policy**
* Use **VPC endpoint policy** for secure internal apps
* Combine **IAM + Bucket policy** for strong security
* Enable:

  * Versioning
  * Encryption (SSE-S3 / SSE-KMS)
  * Logging

