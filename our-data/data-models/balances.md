# Address Balance Model

Flipside records the balance for every address that is involved within a transaction, in addition to account for such things as genesis allocation and mint-time distributions.&#x20;

Balances for each address are rolled up into a daily balance table, account for every address we've seen on the network.

#### Daily Balance Table Schema

| Field         | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| date          | The date the balance was recorded.                           |
| address       | The address the balance was recorded for.                    |
| balance       | The decimal adjusted balance recorded for the address.       |
| balance\_usd  | The USD equivalent of the recorded balance.                  |
| balance\_type | The type of balance, i.e. 'liquid', 'staked', 'locked', etc. |
| currency      | The on-chain asset being recorded.                           |

#### Dataset Features:

* Current day data is updated throughout the day to provide an up-to-date reading of balances.&#x20;
* If an account is inactive one day, their previous day's balance is carried forward.
* The currency field denotes which on-chain asset is being recorded.
* Addresses are labeled according to our Label System.&#x20;
* Label fields are left blank (NULL) if the address is unlabeled.
