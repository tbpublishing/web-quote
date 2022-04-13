
The Presstimator uses data submitted from a Request a Quote webform in the New Quote from Web Form functionality.

A webform, web form or HTML form on a web page allows a user to enter data that is sent to a server for processing. 
Forms can resemble paper or database forms because web users fill out the forms using checkboxes, dropdown boxes, radio buttons, or text fields.

Forms are enclosed in the HTML <form> tag. 
This tag specifies the communication endpoint the data entered into the form should be submitted to, and the method of submitting the data, GET or POST.

When data that has been entered into HTML forms is submitted, the names and values in the form elements are encoded and sent to the server in an HTTP request message using GET or POST.
Typically, the data submitted on the form is transmitted via email.  This allows your email server to handle security of the email and form submission. 

The Presstimator imports the contents of the email submitted by the webform to create a New Quote.
Please view the ImportFields.txt file for tags that are currently imported.


In our example we use Tectite.com's free FormMail processor.  You can choose any FormMail processor.

In our example there are three files that go on your server. 


1) The webform_request.html is the form that users enter the data into from your website. 
   <!-- STEP 1: Put the full URL to formmail.php on your website in the 'action' value. -->
   Example:  <form method="post" action="http://www.yourdomain.com/formmail.php" name="Request a Quote">
   The formmail.php file receives and processes the form contents.
   Rename"yourdomain.com" to your domain.
   
   You can enter required fields and validation on the webpage before submitting the form to be processed.

   Option:  You can enter a webpage to navigate to after successful submission of the webform.
   <input type="hidden" name="good_url" value="http://yourdomain.com/postrequest.html" />
   
   You can customize this example form in any way or create your own.
   Please view the ImportFields.txt file for tags that are currently imported.


2) The postrequest.html file is the optional webpage that the user is navigated to once they enter the valid information on the form.  


3) The formmail.php file is the file that processes the data entered in the form and sends it to the specified email address. 
   NOTE: Any formmail utility will work.
   For this example, we used the free formmail tool at http://www.tectite.com/ to process the contents of forms.
   Please note that you must change the email address and domain information in the fommail.php file.
   Rename $recipient = "youremail@domain.com"; // youremail@domain.com to your email address that will receive the request.
   Rename $referers = array('yourdomain.com');  // yourdomain.com to your domain for security purposes.  This form will only submit the information if coming from this domain.
   You can customize formmail processing or use another formmail php or create your own.


You can use any other form submission you would like as long as the fields being submitted by the form match the fields indicated in ImportFields.txt.

The New Quote from WebForm will look for the fields in ImportFields.txt to populate the Specs of a Quote in the Presstimator.
Once the New Quote is created, clicking the Load All Defaults button in the Quote in the Presstimator will complete the Quote.
Additional fields can be added as needed.

Star*Key Software assumes no responsibility for the implementation of the above products and is in no way affiliated with tectite.com or Open Concepts (Vic) Pty Limited.
 
