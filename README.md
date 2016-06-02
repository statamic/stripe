# Stripe

This tag acts as some syntactic sugar for [Stripe Checkout][checkout]. It simplifies your templates.

The server-side processing is up to you.

### Stripe.js
A shortcut to placing Stripe.js on your page. Put this at the bottom of your layout.

```
{{ stripe:js }}

Outputs:
<script type="text/javascript" src="https://js.stripe.com/v2/"></script>
```

### Stripe Checkout
A shortcut for generating a Stripe Checkout form.

```
{{ stripe:checkout action="/my-action" amount="500" description="T-shirt" }}

Outputs:
<form action="/my-action" method="POST">
    <script
        src="https://checkout.stripe.com/checkout.js" class="stripe-button"
        data-key="pk_test_6pRNASCoBOKtIshFeQd4XMUh"
        data-amount="500"
        data-name="My Company"
        data-description="T-shirt"
        data-image="/logo.png"
        ...
    ></script>
</form>
```

#### Parameters

The `action` parameter specifies where the form will POST to after receiving a token from Stripe.
The server-side logic is up to you to develop with your own addon.

Any configuration option listed [in the Stripe Checkout docs](https://stripe.com/docs/checkout#integration-simple-options) are available to you on the tag
without the `data-` prefix, and with underscores instead of dashes.

For example, where in the docs it says `data-zip-code="true"`, you'd use `zip_code="true"`.


[checkout]: https://stripe.com/checkout
