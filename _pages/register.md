---
layout: default
permalink: /register
title: Register
nav: true
nav_order: 3
tabs: true
---

### Register &amp; choose a start date

Once you choose a start date below for one of the workshop options, you will be taken to the payments page where we will collect your name and email. After you have finished paying, you will receive a welcome email from Tumbleweed Pioneer.

Thank you for registering for the workshop!

### Prompts-only workshop ($100)
<select name="prompts-only-dates" id="prompts-only-dates">
    <option disabled selected value>&ndash;&ndash; Select an option &ndash;&ndash;</option>
    <option value="price_1S7gyfDWI41Mc7pyCvm8EuUA">Starting September 22 &mdash; Re-writing Your Career Moves: Prompts</option>
    <option value="price_1S7gz7DWI41Mc7pyH7o2aOME">Starting September 29 &mdash; Re-writing Your Career Moves: Prompts</option>
    <option value="price_1S7gzTDWI41Mc7pyHjRr1Ho7">Starting October 6 &mdash; Re-writing Your Career Moves: Prompts</option>
    <option value="price_1S7gzmDWI41Mc7py37rFL1HB">Starting October 13 &mdash; Re-writing Your Career Moves: Prompts</option>
</select>
<button disabled class="checkout-button" id="prompts-only-checkout-button" role="link" type="button">Checkout</button>

### Prompts + classes workshop ($350)
<select name="prompts-plus-classes-dates" id="prompts-plus-classes-dates">
    <option disabled selected value>&ndash;&ndash; Select an option &ndash;&ndash;</option>
    <option value="price_1S7h3pDWI41Mc7pysOxa0OJh">Starting September 22 &mdash; Re-writing Your Career Moves: Prompts + Classes</option>
    <option value="price_1S7h46DWI41Mc7pyggWUc8YP">Starting September 29 &mdash; Re-writing Your Career Moves: Prompts + Classes</option>
    <option value="price_1S7h4MDWI41Mc7pyvmGTfqhT">Starting October 6 &mdash; Re-writing Your Career Moves: Prompts + Classes</option>
    <option value="price_1S7h4cDWI41Mc7py1CdmkygC">Starting October 13 &mdash; Re-writing Your Career Moves: Prompts + Classes</option>
</select>
<button disabled class="checkout-button" id="prompts-plus-classes-checkout-button" role="link" type="button">Checkout</button>

<div id="error-message"></div>
<script>
/* Prompts-only checkout */
(function() {
  var stripe = Stripe('pk_live_51OS9CkDWI41Mc7pyIIsKI0sxlc10XtY1ZPUKM8C0e75wu2uQXU7PRzFMzfVBfMWqvMEWKA0Hey2keyP5MY30jN5700nyu87NR0');

    var workshopDatesSelect = document.getElementById('prompts-only-dates');
    workshopDatesSelect.addEventListener("change", function() {
        checkoutButton.disabled = workshopDatesSelect.value == null;
    });


  var checkoutButton = document.getElementById('prompts-only-checkout-button');
  checkoutButton.addEventListener('click', function () {
    /*
     * When the customer clicks on the button, redirect
     * them to Checkout.
     */
    stripe.redirectToCheckout({
      lineItems: [{price: document.getElementById("prompts-only-dates").value, quantity: 1}],
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

/* Prompts + classes checkout */
(function() {
  var stripe = Stripe('pk_live_51OS9CkDWI41Mc7pyIIsKI0sxlc10XtY1ZPUKM8C0e75wu2uQXU7PRzFMzfVBfMWqvMEWKA0Hey2keyP5MY30jN5700nyu87NR0');

    var workshopDatesSelect = document.getElementById('prompts-plus-classes-dates');
    workshopDatesSelect.addEventListener("change", function() {
        checkoutButton.disabled = workshopDatesSelect.value == null;
    });


  var checkoutButton = document.getElementById('prompts-plus-classes-checkout-button');
  checkoutButton.addEventListener('click', function () {
    /*
     * When the customer clicks on the button, redirect
     * them to Checkout.
     */
    stripe.redirectToCheckout({
      lineItems: [{price: document.getElementById("prompts-plus-classes-dates").value, quantity: 1}],
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

Refund policy: If you are unable to attend the workshop after registering, a full refund can be issued up to 48 hours before the workshop start date. If you are unable to join or continue with the workshop after that time, please reach out to tumbleweedpioneer AT gmail DOT com.

