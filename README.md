### What is it?

It's a project that allows you to access bunq's public API using [Postman](https://www.getpostman.com).

### How does one use it?

1. [Get Postman](https://www.getpostman.com/apps)
2. Run it. Don't bother signing in if you don't want to, there's a small link on the bottom to skip. This project does
   not use any of Postman's cloud features.
3. Click `Import` button in top left and drag all the files from the project there
4. In top right corner select your environment (sandbox or production).
5. If you selected sandbox, run `Create a sandbox user` request. It will automatically save your API key to the 
   environment.
6. If you selected production, edit the environment using the "eye" icon. Set "current value" of `api_key` to your API 
   key.
7. Run `Create an installation`, `Add the device`, `Add a session` in that order. They will create everything needed for
   using public API, including RSA keys, session and installation tokens. For you reference all those values will be set
   in the environment.
8. Run `GET - List monetary accounts` to check that everything is working properly. If it does, you can modify that request to
   do whatever you wanted to do and "Save as" for your future use.

### How does it work?

Postman has two javascript features: "Pre-request Script" and "Tests" that can get and set environment variables. Every
pre-request script includes a minimized RSA javascript library ([jsrsasign](https://github.com/kjur/jsrsasign)) and
some code to make signing work. Also, "Tests" save all the interesting values from responses such as tokens so that they
can be used in subsequent requests. Voila!
