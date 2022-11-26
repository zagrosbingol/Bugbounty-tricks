


The bad twin attack:
  - Register on the main application
  - Decode the token if it is jwt
  - See if it contains any unique identifier and note it
  - Scan for subdomain that has the same login page like the main application
  - Register there with the same username and password used on the main application and note the token
  - Replace the main webb app token with the token from the staging app above
  - See if you get access to anybody elses account.