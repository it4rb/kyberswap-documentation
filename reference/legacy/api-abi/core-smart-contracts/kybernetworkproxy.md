# KyberNetworkProxy

{% hint style="warning" %}
You are referring to the **`Legacy`** version of KyberSwap docs.

For the most updated information, please refer to:

* [**`Classic`**](broken-reference)
* [**`Elastic`**](../../kyberswap-elastic/)
* [**`Limit Order`**](../../../../kyberswap-solutions/limit-order/)
* [**`Aggregator`**](../../../../kyberswap-solutions/kyberswap-aggregator/)
{% endhint %}

## contract KyberNetworkProxy

is [IKyberNetworkProxy](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikybernetworkproxy.md), [ISimpleKyberProxy](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-isimplekyberproxy.md), WithdrawableNoModifiers, Utils5\ imports WithdrawableNoModifiers, Utils5, SafeERC20, [IKyberNetwork](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikybernetwork.md), [IKyberNetworkProxy](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikybernetworkproxy.md), [ISimpleKyberProxy](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-isimplekyberproxy.md), [IKyberHint](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberhint.md)

_Source_: [KyberNetworkProxy.sol](https://github.com/KyberNetwork/smart-contracts/blob/master/contracts/sol6/KyberNetworkProxy.sol)

***

### INDEX[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#index) <a href="#index" id="index"></a>

\<AUTOGENERATED\_TABLE\_OF\_CONTENTS>

### REFERENCE[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#reference) <a href="#reference" id="reference"></a>

#### Events[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#events) <a href="#events" id="events"></a>

#### `KyberNetworkSet`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#kybernetworkset) <a href="#kybernetworkset" id="kybernetworkset"></a>

Event for logging the setting of the KyberNetwork contract address.

***

event **KyberNetworkSet**(IKyberNetwork newKyberNetwork, IKyberNetwork previousKyberNetwork) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `newKyberNetwork` | IKyberNetwork | new kyberNetwork contract address | | `previousKyberNetwork` | IKyberNetwork | old kyberNetwork contract address | Signature: 0x8936e1f096bf0a8c9df862b3d1d5b82774cad78116200175f00b5b7ba3010b02

\


#### `KyberHintHandlerSet`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#kyberhinthandlerset) <a href="#kyberhinthandlerset" id="kyberhinthandlerset"></a>

Event for logging the setting of the KyberHintHandler contract address.

***

event **KyberHintHandlerSet**(IKyberHint kyberHintHandler) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `kyberHintHandler` | IKyberHint | kyberHintHandler contract address |

Signature: 0x6deb3a98fd141d661e9c0fb2d847541cc0c629cfb100c61011a76f57cb3b3a9b

\


#### Functions[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#functions) <a href="#functions" id="functions"></a>

#### `trade`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kybernetworkproxy#trade) <a href="#trade" id="trade"></a>

Executes a Best-of-All trade (no reserve routing) between src and dest token and send dest tokens to destAddress; platform fee is ignored and is pre-Katalyst/backwards compatible.

***

function **trade**(IERC20 src, uint256 srcAmount, IERC20 dest, address payable destAddress, uint256 maxDestAmount, uint256 minConversionRate, address payable platformWallet) external payable override returns (uint256) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `src` | IERC20 | source ERC20 token contract address | | `srcAmount` | uint256 | source ERC20 token amount in its token decimals | | `dest` | IERC20 | destination ERC20 token contract address | | `destAddress` | address | recipient address for destination ERC20 token | | `maxDestAmount` | uint256 | limit on the amount of destination tokens | | `minConversionRate` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | | `platformWallet` | address | address receiving the platform fee | **Returns:**\ Amount of actual destination tokens in twei

\
\### \`tradeWithHint\` Executes a trade between src and dest token and send dest tokens to destAddress; platform fee is ignored and is pre-Katalyst/backwards compatible. \_\_\_ function \_\_tradeWithHint\_\_(ERC20 src, uint256 srcAmount, ERC20 dest, address payable destAddress, uint256 maxDestAmount, uint256 minConversionRate, address payable walletId, bytes hint) external payable override returns (uint256) | Parameter | Type | Description | | ------------------- |:-------:|:--------------------------------------------------------------------:| | \`src\` | ERC20 | source ERC20 token contract address | | \`srcAmount\` | uint256 | source ERC20 token amount in its token decimals | | \`dest\` | ERC20 | destination ERC20 token contract address | | \`destAddress\` | address | recipient address for destination ERC20 token | | \`maxDestAmount\` | uint256 | limit on the amount of destination tokens | | \`minConversionRate\` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | | \`walletId\` | address | deprecated | | \`hint\` | bytes | hint in bytes for reserve routing | \*\*Returns:\*\*\ Amount of actual destination tokens in twei\
\### \`tradeWithHintAndFee\` Executes a trade between src and dest token and send dest tokens to destAddress; includes the platform fee. \_\_\_ function \_\_tradeWithHintAndFee\_\_(IERC20 src, uint256 srcAmount, IERC20 dest, address payable destAddress, uint256 maxDestAmount, uint256 minConversionRate, address payable platformWallet, uint256 platformFeeBps, bytes hint) external payable override returns (uint256 destAmount) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`src\` | IERC20 | source ERC20 token contract address | | \`srcAmount\` | uint256 | source ERC20 token amount in its token decimals | | \`dest\` | IERC20 | destination ERC20 token contract address | | \`destAddress\` | address | recipient address for destination ERC20 token | | \`maxDestAmount\` | uint256 | limit on the amount of destination tokens | | \`minConversionRate\` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | | \`platformWallet\` | address | address receiving the platform fee | | \`platformFeeBps\` | uint256 | platform fee in BPS to be used in this trade | | \`hint\` | bytes | hint in bytes for reserve routing | \*\*Returns:\*\*\ destAmount - Amount of actual destination tokens in twei\
\### \`swapTokenToToken\` Makes a simple ERC20 -> ERC20 token trade. \_\_\_ function \_\_swapTokenToToken\_\_(IERC20 src, uint256 srcAmount, IERC20 dest, uint256 minConversionRate) external override returns (uint256) | Parameter | Type | Description | | ------------------- |:-------:|:--------------------------------------------------------------------:| | \`src\` | IERC20 | source ERC20 token contract address | | \`srcAmount\` | uint256 | wei amount of source ERC20 token | | \`dest\` | IERC20 | destination ERC20 token contract address | | \`minConversionRate\` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | \*\*Returns:\*\*\ Amount of actual destination tokens in twei\
\### \`swapEtherToToken\` Execute a simple ETH -> ERC20 token trade. \_\_\_ function \_\_swapEtherToToken\_\_(IERC20 token, uint256 minConversionRate) external override returns (uint256) | Parameter | Type | Description | | ------------------- |:-------:|:--------------------------------------------------------------------:| | \`token\` | IERC20 | destination ERC20 token contract address | | \`minConversionRate\` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | \*\*Returns:\*\*\ Amount of actual destination tokens in twei\
\### \`swapTokenToEther\` Execute a simple ERC20 token -> ETH trade. \_\_\_ function \_\_swapTokenToEther\_\_(IERC20 token, uint256 srcAmount, uint256 minConversionRate) external override returns (uint256) | Parameter | Type | Description | | ------------------- |:-------:|:-------------------------------------------------------------------:| | \`token\` | IERC20 | destination ERC20 token contract address | | \`srcAmount\` | uint256 | source ERC20 token amount in its token decimals | | \`minConversionRate\` | uint256 | minimum conversion rate; trade is canceled if actual rate is lower | \*\*Returns:\*\*\ destAmount - Amount of actual destination ETH wei\
\### \`getExpectedRate\` Get the token conversion rate without platform fee; pre-Katalyst/backwards compatible. \_\_\_ function \_\_getExpectedRate\_\_(ERC20 src, ERC20 dest, uint256 srcQty) external view override returns (uint256 expectedRate, uint256 worstRate) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`src\` | ERC20 | source ERC20 token contract address | | \`dest\` | ERC20 | destination ERC20 token contract address | | \`srcQty\` | uint256 | source ERC20 token amount in its token decimals | \*\*Returns:\*\*\ expectedRate - conversion rate of the src and dest tokens after deducting the network fee. worstRate - 97% rate of the conversion rate, allowaing a 3% buffer for use in minConversionRate in trade.\
\### \`getExpectedRateAfterFee\` Get the token conversion rate after processing the hint and includes the platform fee. \_\_\_ function \_\_getExpectedRateAfterFee\_\_(IERC20 src, IERC20 dest, uint256 srcQty, uint256 platformFeeBps, bytes hint) external view override returns (uint256 expectedRate) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`src\` | IERC20 | source ERC20 token contract address | | \`dest\` | IERC20 | destination ERC20 token contract address | | \`srcQty\` | uint256 | source ERC20 token amount in its token decimals | | \`platformFeeBps\` | uint256 | platform fee in BPS | | \`hint\` | bytes | hint in bytes for reserve routing | \*\*Returns:\*\*\ expectedRate - conversion rate of the src and dest tokens after deducting the network and platform fee.\
\### \`maxGasPrice\` Get the maximum gas price limit. \_\_\_ function \_\_maxGasPrice\_\_() external view returns (uint256)\ \*\*Returns:\*\*\ The maximum gas price limit\
\### \`enabled\` Returns if the network is enabled or not. \_\_\_ function \_\_enabled\_\_() external view returns (bool)\ \*\*Returns:\*\*\ \`true\` if the network is enabled, \`false\` otherwise.
