.. _example:

Example
============

Test the code::

    #CFOpenData/DataExtract/get17Scores.py
    
This will call::

    #CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py

Get 2017 data::

    cd DataExtract
    python get17Scores.py
    
This writes the file::

    #DataExtract/Scores/2017_Scores_Men.csv

The last name is Ron Lyman. Can't work out why it isn't Sean Wray like in the URL
Ron Lyman is last on the second last page. TO DO increase the loop by 1

It broke for me once and gave the following error message. However, running the code again seemed to be fine:

.. code:: python

    Scores/2017_Scores_Men.csv written to page 1050
    Traceback (most recent call last):
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/connector.py", line 375, in connect
        proto = yield from self._create_connection(req)
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/connector.py", line 632, in _create_connection
        _, proto = yield from self._create_direct_connection(req)
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/connector.py", line 643, in _create_direct_connection
        hosts = yield from self._resolve_host(req.url.raw_host, req.port)
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/connector.py", line 615, in _resolve_host
        self._resolver.resolve(host, port, family=self._family)
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/resolver.py", line 30, in resolve
        host, port, type=socket.SOCK_STREAM, family=family)
      File "/Users/Ray/anaconda/lib/python3.6/concurrent/futures/thread.py", line 56, in run
        result = self.fn(*self.args, **self.kwargs)
      File "/Users/Ray/anaconda/lib/python3.6/socket.py", line 745, in getaddrinfo
        for res in _socket.getaddrinfo(host, port, family, type, proto, flags):
    socket.gaierror: [Errno 8] nodename nor servname provided, or not known

    The above exception was the direct cause of the following exception:

    Traceback (most recent call last):
      File "get17Scores.py", line 56, in <module>
        main()
      File "get17Scores.py", line 51, in main
        CFOpenData = extractScoresMainSite.extractScoresMainSite(div,scal,year,numberperpage)
      File "/Volumes/SAMSUNG/WORK/POSTDOC_RSMAS_2016/PYTHON_dev/CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py", line 251, in __init__
        self.startEventLoop(i*nper,nper) # 0, 50; 50, 50; 100, 50; ...
      File "/Volumes/SAMSUNG/WORK/POSTDOC_RSMAS_2016/PYTHON_dev/CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py", line 200, in startEventLoop
        loop.run_until_complete(future)
      File "/Users/Ray/anaconda/lib/python3.6/asyncio/base_events.py", line 467, in run_until_complete
        return future.result()
      File "/Volumes/SAMSUNG/WORK/POSTDOC_RSMAS_2016/PYTHON_dev/CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py", line 177, in loopPages
        results = await asyncio.gather(*async_list) 
      File "/Volumes/SAMSUNG/WORK/POSTDOC_RSMAS_2016/PYTHON_dev/CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py", line 70, in downloadPage
        return await self.getPage(nParams, session)
      File "/Volumes/SAMSUNG/WORK/POSTDOC_RSMAS_2016/PYTHON_dev/CFOpenData/DataExtract/extractScoresMainSite/extractScoresMainSite.py", line 86, in getPage
        async with session.get(self.basepath, params=params, headers=headers) as response:
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/client.py", line 626, in __aenter__
        self._resp = yield from self._coro
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/client.py", line 225, in _request
        conn = yield from self._connector.connect(req)
      File "/Users/Ray/anaconda/lib/python3.6/site-packages/aiohttp/connector.py", line 380, in connect
    .format(key, exc.strerror)) from exc
    aiohttp.client_exceptions.ClientConnectorError: [Errno 8] Cannot connect to host games.crossfit.com:443 ssl:True [nodename nor servname provided, or not known]
