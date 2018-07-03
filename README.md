# Fix WhatsApp Api in Desktop Browsers

How to solve the WhatsApp api link problem “Click to Chat” does not work in Firefox and Safari desktop browsers by creating a “responsive” WhatsApp link.

## Getting Started

There are two bases for you to do this solution: api.whatsapp and web.whatsapp. Throughout the internet you will find people teaching with api., However in some tests I realized that it does not work in Firefox and Safari desktop browsers. These only work the web.whatsapp and the web does not work on mobiles.

This can be solved with a simple script that will redirect the user according to the device he is using.

### Instructions

* A Change where “YOURNUMBER” is by its number in the following format 15551234567, without the “+” and “()”..
* Replace the text “YOURTEXT” with what you want the person to send by changing the space for “+”. Ex. “I+Want”
* Save the file named index.php and upload it to your server.
