# A Data Manager's Guide to GenBank

These are the materials for a Brown Bag talk about GenBank, given to NMNH collections data managers on July 27, 2017.

## Call for beta testers

Mike is currently developing software to allow for downloading GenBank search results in spreadsheet format.

You can sign up to help test and provide feedback here: https://goo.gl/forms/WLAxBDXEP6A53Hzx1

## In-person examples on searching GenBank

First, let's all go to GenBank's homepage at https://www.ncbi.nlm.nih.gov/genbank/.

* Our first sample search will be one that we saw earlier in the presentation -- to find all sequences that are labelled as coming from USNM:

	`collection USNM[properties]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore?term=collection%20USNM%5Bproperties%5D)

* I want to point out that a lot of these GenBank search "tags" can be shortened, which you might come across. So that you believe me, try the following search:

	`collection usnm[prop]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=collection+usnm%5Bprop%5D)

* You can combine multiple search terms together with the keywords AND, OR, and NOT. They have to be capitalized to use correctly. Let's try the same search and include the plants from our collections.

	`collection usnm[prop] OR collection us[prop]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=collection+usnm%5Bprop%5D+OR+collection+us%5Bprop%5D)

* This search on collections only picks up records that have a specimen_voucher value in the structured triplet format. Let's use the text search feature to find records that might be missed.

	`usnm[text] NOT (collection usnm[prop])`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=usnm%5Btext%5D+NOT+(collection+usnm%5Bprop%5D))

* You can also search on specific taxonomic groups.

	`collection usnm[prop] AND aves[organism]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=collection+usnm%5Bprop%5D+AND+aves%5Borganism%5D)

* And authors:

	`trizna[author]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=trizna%5Bauthor%5D)

* BARCODE keyword records:

	`barcode[keyword]`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=barcode%5Bkeyword%5D)

* Finally, you can filter results by publication date. Here's a search to find ALL records with structured US and USNM vouchers published in the last year:

	`(collection usnm[Properties] OR collection us[Properties]) AND (2016/07/27[PDAT] : 2017/07/27[PDAT])`

	[Link](https://www.ncbi.nlm.nih.gov/nuccore/?term=(collection+usnm%5BProperties%5D+OR+collection+us%5BProperties%5D)+AND+(2016%2F07%2F27%5BPDAT%5D+%3A+2017%2F07%2F27%5BPDAT%5D))