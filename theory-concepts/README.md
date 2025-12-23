# Security Concepts 
## 1. Encryption vs. Encoding

**The Core Idea:**
Both encryption and encoding change data from one form to another—but why they do it, and how secure they are, is very different.

### Encoding

*Purpose:* Make data usable across systems.
Example: Sending a file over the internet might break if it contains special characters. Encoding (like Base64) ensures it travels safely.

*Security:* None at all. Anyone who knows the encoding scheme can decode it—no secret needed.
Example: A bank account number in a URL is URL-encoded so the link doesn’t break. Anyone can still read it.



### Encryption

*Purpose:* Keep data secret. Only authorized people can read it.

*Security:* Strong. You need a secret key to decrypt the data. Without it, the data is just random gibberish.
Example: A customer’s credit card number is encrypted before storing it in a database. Even if hackers steal the database, they can’t read the numbers.

