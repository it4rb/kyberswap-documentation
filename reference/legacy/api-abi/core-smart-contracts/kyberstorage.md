# KyberStorage

{% hint style="warning" %}
You are referring to the **`Legacy`** version of KyberSwap docs.

For the most updated information, please refer to:

* [**`Classic`**](broken-reference)
* [**`Elastic`**](../../kyberswap-elastic/)
* [**`Limit Order`**](../../../../kyberswap-solutions/limit-order/)
* [**`Aggregator`**](../../../../kyberswap-solutions/kyberswap-aggregator/)
{% endhint %}

## contract KyberStorage

is [IKyberStorage](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstorage.md), PermissionGroupsNoModifiers, Utils5\ imports [IKyberHistory](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberhistory.md), [IKyberStorage](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikyberstorage.md), [IKyberNetwork](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-ikybernetwork.md), PermissionGroupsNoModifiers, Utils5

_Source_: [KyberStorage.sol](https://github.com/KyberNetwork/smart-contracts/blob/master/contracts/sol6/KyberStorage.sol)

***

### INDEX[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#index) <a href="#index" id="index"></a>

\<AUTOGENERATED\_TABLE\_OF\_CONTENTS>

### REFERENCE[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#reference) <a href="#reference" id="reference"></a>

#### Events[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#events) <a href="#events" id="events"></a>

#### `KyberNetworkUpdated`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#kybernetworkupdated) <a href="#kybernetworkupdated" id="kybernetworkupdated"></a>

Event logging the setting of the new KyberNetwork contract address.

***

event **KyberNetworkUpdated**(IKyberNetwork newKyberNetwork) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `newKyberNetwork` | IKyberNetwork | new contract address | Signature: 0x18970d46ac8a7d7e0da90e1bebb0be3e87ffc7705fc09d3bba5373d59b7a12aa

\


#### `RemoveReserveFromStorage`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#removereservefromstorage) <a href="#removereservefromstorage" id="removereservefromstorage"></a>

Event logging the removal of a reserve address and its corresponding reserve ID from storage.

***

event **RemoveReserveFromStorage**(address reserve, bytes32 reserveId) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `reserve` | address | address of the reserve | | `reserveId` | bytes32 | reserve ID of the reserve | Signature: 0xa5cd88a226efb041d6bdc0ac32964affd749b8a7c4d9e0c4ffba575e7180b1c9

\


#### `AddReserveToStorage`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#addreservetostorage) <a href="#addreservetostorage" id="addreservetostorage"></a>

Event logging the addition of a reserve address and its corresponding reserve ID to storage.

***

event **AddReserveToStorage**(address reserve, bytes32 reserveId, ReserveType reserveType, address rebateWallet) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `reserve` | address | address of the reserve | | `reserveId` | bytes32 | resereserve ID of the reserverve ID | | `reserveType` | ReserveType | the reserve type, where 0 - none, 1 - FPR, 2 - APR, 3 - Bridge, 4 - Utility, 5 - Custom, 6 - Orderbook, 7 - Last | | `rebateWallet` | address | rebate wallet address of the reserve | Signature: 0x15ae42ec2557dbe988b80500b4faab3c4b8cc095753df46cdc860050d994dcae

\


#### `ReserveRebateWalletSet`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#reserverebatewalletset) <a href="#reserverebatewalletset" id="reserverebatewalletset"></a>

Event logging the setting of the rebate wallet address of the reserve.

***

event **ReserveRebateWalletSet**(bytes32 reserveId, address rebateWallet) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `reserveId` | bytes32 | reserve ID of the reserve | | `rebateWallet` | address | rebate wallet address of the reserve | Signature: 0x42cac9e63e37f62d5689493d04887a67fe3c68e1d3763c3f0890e1620a0465b3

\


#### `ListReservePairs`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#listreservepairs) <a href="#listreservepairs" id="listreservepairs"></a>

Event logging the listing of a token pair for a reserve.

***

event **ListReservePairs**(bytes32 reserveId, address reserve, IERC20 src, IERC20 dest, bool add) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | `reserveId` | bytes32 | reserve ID of the reserve | | `reserve` | address | address of the reserve | | `src` | IERC20 | source token | | `dest` | IERC20 | destination token | | `add` | bool | `true` if listing the token, otherwise `false` | Signature: 0xfcdbd685961328a43b4aa133de257d3769cc01891b4ee00fd5058e5aa3564ca5

\


#### Functions[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#functions) <a href="#functions" id="functions"></a>

#### `getReserves`[​](https://docs.kyberswap.com/Legacy/api-abi/core-smart-contracts/api\_abi-kyberstorage#getreserves) <a href="#getreserves" id="getreserves"></a>

Returns all the listed reserve addresses in the network.

***

function **getReserves**() external view returns (IKyberReserve\[]) **Returns:**\ An array of all reserves

\
\### \`getReservesPerType\` Returns an a array of reserve IDs for the given reserve type. \_\_\_ function \_\_getReservesPerType\_\_(ReserveType resType) external view returns (bytes32\[]) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`resType\` | ReserveType | the reserve type, where 0 - none, 1 - FPR, 2 - APR, 3 - Bridge, 4 - Utility, 5 - Custom, 6 - Orderbook, 7 - Last | \*\*Returns:\*\*\ Array of reserve IDs.\
\### \`getReserveId\` Returns the reserveID of the reserve given the address. \_\_\_ function \_\_getReserveId\_\_(address reserve) external view override returns (bytes32) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserve\` | address | reserve address | \*\*Returns:\*\*\ 32-byte reserve ID\
\### \`getReserveIdsFromAddresses\` Returns a list of reserveIDs from a list of given addresses. \_\_\_ function \_\_getReserveIdsFromAddresses\_\_(address\[] reserveAddresses) external view override returns (bytes32\[] reserveIds) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveAddresses\` | address\[] | list of reserve addresses | \*\*Returns:\*\*\ reserveIds - array of 32-byte reserve IDs\
\### \`getReserveAddressesFromIds\` Returns a list of addresses from a list of given reserve IDs. \_\_\_ function \_\_getReserveAddressesFromIds\_\_(bytes32\[] reserveIds) external view override returns (address\[] reserveAddresses) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveIds\` | bytes32\[] | list of reserve IDs | \*\*Returns:\*\*\ reserveAddresses - array of reserve addresses\
\### \`getRebateWalletsFromIds\` Returns a list of rebates wallets from a list of given reserve IDs. \_\_\_ function \_\_getRebateWalletsFromIds\_\_(bytes32\[] reserveIds) external view override returns (address\[] rebateWallets) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveIds\` | bytes32\[] | list of reserve IDs | \*\*Returns:\*\*\ rebateWallets - array of rebate wallets addresses\
\### \`getReserveIdsPerTokenSrc\` Returns a list of reserve IDs that supports a given source token. \_\_\_ function \_\_getReserveIdsPerTokenSrc\_\_(IERC20 token) external view override returns (bytes32\[] reserveIds) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`token\` | IERC20 | source token | \*\*Returns:\*\*\ reserveIds - array of 32-byte reserve IDs\
\### \`getReserveAddressesPerTokenSrc\` Returns a list of reserve addresses that supports a given source token. \_\_\_ function \_\_getReserveAddressesPerTokenSrc\_\_(IERC20 token, uint256 startIndex, uint256 endIndex) external returns (address\[] reserveAddresses) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`token\` | IERC20 | source token | | \`startIndex\` | uint256 | start index of reserve list to narrow search | | \`endIndex\` | uint256 | end index of reserve list to narrow search | \*\*Returns:\*\*\ reserveAddresses - array of reserve addresses\
\### \`getReserveIdsPerTokenDest\` Returns a list of reserve IDs that supports a given destination token. \_\_\_ function \_\_getReserveIdsPerTokenDest\_\_(IERC20 token) external view override returns (bytes32\[] reserveIds) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`token\` | IERC20 | destination token | \*\*Returns:\*\*\ reserveIds - array of 32-byte reserve IDs\
\### \`getReserveAddressesByReserveId\` Returns a list of addresses from a given reserve ID, where index 0 is the currently used reserve address and indexes > 0 are older versions. \_\_\_ function \_\_getReserveAddressesByReserveId\_\_(bytes32 reserveId) external view override returns (address\[] reserveAddresses) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveId\` | bytes32 | reserve ID of the reserve | \*\*Returns:\*\*\ reserveAddresses - array of reserve addresses\
\### \`getContracts\` Returns a list of KyberDao, KberFeeHandler, KyberMatchingEngine and KyberNetwork contracts, where index 0 is currently used address and indexes > 0 are older versions. \_\_\_ function \_\_getContracts\_\_() external view returns (address\[] kyberDaoAddresses, address\[] kyberFeeHandlerAddresses, address\[] kyberMatchingEngineAddresses, address\[] kyberNetworkAddresses) \*\*Returns:\*\*\ kyberDaoAddresses - array of KyberDao contract addresses kyberFeeHandlerAddresses - array of KyberFeeHandler contract addresses kyberMatchingEngineAddresses - array of KybermatchingEngine contract addresses kyberNetworkAddresses - array of KyberNetwork contract addresses\
\### \`getKyberProxies\` Returns the list of KyberNetworkProxy addresses. \_\_\_ function \_\_getKyberProxies\_\_() external view override returns (IKyberNetworkProxy\[]) \*\*Returns:\*\*\ Array of KyberNetworkProxy addresses\
\### \`isKyberProxyAdded\` Returns a boolean indicating if a KyberNetworkProxy has been added. \_\_\_ function \_\_isKyberProxyAdded\_\_() external view override returns (bool) \*\*Returns:\*\*\ \`true\` if proxy has been added, otherwise \`false\`\
\### \`getReserveDetailsById\` Returns a reserve's information given a reserve ID. \_\_\_ function \_\_getReserveDetailsById\_\_(bytes32 reserveId) external view override returns (address reserveAddress, address rebateWallet, enum IKyberStorage.ReserveType resType, bool isFeeAccountedFlag, bool isEntitledRebateFlag) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveId\` | bytes32 | reserve ID of the reserve | \*\*Returns:\*\*\ reserveAddress - address of the reserve rebateWallet - rebate wallet address of the reserve resType - the reserve type, where 0 - none, 1 - FPR, 2 - APR, 3 - Bridge, 4 - Utility, 5 - Custom, 6 - Orderbook, 7 - Last isFeeAccountedFlag - whether fees are to be charged for a trade for this reserve isEntitledRebateFlag - whether reserve is entitled to receive rebates\
\### \`getReserveDetailsByAddress\` Returns a reserve's information given a address. \_\_\_ function \_\_getReserveDetailsByAddress\_\_(address reserve) external view override returns (bytes32 reserveId, address rebateWallet, enum IKyberStorage.ReserveType resType, bool isFeeAccountedFlag, bool isEntitledRebateFlag) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserve\` | address | address of reserve | \*\*Returns:\*\*\ reserveId - reserve ID of the reserve rebateWallet - rebate wallet address of the reserve resType - the reserve type, where 0 - none, 1 - FPR, 2 - APR, 3 - Bridge, 4 - Utility, 5 - Custom, 6 - Orderbook, 7 - Last isFeeAccountedFlag - whether fees are to be charged for a trade for this reserve isEntitledRebateFlag - whether reserve is entitled to receive rebates\
\### \`getListedTokensByReserveId\` Returns the listed tokens of a given reserve ID. \_\_\_ function \_\_getListedTokensByReserveId\_\_(bytes32 reserveId) external returns (IERC20\[] srcTokens, IERC20\[] destTokens) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveId\` | bytes32 | reserve ID of the reserve | \*\*Returns:\*\*\ srcTokens - array of source token addresses destTokens - array of destination token addresses\
\### \`getFeeAccountedData\` Returns array of booleans if a respective reserve is fee accounted given a list of reserve IDs \_\_\_ function \_\_getFeeAccountedData\_\_(bytes32\[] reserveIds) external view override returns (bool\[] feeAccountedArr) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveIds\` | bytes32\[] | reserve ID of the reserve | \*\*Returns:\*\*\ feeAccountedArr - array of fee accounted booleans respective to reserve IDs input\
\### \`getEntitledRebateData\` Returns array of booleans if a respective reserve is entitled for rebates given a list of reserve IDs \_\_\_ function \_\_getEntitledRebateData\_\_(bytes32\[] reserveIds) external view override returns (bool\[] entitledRebateArr) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveIds\` | bytes32\[] | reserve ID of the reserve | \*\*Returns:\*\*\ entitledRebateArr - array of rebate entitled booleans respective to reserve IDs input\
\### \`getReservesData\` Returns information about fee, address, and rebate information of reserves given their reserve IDs. Also check if these reserve IDs are listed for token. \_\_\_ function \_\_getReservesData\_\_(bytes32\[] reserveIds, IERC20 src, IERC20 dest) external view override returns (bool areAllReservesListed, bool\[] feeAccountedArr, bool\[] entitledRebateArr, IKyberReserve\[] reserveAddresses) | Parameter | Type | Description | | --------- |:-----:|:-----------:| | \`reserveIds\` | bytes32\[] | list of reserve IDs | | \`src\` | IERC20 | source token | | \`dest\` | IERC20 | destination token | \*\*Returns:\*\*\ areAllReservesListed - if token is listed for the given reserve ID feeAccountedArr - array of fee accounted booleans respective to reserve IDs input entitledRebateArr - array of rebate entitled booleans respective to reserve IDs input reserveAddresses - array of reserve addresses
