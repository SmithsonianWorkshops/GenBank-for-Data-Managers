# A Data Manager's Guide to GenBank

These are the materials for a Brown Bag lecture about GenBank.

## In-person examples on searching GenBank

First, let's all go to GenBank's homepage at https://www.ncbi.nlm.nih.gov/genbank/.

Our first sample search will be one that we saw earlier in the presentation -- to find all sequences that are labelled as coming from USNM:

`collection USNM[properties]`

I want to point out that a lot of these GenBank search "tags" can be shortened, which you might come across. So that you believe me, try the following search:

`collection usnm[prop]`

You can combine multiple search terms together with the keywords AND, OR, and NOT. They have to be capitalized to use correctly. Let's try the same search and include the plants from our collections.

`collection usnm[prop] OR collection us[prop]`

This search on collections only picks up records that have a specimen_voucher value in the structured triplet format. Let's use the text search feature to find records that might be missed.

`usnm[text] NOT (collection usnm[prop])`

You can also search on specific taxonomic groups.

`collection usnm[prop] AND aves[organism]`

And authors:

`trizna[author]`

BARCODE keyword records:

`barcode[keyword]`

And finally, you can filter results by publication date:

`(collection usnm[Properties] OR collection us[Properties]) AND (2016/07/27 : 2017/07/27[PDAT]) AND (("2016/07/27"[PDAT] : "2017/07/27"[PDAT]))`