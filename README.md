Vogel het Uit API
=================

The Vogel het Uit API can be seen at http://sverhoeven.github.io/vogelhetuit-api

Or at http://docs.vogelhetuit.apiary.io/

Generate html
-------------

    aglio -t default-multi -i apiary.apib -o index.html

Testing
-------

To test api documentation against server backend.

First install `dredd` (https://github.com/apiaryio/dredd) with:

    sudo npm install -g dredd

To allow for server to be run with a path edit `/usr/lib/node_modules/dredd/lib/execute-transaction.js`.

	-    path: request['uri'],
	+    path: parsedUrl['pathname'] + request['uri'],

Run tests with:

	dredd apiary.apib http://localhost:8000/app_dev.php/api -u admin:adminpw -m GET
