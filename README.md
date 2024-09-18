# arkeoguide

ARKEO Network: Quick Guide with Code

## 1. Data Providers Management
   
### 1.1 Registering a Data Provider

To register a data provider, use the ARKEO CLI:

```
arkeod tx arkeo register-provider <provider-address> --bond <amount> --from <your-key> --chain-id <chain-id> --gas auto
```
Parameters:

<provider-address>: Your provider's blockchain address.

<amount>: The amount of the bond to stake.

<your-key>: Your wallet key.

<chain-id>: The chain ID of the ARKEO network.

### 1.2 Updating Provider Information

Update provider data feed information:

```
arkeod tx arkeo update-provider <provider-address> --data <data-type> --bond <new-amount> --from <your-key> --chain-id <chain-id> --gas auto
```
## 2. Sentinel Management
   
### 2.1 Registering as a Sentinel

Register as a sentinel to monitor the network:

```
arkeod tx arkeo register-sentinel <sentinel-address> --bond <amount> --from <your-key> --chain-id <chain-id> --gas auto
```
### 2.2 Reporting Issues

Sentinels can report issues using:

```
arkeod tx arkeo report-issue <provider-address> --reason <reason-code> --from <your-key> --chain-id <chain-id> --gas auto
```
## 3. Contracts Management
   
### 3.1 Creating a Contract
   
Create a new contract for data access:

```
arkeod tx arkeo create-contract <provider-address> --data-type <data-type> --fee <access-fee> --usage-limits <limits> --from <your-key> --chain-id <chain-id> --gas auto
```
Parameters:

<data-type>: Type of data you are providing (e.g., price-feed).

<access-fee>: Fee for data access.

<limits>: Any usage restrictions.

3.2 Updating Contracts

Update contract terms:

```
arkeod tx arkeo update-contract <contract-id> --new-fee <new-fee> --new-limits <new-limits> --from <your-key> --chain-id <chain-id> --gas auto
```
## 4. Contracts Query
   
### 4.1 Querying Contracts

To get information about a contract:

```
arkeod query arkeo contract <contract-id>
```
Example output:

```
{
  "contract_id": "123",
  "provider": "provider-address",
  "data_type": "price-feed",
  "fee": "10 ARKEO",
  "limits": "1000 requests/month"
}
```
### 4.2 Tracking Usage

Check contract usage metrics:

```
arkeod query arkeo usage <contract-id> --from <consumer-address>
```
