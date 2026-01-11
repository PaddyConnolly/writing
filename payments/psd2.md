# PSD2 Explained

## Background

I encountered PSD2 quite a lot over my first few months at FIS, and couldn't really get my head around it, not because it was confusing, but because the fintech industry likes to throw a lot of acronyms out and it gets hard to keep up - so I'm writing this overview mainly for myself to refer back to.

## Overview

PSD2 stands for Payment Services Directive 2 - It's EU legislation that affects the whole payments industry, from Merchant to Issuer (or at least anyone who wants to do business in the EEA)

## Main Components

### Strong Customer Authentication (SCA)

When you perform a traditional transaction (i.e. inserting your card into a machine), you might not realise that you are essentially performing two-factor authentication, because you have something (the card with the chip) and you know something (the PIN).

SCA dictates that for electronic payments, you must do the same - but we have a problem - when you checkout online, you know something (the card details), but your issuer needs a bit more than that. Therefore, SCA requires that a customer provides two of the following:

  - Something they know (the card details as above)
  - Something they have (Phone, Hardware Token)
  - Something they are (Fingerprint, Facial recognition)

### Open Banking

Open Banking was introduced to stop traditional big banks from stifling competition by blocking new, innovative fintech apps from having access to their customers accounts - even when the customer explictly said that they wanted to use these apps.

### Third-Party Providers (TPPs)

This part is similar to the above, it dictates that customers of the traditional banks have the right to use PISPs and AISPs

- PISPs (Payment Initiation Service Provider): Imagine if you wanted to instantly send money to your friend via Revolut, but your bank (say HSBC), didn't like the competition and blocked it and instead forced you to use their slower, clunkier bank transfer.

- AISPs (Account Information Service Provider): Again, consider if you saw a budgeting app that you wanted to use, but your bank were developing one in-house and didn't want to lose customers, so they blocked outgoing information (that you've consented to) going to the app.

### Fee Transparency

This meant that there were much stricter rules on what fees could be charged and how any changes had to be communicated to the user. For us, it meant that any changes we did involving fees usually got put on hold for a couple of months, as they had to give the users ~60 days notice of any changes.

### Surcharge Ban

Bans EU businesses from adding a fee for credit/debit purchases (instead of cash)
