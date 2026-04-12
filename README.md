# NFC vCard Writer

This is a fairly simple project (HTML, Javascript) to allow a user with Chrome running on a supported Android device to write a vCard to an NFC tag (see [NDEFWriter](https://caniuse.com/?search=NDEFWriter) for latest device/browser version support).

It was annoying how bad some of the available apps were that offered to do this - either full of ads, partial/broken/no vCard implementation, or expensive - so I ended up spending a bit of time researching this (I needed to be able to read/write NFC enabled ID cards for a non-profit to track volunteers, so was already heading down the rabbit-hole!).

Current implementation supports vCard 3.0, and work addresses (though could be easily extended to support a home address option as well), and assumes it's the only record on the card (it overwrites whatever was on the card before).

It checks input to make sure the vCard will fit onto an NTAG215 format card (if using an NTAG216 the `max_size` constant should be adjusted accordingly) - it would be nice to add an option to read the card the user intends to use and set the `max_size` based on memory (could also check if it's writable or locked at the same time).

Apart from the length check, there is no validation (might be nice to validate emails are correct format or the URL can be accessed), either keeping it within the HTML/JavaScript or doing some server side validation.

If you want to try it out, there's a live version hosted [here](https://obm.one/nfc_write).

**Requests:** 
---
- if someone with an iPhone can validate if these vCards are correctly read that would be great (annoyingly Apple didn't add NFC capabilities to the iPad Pro I have).
- would be good to have a list of phones this has been tested with to know what it can write from. I've tested successfully on a Pixel Pro 9 and Pixel 3.

*Oh, and if you use this in a commercial project or just feel generous - BTC gratefully accepted: bc1qeurlc5eqmv7997ce9uep7dxsk4w2rya8v88gzyv24r297qs2wrmqfp8kfq*

