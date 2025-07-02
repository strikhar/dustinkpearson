---
title: Contact
layout: page
description: Contact Dustin Pearson.
permalink: /contact
featured_image: '/images/dustin.jpg'
---

{% include contact-form.html %}  

<script src="https://www.google.com/recaptcha/api.js"></script>

 <script>
   function onSubmit(token) {
     document.getElementById("demo-form").submit();
   }
 </script>

<button class="g-recaptcha" 
        data-sitekey="6LefgXQrAAAAAA7ovWLDfdITCt_GWQ0CjlAhfOlD" 
        data-callback='onSubmit' 
        data-action='submit'>Submit</button>
