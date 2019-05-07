# ![LOGO](logo.png) LH Partner **flow**ground Connector

## Description

A generated **flow**ground connector for the LH Partner API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/lufthansa.com/partner/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:42:48+03:00

## API Description



## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Baggage Trip and Contact

> Retrieve passenger trip, contact and baggage details. This service is only accessible for LH privileged partners

*Tags:* `Baggage`

#### Input Parameters
* `searchID` - _required_ - Bag tag number, PNR, boarding card or FQTV ID
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")

### All Fares

> Retrieves all available fares for a specific Origin & Destination pair on a given date. Available fares are: One-way and Return for 4U. Return only for OS

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Specifies in which catalogue the fares need to be searched (e.g.'4U;OS').
* `origin` - _required_ - Enter journey origin (e.g 'FRA').
* `destination` - _required_ - Enter journey destination (e.g 'MAD').
* `travel-date` - _required_ - Enter journey travel-date (e.g 2016-10-20)
* `return-date` - _optional_ - Enter journey return-date (e.g 2016-10-31)'.
* `cabin-class` - _optional_ - Enter the required cabin class (e.g econonmy, business etc.). (Acceptable values are: "", "economy", "premium economy", "business", "first")
* `travelers` - _optional_ - Specifies the type and number of travelers (e.g. '(adult=2;child=2;infant=1)') For LH only (adult=1) possible.
* `fare-family` - _optional_ - Mandatory for 4U. Specifies, which fares to be returned, such as basic, smart, best, smartflex, bestflex . (Acceptable values are: "", "basic", "smart", "best", "smartflex", "bestflex")
* `trackingid` - _optional_ - Austrian Airlines only - specify the web tracking id to be used in OS Deep link.
* `Accept` - _optional_ - Mandatory http header:  application/xml or application/json

### Best Fares

> Retrieve best fares for the requested journey across multiple days or multiple months.

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Search fares from these carriers' catalogues (e.g. '4U;OS;LH')
* `origin` - _required_ - Journey origin. 3-letter IATA airport code (e.g. 'FRA')
* `destination` - _required_ - Journey destination. 3-letter IATA airport code (e.g. 'MAD')
* `travel-date` - _required_ - Journey travel-date (YYYY-MM-DD)
* `trip-duration` - _required_ - Trip duration in days (e.g. '7')
* `range` - _required_ - Fare range: 'byday' or 'bymonth' (Acceptable values are: "byday", "bymonth")
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `cabin-class` - _optional_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `country` - _optional_ - Country code of requestor. 2-letter ISO 3166-1 country code (e.g. 'de')
* `trackingid` - _optional_ - Austrian Airlines only - specify the web tracking id to be used in OS Deep link.
* `fare-family` - _optional_ - Fare family: basic, smart, best, smartflex, bestflex - Germanwings only (Acceptable values are: "", "basic", "smart", "best", "smartflex", "bestflex")

### Deep Links

> Returns valid deep links for the provided input parameters

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Carrier for which the deep link will be created (e.g. 'LH')
* `trackingid` - _required_ - Deep link tracking ID
* `country` - _required_ - 2-letter ISO 3166-1 country code
* `lang` - _required_ - 2-letter ISO 3166-1 language code
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `origin` - _optional_ - Journey origin. 3-letter IATA airport or city code (e.g. 'FRA')
* `origin-name` - _optional_ - Journey origin airport or city name (e.g. 'frankfurt')
* `destination` - _optional_ - Journey destination. 3-letter IATA airport or city code (e.g. 'MAD')
* `destination-name` - _optional_ - Journey destination airport or city name (e.g. 'madrid')
* `travel-date` - _optional_ - Journey travel-date (YYYY-MM-DD)
* `return-date` - _optional_ - Journey return-date (YYYY-MM-DD)
* `cabin-class` - _optional_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `outbound-segments` - _optional_ - Outbound flight segments in the sequence of travel (e.g. 'LH096;LH480')
* `return-segments` - _optional_ - Flight segments in the sequence of travel (e.g. 'LH7465;LH431')
* `travelers` - _optional_ - Type and number of travelers (e.g. '(adult=2;child=2;infant=1)')
* `fare` - _optional_ - Travel fare (e.g. '1341.45')
* `net-fare` - _optional_ - Travel net fare. Total fare less taxes and charges (e.g. '1140')
* `fare-currency` - _optional_ - Fare currency (e.g. 'EUR')
* `partnerid` - _optional_ - Deep link partner id (e.g. '1247')
* `encryption-key` - _optional_ - Deep link encryption-key

### LH Deep Links - FFP

> Returns valid LH deep links (FFP - links to flight selection screen on LH.COM)

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Carrier for which the deep link will be created (e.g. 'LH')
* `origin` - _required_ - Journey origin. 3-letter IATA airport or city code (e.g. 'FRA')
* `destination` - _required_ - Journey destination. 3-letter IATA airport or city code (e.g. 'MAD')
* `travel-date` - _required_ - Journey travel-date (YYYY-MM-DD)
* `trackingid` - _required_ - Deep link tracking ID
* `country` - _required_ - 2-letter ISO 3166-1 country code
* `lang` - _required_ - 2-letter ISO 3166-1 language code
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `return-date` - _optional_ - Journey return-date (YYYY-MM-DD)
* `cabin-class` - _optional_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `travelers` - _optional_ - Type and number of travelers (e.g. '(adult=2;child=2;infant=1)')
* `partnerid` - _optional_ - Deep link partner id (e.g. '1247')
* `encryption-key` - _optional_ - Deep link encryption-key

### LH Deep Links - ITCO

> Returns valid LH deep links (ITCO - links to shopping cart on LH.COM)

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Carrier for which the deep link will be created (e.g. 'LH')
* `origin` - _required_ - Journey origin. 3-letter IATA airport or city code (e.g. 'FRA')
* `destination` - _required_ - Journey destination. 3-letter IATA airport or city code (e.g. 'MAD')
* `travel-date` - _required_ - Journey travel-date (YYYY-MM-DD)
* `outbound-segments` - _required_ - Outbound flight segments in the sequence of travel (e.g. 'LH096;LH480')
* `fare` - _required_ - Travel fare (e.g. '1341.45')
* `fare-currency` - _required_ - Fare currency (e.g. 'EUR')
* `trackingid` - _required_ - Deep link tracking ID
* `country` - _required_ - 2-letter ISO 3166-1 country code
* `lang` - _required_ - 2-letter ISO 3166-1 language code
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `return-date` - _optional_ - Journey return-date (YYYY-MM-DD)
* `cabin-class` - _optional_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `return-segments` - _optional_ - Flight segments in the sequence of travel (e.g. 'LH7465;LH431')
* `travelers` - _optional_ - Type and number of travelers (e.g. '(adult=2;child=2;infant=1)')
* `net-fare` - _optional_ - Travel net fare. Total fare less taxes and charges (e.g. '1140')
* `partnerid` - _optional_ - Deep link partner id (e.g. '1247')
* `encryption-key` - _optional_ - Deep link encryption-key

### Fares

> Retrieve all available fares per fare family for a specific Origin & Destination on a given date

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Search fares from these carriers' catalogues - currently active for Germanwings only  (4U)
* `segments` - _required_ - Journey details  e.g. (origin=TXL;destination=CGN;travel-date=2016-12-15;return-date=2016-12-20;cabin=Economy)
* `carriers` - _required_ - Include fares for these carriers e.g. ('4U;LH')
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `travelers` - _optional_ - Type and number of travelers e.g. (adult=1;child=1;infant=1)
* `fare-types` - _optional_ - Fares family: basic,smart, best, smartflex, bestflex - Germanwings only (Acceptable values are: "", "basic", "smart", "best", "smartflex", "bestflex")

### Lowest Fares

> Retrieve lowest fare for a specific Origin & Destination pair on a given date. Available fares are: One-way and Return for 4U. Return only for OS & LH

*Tags:* `Offers`

#### Input Parameters
* `catalogues` - _required_ - Search fares from these carriers' catalogues e.g. '4U;OS;LH'
* `origin` - _required_ - Journey origin. 3-letter IATA aiport code e.g. 'FRA'
* `destination` - _required_ - Journey destination. 3-letter IATA airport code e.g. 'MAD'
* `travel-date` - _required_ - Journey travel-date YYYY-MM-DD
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `return-date` - _optional_ - Journey return-date - mandatory for OS and LH searches YYYY-MM-DD
* `cabin-class` - _optional_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `travelers` - _optional_ - Type and number of travelers e.g. '(adult=2;child=2;infant=1)'. For LH only (adult=1) possible
* `fare-family` - _optional_ - Fare family: basic, smart, best, smartflex, bestflex - Germanwings only (Acceptable values are: "", "basic", "smart", "best", "smartflex", "bestflex")
* `country` - _optional_ - Country code of requestor. 2-letter ISO 3166-1 country code (e.g. 'de')

### Fares Subscriptions

> Create a subscription for best price O&D. Receive regular updates on lowest fares

*Tags:* `Offers`

#### Input Parameters
* `origin` - _required_ - Journey origin. 3-leter IATA airport code (e.g. 'FRA')
* `destination` - _required_ - Journey destination. 3-letter IATA airport code (e.g. 'MAD')
* `cabin-class` - _required_ - Cabin class: 'economy', 'premium_economy', 'business', 'first' (Acceptable values are: "", "economy", "premium_economy", "business", "first")
* `trip-duration` - _required_ - Trip duration in days (e.g. '7')
* `email` - _required_ - Email Address')
* `lang` - _required_ - 2-letter ISO 3166-1 language code
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `country` - _optional_ - 2-letter ISO 3166-1 country code
* `trackingid` - _optional_ - Tracking parameter

### OND Route

> Returns LH route origin & destination information

*Tags:* `Offers`

#### Input Parameters
* `origin` - _required_ - Enter either the orgin city or orgin country code (e.g 'FRA' or 'DE'). Enter '*' for all
* `destination` - _required_ - Enter either the destination city or country code (e.g 'MAD' or 'ES'). Enter '*' for all
* `Accept` - _required_ - Mandatory http header:  application/xml or application/json
* `catalogues` - _optional_ - Carrier for which the OND will be retrieved (e.g. 'LH')
* `limit` - _optional_ - Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is given, 100 will be taken)
* `offset` - _optional_ - Number of records skipped. Defaults to 0

### OND Status

> Returns LH network route status information. Search for recently added or retired routes

*Tags:* `Offers`

#### Input Parameters
* `Accept` - _required_ - Mandatory http header:  application/xml or application/json
* `catalogues` - _optional_ - Carrier for which the OND will be retrieved (e.g. 'LH')
* `new-routes` - _optional_ - Enter if newly added routes should be returned in the response. (Acceptable values are: "", "true", "false")
* `old-routes` - _optional_ - Enter if old (deleted) routes should be returned in the response. (Acceptable values are: "", "true", "false")

### Top OND

> Returns LH Top routes per country or across all countries

*Tags:* `Offers`

#### Input Parameters
* `Accept` - _required_ - Mandatory http header:  application/xml or application/json
* `catalogues` - _optional_ - Carrier for which the OND will be retrieved (e.g. 'LH')
* `origin` - _optional_ - Enter the origin country code (e.g. 'DE'). Leave empty to search Top OND across all countries

### Orders

> Retrieve order by ID and optionally name. This service is only accessible for LH privileged partners

*Tags:* `Orders`

#### Input Parameters
* `orderID` - _required_ - Unique order identifier
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `name` - _required_ - Surname of traveller

### Auto Check-In

> Trigger an automatic check-in given a ticket number. This service is only accessible for LH privileged partners

*Tags:* `Preflight`

#### Input Parameters
* `ticketnumber` - _required_ - Ticket number
* `emailAddress` - _required_ - Email address
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")

### Price Offers

> Retrieve a best price offer given an origin and destination.

*Tags:* `Promotions`

#### Input Parameters
* `origin` - _required_ - Departure city. 3-letter IATA city code
* `destination` - _required_ - Destination city. 3-letter IATA city code
* `departureDate` - _required_ - Departure date in local time (YYYY-MM-DD)
* `returnDate` - _required_ - Return date in local time (YYYY-MM-DD)
* `service` - _optional_ - Optional parameter.

### Seat Details

> A description of all available seat details by aircraft type. You can retrieve the full set or details for a particular aircraft type.

*Tags:* `Reference Data`

#### Input Parameters
* `aircraftCode` - _required_ - Aircraft type. 3-character IATA equipment code
* `Accept` - _required_ - http header: application/json or application/xml (Acceptable values are: "application/json", "application/xml")
* `cabinCode` - _required_ - Cabin class: M, E, C, F (Acceptable values are: "", "M", "E", "C", "F")
* `lang` - _optional_ - 2-letter ISO 3166-1 language code

## License

**flow**ground :- Telekom iPaaS / lufthansa-com-partner-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
