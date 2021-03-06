## PARTNER

### PARTNER SUPPLY DELAY
This service can help you in such a situation like vacation, stocktaking or you know you will not have your products in stock in time by any reason.
Set partner supply delay and the shipment date will stay accurate every time. Add, load, edit or delete partner supply delay.
Should you need to set supply delay only for certain goods, see supply delay for products and variants.
If you set both partner supply delay and supply delay on product or variant , supply delay on the certain product / variant will have higher priority (partner supply delay will be ignored).

*Method POST, PUT and DELETE returning boolean value.*


**POST**

If you want to set partner supply delay for the first time or you have already deleted one, use POST method.
```
<?php
...
use MPAPI\Services\Partner;

...

$partner = new Partner($mpapiClient);

// Setup new partner supply delay

// Only with the end date of validity
$validTo = new \DateTime('+10 days');
$response = $partner->postSupplyDelay($validTo);

// with both dates of validity
$validFrom = new \DateTime('+1 day');
$validTo = new \DateTime('+10 days');
$response = $partner->postSupplyDelay($validTo, $validFrom);
...
```

**GET**
For getting detail of already existing partner supply delay, use GET method.
```
<?php
...
use MPAPI\Services\Partner;

...

$partner = new Partner($mpapiClient);
// get partner supply delay
$supplyDelay = $partner->getSupplyDelay();
...
```

**PUT**
If you want to update existing partner supply delay, use PUT method.
```
<?php
...
use MPAPI\Services\Partner;

...

$partner = new Partner($mpapiClient);
// update end of validity
$validTo = new \DateTime('+13 days');
// update partner supply delay
$supplyDelay = $partner->putSupplyDelay($validTo);
...
```

**DELETE**
To turn off or remove the partner supply delay use DELETE method.
```
<?php
...
use MPAPI\Services\Partner;

...

$partner = new Partner($mpapiClient);
// delete partner supply delay
$supplyDelay = $partner->deleteSupplyDelay();
...
```