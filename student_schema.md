![Student_Schema](http://i.imgur.com/iS1JwJ0.png)

What are the potential costs if you are relying on supporting ruby code to help validate your data?
There might be scalability issues because its a lot of data to manage and test on the controller side.
While the client-side might be unpredictable, for example they might not support JavaScript.


http://edgeguides.rubyonrails.org/active_record_validations.html
^ Say:

Client-side validations can be useful, but are generally unreliable if used alone. If they are implemented using JavaScript, they may be bypassed if JavaScript is turned off in the user's browser. However, if combined with other techniques, client-side validation can be a convenient way to provide users with immediate feedback as they use your site.
Controller-level validations can be tempting to use, but often become unwieldy and difficult to test and maintain. Whenever possible, it's a good idea to keep your controllers skinny, as it will make your application a pleasure to work with in the long run.