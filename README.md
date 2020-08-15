# bandl

bandl is open source library, provides apis for equity stock, derivatives, commodities, and cryptocurrencies.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install stolgo.

```bash
pip install bandl
```


## Usage

### To import NSE Data Module
```python
from bandl.nse_data import NseData()
nd = NseData() # returns 'NseData object'. can be use to get nse data.
```
#### To get Option chain data
```python
expiry_dates = nd.get_oc_exp_dates(symbol) #return available expiry dates
nd.get_option_chain_excel(symbol,expiry_date,filepath) #dumps option chain to file_path
# or get in pandas dateframe
bn_df = nd.get_option_chain_df(symbol, expiry_date,dayfirst=False) #returns option chain in pandas data frame.
```
#### To get stock historical data.
```python
#get NIFTY 50 data for last one year
dfs = nd.get_data(symbol="NIFTY 50")
data_frame = nd.get_data(symbol,series="EQ",start=None,end=None,periods=None,dayfirst=False) #returns historical data in pandas data frames
```

#### To get FII/DII data.
```python
part_oi_df = nd.get_part_oi_df(start=None,end=None,periods=None,dayfirst=False,workers=None)
```

### To import Nasdaq  Module
```python
from bandl.nasdaq import Nasdaq
ndq = Nasdaq()
```
#### get Nasdaq stock historical data.
```python
#get APPLE data for last one year
dfs = ndq.get_data(symbol="AAPL")
```
### Samco module
```python
from bandl.samco import Samco
sc = Samco(user_id,password,dob)
#get NIFTY data for last one year from samco
dfs = sc.get_data(symbol="NIFTY 50")
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Kindly follow PEP 8 Coding Style guidelines. Refer: https://www.python.org/dev/peps/pep-0008/

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
