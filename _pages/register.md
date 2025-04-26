---
layout: default
permalink: /register
title: Register
nav: true
nav_order: 3
tabs: true
---

### Start dates

Choose a start date: 
* April 28 (prompts end on May 27)
* May 5 (prompts end on June 3)
* May 12 (prompts end on June 10)
* May 19 (prompts end on June 17)

<br />
Your name:
First
Last

Your email: 

If you want to ask a question or send a message, you can do so here: 

P.S. Some people have asked if they can pay for this workshop or provide support in another way. Thank you for your interest! 
The best way to support my work is by becoming a [paid subscriber](https://tumbleweedpioneer.substack.com/) to my Substack or by sending a [referral](https://tumbleweedpioneer.com/services/) my way.

<label for="workshop-dates">Choose a start date:</label>
<select name="workshop-dates" id="workshop-dates">
    <option disabled selected value>&ndash;&ndash; Select an option &ndash;&ndash;</option>
    <option value="price_1QK7jODWI41Mc7pyZeYJb9ii">April 28 (prompts end on May 27)</option>
    <option value="price_1QK7jSDWI41Mc7pyKRuaURcV">May 5 (prompts end on June 3)</option>
    <option value="price_1QK7jUDWI41Mc7pyMzcSHV8R">May 12 (prompts end on June 10)/option>
    <option value="price_1QK7jWDWI41Mc7pyu16yo24N">May 19 (prompts end on June 17)</option>
</select>

<button disabled class="checkout-button" id="checkout-button" role="link" type="button">Checkout</button>

<div id="error-message"></div>
<script>
(function() {
  var stripe = Stripe('pk_live_51OS9CkDWI41Mc7pyIIsKI0sxlc10XtY1ZPUKM8C0e75wu2uQXU7PRzFMzfVBfMWqvMEWKA0Hey2keyP5MY30jN5700nyu87NR0');

    var workshopDatesSelect = document.getElementById('workshop-dates');
    workshopDatesSelect.addEventListener("change", function() {
        checkoutButton.disabled = workshopDatesSelect.value == null;
    });


  var checkoutButton = document.getElementById('checkout-button');
  checkoutButton.addEventListener('click', function () {
    /*
     * When the customer clicks on the button, redirect
     * them to Checkout.
     */
    stripe.redirectToCheckout({
      lineItems: [{price: document.getElementById("workshop-dates").value, quantity: 1}],
      mode: 'payment',
      /*
       * Do not rely on the redirect to the successUrl for fulfilling
       * purchases, customers may not always reach the success_url after
       * a successful payment.
       * Instead use one of the strategies described in
       * https://docs.stripe.com/payments/checkout/fulfill-orders
       */
      successUrl: 'https://mylifeprompted.com/confirmation',
      cancelUrl: 'https://mylifeprompted.com/',
    })
    .then(function (result) {
      if (result.error) {
        /*
         * If `redirectToCheckout` fails due to a browser or network
         * error, display the localized error message to your customer.
         */
        var displayError = document.getElementById('error-message');
        displayError.textContent = result.error.message;
      }
    });
  });
})();
</script>
