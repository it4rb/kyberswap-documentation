# Withdrawable

{% hint style="warning" %}
You are referring to the **`Legacy`** version of KyberSwap docs.

For the most updated information, please refer to:

* [**`Classic`**](broken-reference)
* [**`Elastic`**](../../kyberswap-elastic/)
* [**`Limit Order`**](../../../../kyberswap-solutions/limit-order/)
* [**`Aggregator`**](../../../../kyberswap-solutions/kyberswap-aggregator/)
{% endhint %}

## contract Withdrawable

is [PermissionGroups](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-permissiongroups.md)\ imports ERC20Interface, [PermissionGroups](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-permissiongroups.md)

_Source_: [Withdrawable.sol](https://github.com/KyberNetwork/smart-contracts/blob/master/contracts/Withdrawable.sol)

The Withdrawable contract's role is to allow recovery of any ERC20 token or ETH received in a contract. This will prevent any accidental loss of tokens.

***

### INDEX[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#index) <a href="#index" id="index"></a>

\<AUTOGENERATED\_TABLE\_OF\_CONTENTS>

### REFERENCE[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#reference) <a href="#reference" id="reference"></a>

#### Events[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#events) <a href="#events" id="events"></a>

#### `EtherWithdraw`[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#etherwithdraw) <a href="#etherwithdraw" id="etherwithdraw"></a>

Event for logging the withdrawal of ETH received in a contract.

***

event **EtherWithdraw**(uint amount, address sendTo) | Parameter | Type | Description | | --------- |:-------:|:--------------------:| | `amount` | uint | amount of ETH in wei | | `sendTo` | address | recipient's address |\


#### `TokenWithdraw`[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#tokenwithdraw) <a href="#tokenwithdraw" id="tokenwithdraw"></a>

Event for logging the withdrawal of a token received in a contract.

***

event **TokenWithdraw**(ERC20 token, uint amount, address sendTo) | Parameter | Type | Description | | --------- |:-------:|:-----------------------------:| | `token` | ERC20 | ERC20 token contract address | | `amount` | uint | amount of ERC20 tokens in wei | | `sendTo` | address | recipient's address |\


#### Functions[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#functions) <a href="#functions" id="functions"></a>

#### `withdrawEther`[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#withdrawether) <a href="#withdrawether" id="withdrawether"></a>

Withdraws ETH from the contract.

***

function **withdrawEther**(uint amount, address sendTo) external onlyAdmin | Parameter | Type | Description | | --------- |:-------:|:---------------------:| | `amount` | uint | amount of ETH in wei | | `sendTo` | address | recipient's address | Modifiers: [onlyAdmin](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-permissiongroups.md#onlyadmin)\


#### `withdrawToken`[​](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-withdrawable#withdrawtoken) <a href="#withdrawtoken" id="withdrawtoken"></a>

Withdraws an ERC20 token from the contract.

***

function **withdrawToken**(ERC20 token, uint amount, address sendTo) external onlyAdmin | Parameter | Type | Description | | --------- |:-------:|:-----------------------------:| | `token` | ERC20 | ERC20 token contract address | | `amount` | uint | amount of ERC20 tokens in wei | | `sendTo` | address | recipient's address | Modifiers: [onlyAdmin](https://docs.kyberswap.com/Legacy/api-abi/misc/api\_abi-permissiongroups.md#onlyadmin)
