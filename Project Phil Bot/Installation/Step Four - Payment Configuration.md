FaxStore currently supports two payment methods; **Stripe** and **PayPal**. Both of these services offer pros and cons for traders and you can have one or both of them enabled at once.

This article will cover how to set up both of these services for FaxStore.

---

### PayPal

Note; before starting this section, that PayPal requires a [PayPal Business Account](https://www.paypal.com/business/getting-started) to be able to use their API in a way that FaxStore does.

To start off go to the [PayPal Developer site](https://developer.paypal.com/developer/applications) and create a **live** application. This should look something like the below.

![paypal1](https://faxes.zone/i/6lUNJ.png)

Once you have clicked create enter the application name with the 'Merchant' category used.

Then collect your `Client ID` and `Secret` and keep them handy.

![paypal2](https://faxes.zone/i/NdbFU.png)

**Do not share your PayPal Client ID or Secret, this could give people full access to API flows of your PayPal account giving others access to transfer funds and more. Do not share this!**

Now that we have our Client ID and Secret with us we want to edit the config file for FaxStore.

Under the `payments` section of the config file, we want to set `usePayPal` to `true` and place our Client ID and Secret into the respective locations underneath.

![paypal3](https://faxes.zone/i/LDpCB.png)

Save the file and that is completed.

----

### Stripe

[Stripe](https://stripe.com) is another payment processor built into FaxStore.

Create a Stripe account if you haven't. Once you have go to the dashboard and click on 'Developers' in the top right

After this navigate to the API section and create a 'Secret Key' then give it a name.

**Do not share your Publishable key or secret, this could give people full access to API flows of your Stripe account giving others access to transfer funds and more. Do not share this!**

![stripe1](https://faxes.zone/i/2bsT4.png)

You can only view the secret key once, so store it somewhere safe for now.

You will also need a `Publishable key`. There should be a creation button located on the page.

Once you have these two keys take them to your config file and place them in the locations under `payments`. Don't forget to set `useStripe` to `true` to enable Stripe payments.

![stripe2](https://faxes.zone/i/AMeZG.png)

Save the config

---

### Square

[Square](https://squareup.com) is the third payment method supported on FaxStore. Setting up Square is easy.

Create a Square account at https://squareup.com. Once you have done so, go to the developer portal https://developer.squareup.com/apps

Once you're here create a new application, name it as you wish and go and view the application.

Ensure to click 'Production' at the top of the page. Once on production you will see the 'Production Application ID' and the 'Production Access token'.

Copy these tokens and place into the FaxStore config file and save. Job done :)

---

You have now configured payments for FaxStore. Move forward to the [Login Configuration](#)

*[Improve this page](https://github.com/FAXES/Documentation/blob/main/FaxStore/Installation/Step%20Four%20-%20Payment%20Configuration.md)*
