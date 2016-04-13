## Ask a question

Once the application receives an HTTP request from Twilio, it used a different
factory depending on if it's a SMS or a Call generated request to build its 
appropriated TwiML response..

For SMS the application will use '<Message>' verb answer all requests. 

In case of Phone call generated requests, the TwiML will contain a a `<Say>` 
verb for the question's text, and a `<Gather>` or `<Record>` verb to 
collect input based on the question's type, as specified in [questions.json](#1).

TwiML verbs have properties that allow you to change the way the verb works. 
For example, the ```<Record>``` verb always collects audio input, but, using 
the ```transcribeCallback``` property, you can specify a route to which Twilio 
will send a transcript of the audio input. For more on TwiML verbs and their 
properties, check out the [TwiML API documentation](https://www.twilio.com/docs/api/twiml).

---
**See also:**
- [TwiML Voice: <Say>](https://www.twilio.com/docs/api/twiml/say)
- [TwiML Voice: <Message>](https://www.twilio.com/docs/api/twiml/sms/message)
- [TwiML Voice: <Record>](https://www.twilio.com/docs/api/twiml/record)
- [TwiML Voice: <Gather>](https://www.twilio.com/docs/api/twiml/gather)
