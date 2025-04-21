---
layout: default
permalink: /
title: My life prompted
nav: true
nav_order: 1
tabs: true
---

{% tabs sections %}

{% tab sections Current workshop offering %}


### Free, prompt-based writing workshop description
This workshop was designed for people who have been laid off, let go, or are otherwise looking for a work opportunity. Sign up for a start date and you’ll receive a prompt a day for 30 days. Every Friday I’ll send a few resources your way (links to other writing workshops, book references, etc.). And a few weeks into the prompting, I’ll send out information about a virtual meeting for those who want to talk about how the prompt process is going. 


### How it works 
Each workshop participant will receive a prompt every morning in their inbox for 30 days. I recommend spending a minimum of 10 minutes writing. When, where, and how you write is, of course, entirely up to you. Some will turn to paper journals, while others will choose to bang something out on a computer or phone. I do recommend keeping track of your prompts, as you’ll likely want to refer to them later. Unless you decide to share, no one else will see these, so let your mind roam and your thoughts flow with glorious abandon.  


### What will the prompts be like? 
The mystery is part of the journey! Some of the prompts will be directly related to work themes, while others will just get your thinking about disparate topics. Trust! Stay curious!


### What’s the point of all this? 
I am a very strong believer in the power of writing, and in the prompt-based writing method specifically. There is a lot of evidence out there to support the wide-ranging benefits that a daily writing practice can provide, and I can add my direct experience to the mix. Years ago, I read a fascinating [study](https://psycnet.apa.org/record/1994-39375-001) about the positive benefits of “expressive writing” for people who experienced job loss. In a nutshell, folks who practiced journaling every day found their next gig more quickly than those who didn't. I’m also deeply interested in people finding work opportunities that are _highly satisfying_, and I believe that journaling is a key component to understanding and finding that satisfaction. 

So if you’re looking for work, I want to support you on your journey. And I’ll be honest, I have a bigger agenda: I hope this leads to a life-long journaling practice for you. This workshop is free so that you can focus entirely on writing and crafting your vision of what’s next.   

### What is next? 
Register for this free workshop and start writing. Pick one of the four start dates. Starting on the date you picked, you’ll get a prompt a day for the next 30 days. 

{% endtab %}

{% tab sections About %}

I’m your workshop host, Emily Nava. I started my own writing business, [Tumbleweed Pioneer](https://tumbleweedpioneer.com/), in 2023. Since then I’ve led a number of prompts-based writing workshops. It’s a practice I feel passionate about because this writing method led to my own creative unblocking. I’ve written since I was a young child, but chose a career in the tech industry until I felt the pull grow stronger and stronger to commit to my creative calling. Now I work as a full-time writer, choosing the projects and clients that fulfill me. Prompts aren’t the only thing that contributed to my path, but they have been a huge part of it and I want to share the practice with others.

Through the process of working with my clients, I’ve developed a unique and inspiring way for people to start trusting themselves and their voice. And I am a firm believer that having more people in touch with their creative selves in this world is a great thing!

{% endtab %}

{% tab sections Register %}

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

{% endtab %}

{% endtabs %}

