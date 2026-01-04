# Tokenisation

A payment token is simply a number that looks like a card number - but isn't - and that's important because it allows existing systems to treat it like a card number.

## Token Vault

Visa and Mastercard maintain a secure database called a Token Vault. The vault stores a 1:X mapping between your card number, and your tokens. For example, you might Apple Pay at a shop, and then order something online at Argos, and both times money came off of your card, but neither of the two companies know your card number - and importantly - they didn't even get the same token.

This means that if Argos were then to suffer a serious data breach, and your tokens got leaked, your card network (Visa or Mastercard) would see someone attempting to use a number which is stored somewhere, effectively as `ARGOS_TOKEN`, to buy something at Tesco, they would flag this as fraudulent.

Even better, since this token can't be reverse engineered into your card number, you don't even have to cancel your card, your bank will automatically reset just the Argos token, and you can continue using your card.

## Device Binding

Beyond merchant-specific tokens, you can also have device-specific tokens - think Apple or Google Pay. Instead of linking your card number to a merchant, it links it to a device. This means that instead of banks having to do rigorous checks every single time you try to buy something, they can verify you once when you link your card to your phone, and then you can use that token wherever you like
