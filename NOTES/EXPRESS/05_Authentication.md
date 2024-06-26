[[#Hashing]]
[[#Encryption]]
[[#JWT]]
[[#Local Storage]]

Before going to authentication lets understand some crpytography jargons
1. Hashing
2. Encryption
3. JWT (JSON Web Tokens)
4. Local Storage

#### Hashing

- We hash our password before store them into database.
- Converting a simple string into something complicated gibberish.
- A hash code never convert backs to string.
- For verification same string get converted into hash code and hash code is compared to the hash code already present.
- Password---------------> Hashcode.

#### Encryption

- Your string get converted into something gibberish and that encrypted data can back converted to string also.
- It is 2 way.
- A secret key is needed to decrypt the data.

#### JWT

 JWT is mainly used to create tokens.
 - JSON - Only works for JSON data. 
 - Web -  Used it in a web.
 - Tokens - The input is converted and generates a string known a token.
 - Using JWT your input gets converted into some output and whomsoever having that output can produce the same input.
 - Conversion anyone can do but verification can't there is something called` jwt.verify()` function that verifies the password and the input . It is similar to bank anyone can see the check but only the bank can verify the cheque.

##### Main things in the JWT
1. Generating a JWT --> Can be done by jwt.sign(value,password)
2. Decoding a JWT
3. Verifying a JWT
 
**Main functions of JWT** :-
1. jwt.sign() :- The `jwt.sign` function creates a new JWT.
	1. Syntax :-` jwt.sign(payload, secretOrPrivateKey, [options, callback])
	2. jargons :-
	- **payload**: This is the data you want to include in the token. It can be an object, buffer, or string.
	- **secretOrPrivateKey**: This is the secret key or private key used to sign the token.
	- **options**: (Optional) This is an object containing various options for the token, such as expiration time, audience, issuer, etc.
	- **callback**: (Optional) If provided, the function will be asynchronous, and the callback will be called with the token or an error.
2. jwt.verify() :-
`

#### Local Storage
 A place in your browser where you can store some data usually that are stored include-
 1. Authentication tokens.
 2. User language preference.
 3. User theme preference.


**Programs :-**
1. Create a website having two end points -
   - `POST/signin` :- Returns the json web token with username encrypted.
   -  `GET/users`:-  Takes authorization header as input expects user to sendback this JWT. Returns an array of all users if user is signed in (token is correct) Returns 403 status code if not.