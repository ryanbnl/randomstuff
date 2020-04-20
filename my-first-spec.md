# DP3T Backend Specification

The backend consists of two main functions: providing a set <blabla short explaination in simple english or for simple english people>.


## Overview for app developers

To check for infection: first load the list of data dumps from /exposed.

for each (dump-you-havent-processed-or-which-has-a-new-hash)

	load data from `uri_filter` into your cocofilter
	run your local interactions through the cocofilter.

	if ( interaction in cocofilter )
		download the big list of ids from uri_data and check them
	else
		stop you're not exposed

## /exposed

GET /{version}/exposed

Response:

	application/json

	{
		[{
			time_stamp_from: 'isodatetime',
			time_stamp_to: 'iso',
			hash: 'hash_which_identifies_this_for_changes'
			uri_filter: '/whatever/the/uri/is/for/the/coocoofilter'
			uri_data: '/whatever/the/uri/is/for/the/big/binary'
		}, ...]

	}

Response description:

Returns an json array containing a list of data batches in reverse-chronological order - so the latest update comes first. The timespan of the file is included along with a relative url to the coco filter binary and to the data file binary.

...
...
...

