---
title: "DOM events"
post_status: publish
post_name: dom-events
lang: en
taxonomy:
  category: [contact-form-7]
source:
  blog_id: 66
  post_id: 57
  guid: "http://import.local/2021/12/27/dom-events/"
---

Contact Form 7 provides several types of custom DOM events. You can utilize the events within your JavaScript code to run a function in a specific situation.
This article explains the DOM events that Contact Form 7 provides, in what cases those events fire, and how you can use them in your code. Since this article omits general explanation about the DOM event model, if you are not familiar with it please refer to external documents:
DOM events (Wikipedia)Overview of Events and Handlers (MDN)Document Object Model (DOM) Level 2 Events Specification
List of Contact Form 7 custom DOM events
wpcf7invalid — Fires when an Ajax form submission has completed successfully, but mail hasn’t been sent because there are fields with invalid input.wpcf7spam — Fires when an Ajax form submission has completed successfully, but mail hasn’t been sent because a possible spam activity has been detected.wpcf7mailsent — Fires when an Ajax form submission has completed successfully, and mail has been sent.wpcf7mailfailed — Fires when an Ajax form submission has completed successfully, but it has failed in sending mail.wpcf7submit — Fires when an Ajax form submission has completed successfully, regardless of other incidents.
Coding event handler
The code below is a simple example of registering an event handler. In this example, the function listens to the wpcf7submit event and just pops up an alert when the event occurs.
12345var wpcf7Elm = document.querySelector( '.wpcf7' ); wpcf7Elm.addEventListener( 'wpcf7submit', function( event ) {  alert( "Fire!" );}, false );
As you see in the example, you use addEventListener() to register an event handler function. Be aware that the event target (wpcf7Elm in the example) is not a form element, but its parent div element that has a wpcf7 class.
Since all of the wpcf7\* events bubble up through a DOM tree toward the document root, if you don’t need to set a specific event target, you can make it simpler by setting the document property as the event target:
123document.addEventListener( 'wpcf7submit', function( event ) {  alert( "Fire!" );}, false );
User input data through the target contact form is passed to the event handler as the detail.inputs property of the event object. The data structure of detail.inputs is an array of objects, and each object has name and value properties.
This is an example that accesses the user input value through the “your-name” field:
12345678910document.addEventListener( 'wpcf7submit', function( event ) {  var inputs = event.detail.inputs;   for ( var i = 0; i < inputs.length; i++ ) {    if ( 'your-name' == inputs[i].name ) {      alert( inputs[i].value );      break;    }  }}, false );
There are also other properties of the event object that you can utilize in your event handler.
PropertyDescriptiondetail.contactFormIdThe ID of the contact form.detail.pluginVersionThe version of Contact Form 7 plugin.detail.contactFormLocaleThe locale code of the contact form.detail.unitTagThe unit-tag of the contact form.detail.containerPostIdThe ID of the post that the contact form is placed in.
For example, if you want to do something only with a specific contact form (ID=123), use the detail.contactFormId property as seen in the following:
123456document.addEventListener( 'wpcf7submit', function( event ) {  if ( '123' == event.detail.contactFormId ) {    alert( "The contact form ID is 123." );    // do something productive  }}, false );
See also
DOM event doesn’t work.
Share this:FacebookTwitterLike this:Like Loading...
