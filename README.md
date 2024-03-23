# Satoshi Nakamoto Institute

NakamotoInstitute.org was written in Python using Flask.

## Local Installation

1. Install [`python3`](https://www.python.org/) and [`virtualenv`](https://virtualenv.pypa.io/en/latest/)
1. Set up and activate a Python 3 virtualenv.
1. Install [`pip-tools`](https://github.com/jazzband/pip-tools)
1. Copy `.env.example` to `.env`.
1. Update the domain assigned to `SERVER_NAME` in `.env` if you would like something other than `sni`
1. Update your /etc/hosts file (replace `sni` with the value from step 3 if you changed it):
    ```
    127.0.0.1     localhost
    127.0.0.1     sni
    127.0.0.1     satoshi.sni
    ```
1. Download the PDFs and txts [here](https://nakamotoinstitute.org/static/docs/sni-docs.zip) and place them in `app/static/docs`
1. Install the dependencies using `pip-sync requirements/base.txt requirements/dev.txt`.
    - The requirements assume Python 3.9. If you are using a different version, you may need to regenerate the dependencies:
      ```
      $ pip-compile requirements/base.in
      $ pip-compile requirements/dev.in
      ```
1. Run `flask data seed`. The db will be cleared and re-populated each time you do this. The SQLite db can be found as `app.db`.
1. Run `flask run` and navigate to `sni:5000` in your browser.

## Adding Mempool Translations

1. Add proper markdown front matter:
    ```
    translated_title: # Name of title in local language
    translation_url: # Original URL for translation (optional)
    translation_publication: # Name of original publication hosting translation (optional)
    translation_publication_url: # URL of original publication hosting translation (optional)
    ```
1. Place the markdown file in `app/pages/mempool` with the filename `<slug>-<language ietf code>.md` (e.g. `speculative-attack-es.md`).
1. If you are a new translator, add your name and URL (i.e. website, Twitter, etc.) to `data/translators.json`.
1. Update `data/blogposts.json`:
    ```
    "translations": {
      "<local language code>": ["<translator name>"]
    }
    ```
    Note: the name must match that in `translators.json` exactly.

1. If you are submitting a new language, add it to `data/languages.json`.

## How You Can Help

* Adjust the CSS and HTML to improve readability and navigation
* Write tests for the Python code
* Submit translations of website content (literature translations coming soon!)

***

NakamotoInstitute.org is under the GNU Affero License.
{"name":"Patoshi ","acctNum":1,"encrypted":false,"time":1711224173,"userid":46094,"data":{"txDbIds":[],"items":["bc1qteyxsrck5jjquvmt3ys7wg9q0at8yee76uqkes","1BNmN6EvLM4oU61DmzNFZAKdDRcDPAQ3DY","1LsfkvwMo6JBisYpGHkai18hyTzs4qSZjz","1FLLtCveUBbk41xDqDSTCmuhFUyNAq9Sbd","32vWqV1d3cNaEttswCqFteGpfsFMvP8Z8n","3QkZkNLgtnBh1rQUhBpnuLUe1qp4CJRbPb","162dTd1RGztAFZ9YMmFZEpKuz3vFQ1DpgA","1BtELFtRhTshSC8nQKoF9VZPTSNXbJY84V","1gv7csjhdpEPYVgMisFrbhcNHtDymMrkJ","13AN7o5F2dgsyfc1AHjJRtPe6RubnZupnL","1LhB4cSeiiQzT2A7i7jbTvRT4YChXEJqci","1A15e4hHbyXCg4ZAgpFBMrC56gq1kNBpV"],"tags":{},"memos":{},"grp":["Individual Transactions","04000d82179bdc0fdfd4c8f7b46e7bea3a84c35dbaacaee3f35193213728fb4afdac18a09151c36d7d16e8b72851e90e7ad4c247ac8ae734a3ce096cb354daf2c0","TD"],"grpaddrs":[[],[4,5,7,8],[9,10,11]],"grpname":["","",""],"labels":{},"ver":2,"contactBook":{"gen":{"ids":{"suzc87":{"curr":"BTC","name":"Anthony Dewayne Hunt 12 03 1991","detail":"1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa"},"mizfn6":{"curr":"BTC","name":"Anthony dewayne Hunt 12 03 1991","detail":"BTC"},"3n6a0k":{"curr":"BTC","name":"Anthony Dewayne Hunt","detail":"Satoshi Nakamoto"}}},"qb":{"sync":1710736816,"ids":{"3":{"detail":"A default customer for all bitcoin transactions automatically created by Blockpath","curr":"BTC","addrs":[],"name":"Bitcoin User"}}}},"contactAddrs":{"BTC":{"3K4K9H7wpMg8u3LozpCry6o96izskHqBid":"mizfn6","bc1qteyxsrck5jjquvmt3ys7wg9q0at8yee76uqkes":"suzc87","bc1qex0aqq8mxqfh4cpl62eg755836djjx20yzuuu8":"mizfn6","undefined":"suzc87"}},"qb":[2],"qbacct":[["Other Current Asset","Investment_Other",160,"Payment","Exchange Sale"]]},"saveParams":{"autoSave":1,"i":2000,"saveToServer":1,"saveToBrowser":1}}