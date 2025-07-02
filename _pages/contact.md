---
title: Contact
layout: page
description: Contact Dustin Pearson.
permalink: /contact
featured_image: '/images/dustin.jpg'
---

{% include contact-form.html %}

function wpc_block_emails_on_form_submission( $result, $value, $form, $field ) {
    // Ensure the field is an email type and the value is a valid string
    if ( $field->type === 'email' && is_string( $value ) && ! empty( $value ) ) {
        
        // List of blocked emails (can be modified via a filter)
        $blocked_emails = apply_filters( 'wpc_blocked_emails', [ 'ericjonesmyemail@gmail.com' ] );

        // Normalize the email (trim spaces and convert to lowercase)
        $email = mb_strtolower( trim( $value ) );

        // Check if the email is in the blocked list
        if ( in_array( $email, $blocked_emails, true ) ) {
            $result['is_valid'] = false;
            $result['message']  = __( 'Cette adresse e-mail est incorrecte. Veuillez en utiliser une autre.', 'wpchannel' );
        }
    }

    return $result;
}

// Hook the function into Gravity Forms field validation
