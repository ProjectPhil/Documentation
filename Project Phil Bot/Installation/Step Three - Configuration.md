Now that you have completed step one and two it's time to start configuring our site in the configuration file.

As FaxStore has multiple login options and store a lot of tokens, all of these tokens are in the config file to make them as secure as possible.

This section covers a variable documentation table on every single item inside the config file along with what it is and does as well as how to configure it.

---


Once you have configured FaxStore to have all of the **required** configuration options then you can proceed.

**[R]** symbols a required item.

---

| Name | Category  |  Description | Value |
| -------- |:-------------:| --------------:| ---------:|
| processPort | siteInformation |  The Port for NGINX to use. **[R]** | `number` |
| domain | siteInformation |  The website domain name eg: faxes.zone **[R]** | `string` |
| ownerId | siteInformation |  The ID of the site owner **[R]** | `string` |
| startDebug | siteInformation |  Display debug information on start up | `true or false` |
| blockCORS | siteInformation |  Block built in CORS policy | `true or false` |
| usePayPal | payments |  Toggles PayPal as a payment method | `true or false` |
| useStripe | payment |  Toggles Stripe as a payment method | `true or false` |
| stripePublishableKey | payment |  The Stripe publisable key. Guide [here](https://docs.faxes.zone/c/faxstore/stepfour#stripe) | `string` | 
| stripeSecretKey | payment |  The Stripe Secret Key. Guide [here](https://docs.faxes.zone/c/faxstore/stepfour#stripe) | `string` |
| paypalClientId | payment |  The PayPal Client ID. Guide [here](https://docs.faxes.zone/c/faxstore/stepfour#paypal) | `string` | 
| paypalClientSecret | payment |  The Paypal Client Secret. Guide [here](https://docs.faxes.zone/c/faxstore/stepfour#paypal) | `string` |
| discordBotToken | tokens |  The Discord Bot Token. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#discord) | `string` |
| oAuth2ClientId | tokens | The Discord Client ID. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#discord) | `string` |
| oAuth2ClientToken | tokens | The Discord Client Secret. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#discord) | `string` |
| googleClientId | tokens | The Google Client ID. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#google) | `string` |
| googleClientSecret | tokens |  The Google Client Secret. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#google) | `string` |
| githubClientId | tokens |  The GitHub Client ID. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#github) | `string` |
| githubClientSecret | tokens | The GitHub Client Secret. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#github) | `string` |
| twitterAPIKey | tokens |  The Twitter API Key. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#twitter) | `string` |
| twitterSecretKey | tokens |  The Twitter Client Secret. Guide [here](https://docs.faxes.zone/c/faxstore/stepfive#twitter) | `string` |
| host | SQLInformation |  The MYSQL Host. Generally `localhost` **[R]** | `string` |
| username | SQLInformation |  The MYSQL User. Generally `root` **[R]** | `string` |
| password | SQLInformation | The MYSQL Password. This is the password you set in [Step One](https://docs.faxes.zone/c/faxstore/stepone#installing-mysql) **[R]** | `string |
| database | SQLInformation |  The MYSQL Database. Generally faxstore. **[R]** | `string` | 
| useEmails | emails | Toggles Emails. Guide [here](https://docs.faxes.zone/c/faxstore/sendgrid) | `true or false` |
| fromEmail | emails |  The sender email address. Guide [here](https://docs.faxes.zone/c/faxstore/sendgrid) | `string` |
| sendGridToken | emails |  The SendGrid Token. Guide [here](https://docs.faxes.zone/c/faxstore/sendgrid) | `string` |
| emailHeader | emails |  The Header for the email. Supports HTML. Guide [here](https://docs.faxes.zone/c/faxstore/sendgrid) | `string` |
| emailFooter | emails |  The Footer for the email. Supports HTML . Guide [here](https://docs.faxes.zone/c/faxstore/sendgrid) | `string` |
| useDiscordChannelLogs | discordConfig |  Toggles the discord logging | `true or false` |
| botStatus | discordConfig |  Sets the bot status (idle, dnd, online, invisible) | `string` |
| loggingChannelId | discordConfig |  The channel for logs to be sent to. Right click channel and click "copy ID" | `string` |
| guildId | discordConfig |  The ID of your server. Right click your server and click "copy ID" | `string` |
| autoJoinUsers | discordConfig |  Makes users join the server on login | `true or false` |
| useDiscordCommands | discordConfig |  Uses the discord slash commands (requires application commands intent) | `true or false` |
| commandPrefix | discordConfig | Sets the prefix for the command (Only used when Discord Commands are set to false) | `string` | 
| useEmbeds | discordConfig |  Toggles Embeds | `true or false` |
| name | redirects |  Sets the redirect name eg. discord | `string` |
| link | redirects | The URL for the redirect eg. faxes.zone/d | `URL` |

*[Improve this page](https://github.com/FAXES/Documentation/blob/main/FaxStore/Installation/Step%20Three%20-%20Configuration.md)*
