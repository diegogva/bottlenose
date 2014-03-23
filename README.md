Bottlenose
==========

Description
-----------

Bottlenose is a thin Python wrapper over the Amazon Product Advertising API. There is practically no overhead. Before you get started, make sure you have both Amazon Product Advertising and AWS accounts (yes, they are separate--confusing, I know).

Features
--------

* Compatible with Python versions 2.4 and up
* Support for CA, CN, DE, ES, FR, IT, JP, UK, and US Amazon endpoints
* No requirements, except simplejson for Python pre-2.6
* Configurable query parsing
* Configurable throttling for batches of queries
* Configurable query handling
* Configurable error handling and retry

Usage
-----

     >>> import bottlenose
     >>> amazon = bottlenose.Amazon(AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_ASSOCIATE_TAG)
     >>> response = amazon.ItemLookup(ItemId="0596520999", ResponseGroup="Images",
         SearchIndex="Books", IdType="ISBN")
     <?xml version="1.0" ?><ItemLookupResponse xmlns="http://webservices.amazon...

Here's another example.

     >>> response = amazon.ItemSearch(Keywords="Kindle 3G", SearchIndex="All")
     <?xml version="1.0" ?><ItemSearchResponse xmlns="http://webservices.amazon...

Bottlenose can also read your credentials from the environment automatically;
just set `$AWS_ACCESS_KEY_ID`, `$AWS_SECRET_ACCESS_KEY` and
`$AWS_ASSOCIATE_TAG`.

Any valid API call from the following is supported (in addition to any others
that may be added in the future). Just plug in appropriate request parameters
for the operation you'd like to call, and you're good to go.

     BrowseNodeLookup
     CartAdd
     CartClear
     CartCreate
     CartGet
     CartModify
     ItemLookup
     ItemSearch
     SellerListingLookup
     SellerListingSearch
     SellerLookup
     SimilarityLookup

For more information about these calls, please consult the [Product Advertising
API Developer Guide](http://docs.amazonwebservices.com/AWSECommerceService/latest/DG/index.html).

Parsing
-------

By default, queries



License
-------

See LICENSE for details.
