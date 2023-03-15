# IKyberStaking

{% hint style="warning" %}
You are referring to the **`Legacy`** version of KyberSwap docs.

For the most updated information, please refer to:

* **``**[**`Classic`**](../../../../liquidity-solutions/kyberswap-classic/)**``**
* **``**[**`Elastic`**](../../../../liquidity-solutions/kyberswap-elastic/)**``**
* **``**[**`Limit Order`**](../../../../kyberswap-solutions/limit-order/)**``**
* **``**[**`Aggregator`**](../../../../kyberswap-solutions/kyberswap-aggregator/)**``**
{% endhint %}

## interface IKyberStaking

is [IEpochUtils](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-iepochutils.md) imports [IEpochUtils](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-iepochutils.md)

_Source_: [IKyberStaking.sol](https://github.com/KyberNetwork/smart-contracts/blob/master/contracts/sol6/Dao/IKyberStaking.sol)

***

### INDEX[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#index) <a href="#index" id="index"></a>

\<AUTOGENERATED\_TABLE\_OF\_CONTENTS>

### REFERENCE[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#reference) <a href="#reference" id="reference"></a>

#### Events[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#events) <a href="#events" id="events"></a>

#### `Delegated`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#delegated) <a href="#delegated" id="delegated"></a>

Event for logging the delegation to a representative.

***

event **Delegated**(address staker, address representative, uint256 epoch, bool isDelegated) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `staker` | address | staker's address | | `representative` | address | representative's address delegated to | | `epoch` | uint256 | epoch number where delegation happens | | `isDelegated` | bool | `true` if staker has delegated to a new representative, otherwise `false` | Signature: 0xfbb976ae5268347766b726bd1edba29af0fe16f9c505fbd3b9a10cb6d00cfa3d

\


#### `Deposited`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#deposited) <a href="#deposited" id="deposited"></a>

Event for logging the deposit of KNC into the staking contract.

***

event **Deposited**(uint256 curEpoch, address staker, uint256 amount) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `curEpoch` | uint256 | current epoch number where KNC was deposited | | `staker` | address | staker's address | | `amount` | uint256 | amount of KNC deposited in twei | Signature: 0x1599c0fcf897af5babc2bfcf707f5dc050f841b044d97c3251ecec35b9abf80b

\


#### `Withdraw`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#withdraw) <a href="#withdraw" id="withdraw"></a>

Event for logging the withdrawal of KNC from the staking contract.

***

event **Withdraw**(uint256 curEpoch, address staker, uint256 amount) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `curEpoch` | uint256 | current epoch number where KNC was deposited | | `staker` | address | staker's address | | `amount` | uint256 | amount of KNC withdrawn in twei | Signature: 0x9da6493a92039daf47d1f2d7a782299c5994c6323eb1e972f69c432089ec52bf

\


#### Functions[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#functions) <a href="#functions" id="functions"></a>

#### `deposit`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstaking#deposit) <a href="#deposit" id="deposit"></a>

Deposit and stake KNC.

***

function **deposit**(uint256 amount) external | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `amount` | uint256 | amount of KNC to deposit in twei |

\
\### \`delegate\` Sets the delegation to a representative, and only takes effect on the next epoch \_\_\_ function \_\_delegate\_\_(address dAddr) external | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`dAddr\` | address | representative's address to delegate to |\
\### \`withdraw\` Unstakes and withdraws KNC from the staking contract. \_\_\_ function \_\_withdraw\_\_(uint256 amount) external | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`amount\` | uint256 | amount of KNC to withdraw in twei |\
\### \`getStakerData\` Iterates through all the epochs and returns the staker data up to current epoch + 1. \_\_\_ function \_\_getStakerData\_\_(address staker, uint256 epoch) external returns (uint256 stake, uint256 delegatedStake, address representative) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`staker\` | address | staker's address | | \`epoch\` | uint256 | epoch number to start iterating from to get staker data | \*\*Returns:\*\*\ stake - total amount of KNC staked in twei delegatedStake - amount of KNC delegated to the staker's address in twei representative - if the staker is delegating, this shows the address he is delegating to\
\### \`getLatestStakerData\` Returns the staker data for the latest epoch. \_\_\_ function \_\_getLatestStakerData\_\_(address staker) external returns (uint256 stake, uint256 delegatedStake, address representative) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`staker\` | address | staker's address | \*\*Returns:\*\*\ stake - total amount of KNC staked in twei delegatedStake - amount of KNC delegated to the staker's address in twei representative - if the staker is delegating, this shows the address he is delegating to\
\### \`getStakerRawData\` Returns the raw staker data up to current epoch + 1. Returns 0 values if staker data is uninitialized. \_\_\_ function \_\_getStakerRawData\_\_(address staker, uint256 epoch) external returns (uint256 stake, uint256 delegatedStake, address representative) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`staker\` | address | staker's address | | \`epoch\` | uint256 | epoch number to get staker raw data |

**Returns:**\ stake - total amount of KNC staked in twei delegatedStake - amount of KNC delegated to the staker's address in twei representative - if the staker is delegating, this shows the address he is delegating to