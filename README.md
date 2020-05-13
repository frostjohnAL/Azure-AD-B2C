# Arkose Integration with Azure B2C

Arkose Labs Enforcement Challenge Sign in form on Azure B2C

For details on Arkose Labs visit https://www.arkoselabs.com/ 

## Live sample

1. Visit this [link](https://arkosetest2.b2clogin.com/arkosetest2.onmicrosoft.com/oauth2/v2.0/authorize?p=B2C_1_ArkoseChallenge&client_id=96392ea3-c9ca-49c2-b670-e3bb80512cc8&nonce=defaultNonce&redirect_uri=https%3A%2F%2Farkosephp.azurewebsites.net%2Fcallback.php&scope=openid&response_type=id_token&prompt=login)
2. Click Sign up
3. Complete Sign up
4. Return to Sign in page
5. Attempt sign in and on submit the challenge appears

## Setup - Front end

1. Create a B2C Directory + subscription per [link](https://azure.microsoft.com/en-us/services/active-directory/external-identities/b2c/)
2. Follow these steps to create a custom user flow including, storage account and a blob file that will hold the index.html file in this repo [link](https://docs.microsoft.com/en-us/azure/active-directory-b2c/tutorial-customize-ui)
3. Once you have the user flow customized follow these steps to enable javascript for the given user flow [link](https://docs.microsoft.com/en-us/azure/active-directory-b2c/user-flow-javascript-overview)
4. Replace <PUBLIC_KEY> in index.html on line 21 with your public key.

Note: to make your own styling you can remove all the default styling in index.html including references to "arkoselabs".

## Setup - Back end
To validate the token using your private key you'll need to host a backend server to call Arkose after the user has completed the challenge.

1. Follow these steps to set up a php server [link](https://docs.microsoft.com/en-us/azure/app-service/app-service-web-get-started-php)
2. Commit verify-token.php to the hosted repo. Remember to replace <PRIVATE_KEY> on line 3.
3. Update the blob index.html file on line 86 to point to the endpoint created in the php app for verify-token.php.


## Arkose Labs - Sign up 
Reach out to our team to sign up for a merchant account via this [link](https://www.arkoselabs.com/contact-sales/) or at (800) 604-3319. The team can provide a tailored demo at https://www.arkoselabs.com/book-a-demo/
