# Equinox
A set of command line tools for tracking equity markets.

# Equinox Fetch:

Requirements: Ubuntu 17.04 Linux (Untested in other OS environments).

A command line tool to download a list of stocks.

Installation:

Just download the Equinox_Fetch file to a convenient folder. Eg: /home/info/Equinox

Launching the application: 

Terminal: ./Equinox_Fetch

Usage: Equinox_Fetch [-h] [--start START_DATE] [--end END_DATE]
                     [--stocks [STOCKS [STOCKS ...]]] [--index FILE]
                     [--header HEADER] [--save_dir FILE] [--source SOURCE]
                     [--retries RETRIES] [--workers WORKERS] [--delay DELAY]
                     [--encoding_in ENCODING_IN] [--encoding_out ENCODING_OUT]

	optional arguments:
  	-h, --help      Show this help message and exit.
  	--start         Starting date for the stock data: yyyy,mm,dd format.
  	--end           Ending date for the stock data: yyyy,mm,dd format.
  	--stocks        A command-line list of stocks for downloading. Eg:
                        'AAPL' 'INTC' 'NVDA'
  	--index         List of stocks for the index fund, load this list from
                        a csv file.
  	--header        Specify whether the index stocks list file has a
                        header.
  	--save_dir      Location for saving the downloaded stock data.
  	--source        Specify the stock market data source. Eg: yahoo
  	--retries       Maximum number of retries before quitting.
  	--workers       Maximum number of CPU cores for processing data, the
                        upper ceiling is self adjusting to maximum number of
                        available CPU cores.
  	--delay         Time delay between each worker sized chunks of server
                        stock data query, default wait time = 10s, minimum
                        wait time = 2s.
  	--encoding_in   Encoding used for input csv files. eg: utf8, cp1252
  	--encoding_out  Encoding used for output csv files. eg: utf8, cp1252

Example usage using a list file (On Linux): info@moad:~/Equinox$ ./Equinox_Fetch --start 2007,01,01 --end 2017,01,01 --index '/home/info/SP500-List.csv' --save_dir '/home/info/data' --source yahoo --workers 4 --delay 10 --retries 30 --encoding_in cp1252 --encoding_out utf8

Example usage by entering individual set of stock symbols (On Linux): info@moad:~/Equinox$ ./Equinox_Fetch --start 2007,01,01 --end 2017,01,01 --stocks AMD AAPL GOOG INTC MSFT NVDA --save_dir '/home/info/data' --source yahoo --workers 4 --delay 10 --retries 30 --encoding_in cp1252 --encoding_out utf8