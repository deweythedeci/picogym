Running the program using netcat gives us a message saying
```
******************Welcome to our OTP implementation!******************                                                            This is the encrypted flag!                                                                                                       51124f4d194969633e4b52026f4c07513a6f4d05516e1e50536c4954066a1c57
```
and a follow up prompt that encrypts anything we type in
```
What data would you like to encrypt?
```

So, our goal is going to be to break the encryption and retrive the flag.

A quick google search of "one-time pad" will tell us that this type of encryption is unbreakable as long as 4 conditions are fulfilled.

src: https://en.wikipedia.org/wiki/One-time_pad
1. The key must be at least as long as the plaintext.
2. The key must be random.
3. The key must never be reused in whole or in part.
4. The key must be kept completely secret by the communicating parties.

If we can figure out which of these conditions are not being fulfilled, we have something we can exploit.

Next, we can look at the given python file to figure out what the program is doing in more detail.
