![Logo](https://smtpserver.com/assets/svg/logo.svg)


# smtpserver-cURL

cURL documentation for https://smtpserver.com. Mail sending is now super easy!


## License

[cURL](https://curl.se/docs/copyright.html)

![cURL_logo](https://curl.se/logo/curl-logo.svg)


## Documentation

Sending emails via the `SMTPServer's API` using `cURL` is straightforward. Simply create the command by adhering to the instructions provided below.

Mail sending occurs through the utilization of the `POST` method. The API's URL for this functionality is `https://api.smtpserver.com/mailer/send`.

```bash
  curl -X POST https://api.smtpserver.com/mailer/send
```
Proceed by including the headers. Two essential headers, namely `App-Key` and `Content-Type`, are required. The `App-Key` should contain your API key, while the `Content-Type` must always be set to `multipart/form-data`. Subsequently, you have the option to include additional headers as per your requirements.

```bash
  -H "App-Key: <YOUR API KEY>"
  -H "Content-Type: multipart/form-data"
  -H "<CUSTOM-HERDER-1>: <VALUE>"
  -H "<CUSTOM-HERDER-2>: <VALUE>"
```
Afterward, include the `to` field in the form. This field is a `mandatory field` and is expected to comprise a `JSON string` where the keys represent the email IDs of the recipients and the corresponding values indicate their names. If you prefer not to provide a name, simply pass an empty string.

```bash
  -F to='{"test1@test.com": "Tester 1"}'
```
Following that, include the `sender's email address`, which is a `required field`. However, it does not include the sender's name. An alternative option is available for specifying the sender's name.

```bash
  -F from=test@test.com
```
Subsequently, you have the option to include the `sender's name`, if desired.

```bash
  -F from_name='Good Tester'
```
Following that, you can choose to include the `email subject` if desired.

```bash
  -F subject='Test Mail'
```
Subsequently, provide the HTML content for the email body. Alternatively, you can provide the text version of the body. It is mandatory to pass one of these options.

```bash
  -F text='This is a test mail'
  -F html='This is a test mail'
```
In conclusion, you have the choice to include attachments with your email. This step is optional.

```bash
  -F attachment_1=@<ABSOLUTE PATH TO FILE>
  -F attachment_2=@<ABSOLUTE PATH TO FILE>
```


## Screenshot

![CompleteCode Screenshot](https://smtpserver.com/documentation/img/node-complete.png)


## Used By

This project is used by SMTPServer:

- [SMTP SERVER](https://smtpserver.com/)
