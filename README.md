Introduction
------------

This is a very basic JavaScript API for sending events to a logdirector server. It's been kept slim on purpose to demonstrate the basics of sending data with JavaScript.

Usage
-----

**Configuration**

At the start of your script configure the client with the logdirector server URL and your application key:

    logdirector.configure('http://test.logdirector.com/logdirector', 'javascript_test');

**Logging data**

To send a log event, call the log method with the event type key and an optional attribute object:

    logdirector.log('js_log_message', {
        'level': 'important',
        'message': 'Hello World!'
    });

The attribute object works as a simple mapping from key to value - nesting objects is not supported.

**Data types**

By default attributes are stored as string. To use other data types use the following notation:

    logdirector.log('js_type_test', {
        'level:integer': 1,
        'duration:decimal': 123.456,
        'title:string': 'Hello World!'
        'message:text': 'Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.'
    });

logdirector supports the following attribute types:

* **integer**: Number without a fractional component
* **decimal**: Number with a fractional component
* **string**: String of up to 256 characters
* **text**: String with more than 256 characters