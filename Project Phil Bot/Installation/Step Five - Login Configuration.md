Now that we have configured everything else, there is one more major task before we're on the home stretch of installing FaxStore.

FaxStore comes with four login methods you can pick from.


- Discord
- GitHub
- Google
- Twitter

There is a section below for each login method and how to obtain the API tokens to login with these services.

---


### Discord
Although the most common Discord offers a range of out of app features which echo into the Discord platform that other services don't provide.

First things first, create a Discord application through the [Discord developer portal](https://discord.com/developers/applications)

Now on the OAuth2 page you will need to add the following as a redirect and replace the domain with yours. This is used in our login callback to actually log the user in.

```
https://example.com/auth/discord/callback
```
*Change `example.com` to represent your domain name.*

![discord1](https://faxes.zone/i/Giy35.gif)

Now, copy the Client ID and place it in the config file of FaxStore under the `tokens` section. Also copy the Client Secret from the Discord page into your FaxStore config.

`oAuth2ClientId` = Client ID
`oAuth2ClientToken` = Client Secret

Save file. Completed.

---

### GitHub

Adding GitHub is actually a lot easier than you might think!

Simply start by navigating to your [GitHub Developer Settings](https://github.com/settings/developers).

Once there, click on the "New OAuth App" button in the top right corner of the section.

![git1](https://faxes.zone/i/NOlp5.png)

Fill out the form so it might look something like this

![git2](https://faxes.zone/i/H4yBP.png)

```
https://example.com/auth/github/callback
```
*Change `example.com` to represent your domain name.*

Once done, copy the Client ID, and generate a new Client Secret, copy both of them.

Now edit the GitHub related tokens in the FaxStore config file.

Save, and completed.

---

### Google

This is likely the most difficult login method to set up. However, a major pro with this login method is that everyone has a Google account!

First off, head to the  [Google Developers Console](https://console.cloud.google.com/apis/dashboard).

Create a project using the button on the right hand side or via the Blue dropdown.

Create a project name and click create (usually a location isn't required). This might take up to a minute to create the application.

Once created click on `Credentials` on the left side bar, then click `Create Credentials` (using the OAuth client ID method) which is located at the top of the page.

You may be required to set up a 'consent screen', follow through the instructions for this. You will want an External consent screen.

**Consent Screen**
You will be asked for some details. When it asks you for scopes, you want to select the top two scopes (userinfo.email and userinfo.profile).

When you get back around to creating the  OAuth client ID, set it as a `Web application`
Under Authorized redirect URIs add the below callback for our login to function.

```
https://example.com/auth/google/callback
```
*Change `example.com` to represent your domain name.*

Once, the client is created copy the Client ID and Client Secret and add it to the tokens section for the Google flows in the FaxStore config.

---

### Twitter

If you don't have a developer account, you will need to apply for one [here](https://developer.twitter.com/en/apply-for-access)


If/Once you have a developer account go to the [developer portal](https://developer.twitter.com/en/portal/projects-and-apps) in the apps section.

Create a new application and enter the application name.

![twit1](https://faxes.zone/i/AHGMj.png)

After picking a name you will get an `API Key` and `API Key Secret`. Paste these into the Twitter section of the config under `tokens`.

Save.
