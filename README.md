# SauceDemo Checkout Test Suite

This project checks that the public SauceDemo shopping flow still works from login to order confirmation.

## What It Checks

- Login with the public SauceDemo test user.
- Add products to the cart.
- Confirm the cart contains the right items.
- Complete checkout.
- Confirm the success message is shown.

## Run Locally

Install Java 17 and Maven, then run:

```bash
mvn test
```

To run the browser in the background:

```bash
mvn test -Dheadless=true
```

## Notes

- This uses SauceDemo public demo credentials only.
- Test reports are created in the `target/` folder after a run.
- The repository does not include private accounts, browser drivers, logs, or generated reports.
