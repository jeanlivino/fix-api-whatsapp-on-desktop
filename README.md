# Fix WhatsApp Api in Desktop Browsers

How to solve the WhatsApp api link problem “Click to Chat” does not work in Firefox and Safari desktop browsers by creating a “responsive” WhatsApp link.

## [My WhatsApp Link Generator](https://github.com/jeanlivino/whatsapp-link-generator)

## Getting Started

There are two bases for you to do this solution: api.whatsapp and web.whatsapp. Throughout the internet you will find people teaching with api., However in some tests I realized that it does not work in Firefox and Safari desktop browsers. These only work the web.whatsapp and the web does not work on mobiles.

This can be solved with a simple script that will redirect the user according to the device he is using.

### Instructions

* A Change where “YOURNUMBER” is by its number in the following format 15551234567, without the “+” and “()”..
* Replace the text “YOURTEXT” with what you want the person to send by changing the space for “+”. Ex. “I+Want”
* Save the file named index.php and upload it to your server.
```
<?php
// Fix Api Whatsapp on Desktops
// Dev: Jean Livino
$iphone = strpos($_SERVER['HTTP_USER_AGENT'],"iPhone");
$android = strpos($_SERVER['HTTP_USER_AGENT'],"Android");
$palmpre = strpos($_SERVER['HTTP_USER_AGENT'],"webOS");
$berry = strpos($_SERVER['HTTP_USER_AGENT'],"BlackBerry");
$ipod = strpos($_SERVER['HTTP_USER_AGENT'],"iPod");
// check if is a mobile
if ($iphone || $android || $palmpre || $ipod || $berry == true)
{
 header('Location: https://api.whatsapp.com/send?phone=YOURNUMBER&text=YOURTEXT');
 //OR
 echo "<script>window.location='https://api.whatsapp.com/send?phone=YOURNUMBER&text=YOURTEXT'</script>";
}
// all others
else {
 header('Location: https://web.whatsapp.com/send?phone=YOURNUMBER&text=YOURTEXT');
 //OR
 echo "<script>window.location='https://web.whatsapp.com/send?phone=YOURNUMBER&text=YOURTEXT'</script>";
}
?>
```
