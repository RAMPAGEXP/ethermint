
<!--
Guiding Principles:

Changelogs are for humans, not machines.
There should be an entry for every single version.
The same types of changes should be grouped.
Versions and sections should be linkable.
The latest version comes first.
The release date of each version is displayed.
Mention whether you follow Semantic Versioning.

Usage:

Change log entries are to be added to the Unreleased section under the
appropriate stanza (see below). Each entry should ideally include a tag and
the Github issue reference in the following format:

* (<tag>) \#<issue-number> message

The issue numbers will later be link-ified during the release process so you do
not have to worry about including a link manually, but you can if you wish.

Types of changes (Stanzas):

"Features" for new features.
"Improvements" for changes in existing functionality.
"Deprecated" for soon-to-be removed features.
"Bug Fixes" for any bug fixes.
"Client Breaking" for breaking CLI commands and REST routes used by end-users.
"API Breaking" for breaking exported APIs used by developers building on SDK.
"State Machine Breaking" for any changes that result in a different AppState given same genesisState and txList.

Ref: https://keepachangelog.com/en/1.0.0/
-->

# Changelog

## [v0.19.2] - 2022-08-29

### Improvements

* (deps) [1301](https://github.com/RAMPAGEXP/ethermint/pull/1301) Bumb sdk to `v0.45.8`, tendermint to `v0.34.21`, iavl to `v0.19.1` & store options

## [v0.19.1] - 2022-08-26

### State Machine Breaking

* (eth) [#1305](https://github.com/RAMPAGEXP/ethermint/pull/1305) Added support for optional params, basic types arrays and `time` type on eip712.

## [v0.19.0] - 2022-08-15

### State Machine Breaking

* (deps) [#1159](https://github.com/RAMPAGEXP/ethermint/pull/1159) Bump Geth version to `v1.10.19`.
* (ante) [#1176](https://github.com/RAMPAGEXP/ethermint/pull/1176) Fix invalid tx hashes; Remove `Size_` field and validate `Hash`/`From` fields in ante handler,
  recompute eth tx hashes in JSON-RPC APIs to fix old blocks.
* (ante) [#1173](https://github.com/RAMPAGEXP/ethermint/pull/1173) Make `NewAnteHandler` return error if input is invalid

### API Breaking

* (rpc) [#1121](https://github.com/RAMPAGEXP/ethermint/pull/1121) Implement Ethereum tx indexer

### Bug Fixes

* (rpc) [#1179](https://github.com/RAMPAGEXP/ethermint/pull/1179) Fix gas used in `debug_traceTransaction` response.

### Improvements

* (test) [#1196](https://github.com/RAMPAGEXP/ethermint/pull/1196) Integration tests setup
* (test) [#1199](https://github.com/RAMPAGEXP/ethermint/pull/1199) Add backend test suite with mock gRPC query client
* (test) [#1189](https://github.com/RAMPAGEXP/ethermint/pull/1189) JSON-RPC unit tests
* (test) [#1212](https://github.com/RAMPAGEXP/ethermint/pull/1212) Prune node integration tests
* (test) [#1207](https://github.com/RAMPAGEXP/ethermint/pull/1207) JSON-RPC types integration tests
* (test) [#1218](https://github.com/RAMPAGEXP/ethermint/pull/1218) Restructure JSON-RPC API
* (rpc) [#1229](https://github.com/RAMPAGEXP/ethermint/pull/1229) Add support for configuring RPC `MaxOpenConnections`
* (cli) [#1230](https://github.com/RAMPAGEXP/ethermint/pull/1230) Remove redundant positional height parameter from feemarket's query cli.
* (test)[#1233](https://github.com/RAMPAGEXP/ethermint/pull/1233) Add filters integration tests

## [v0.18.0] - 2022-08-04

### State Machine Breaking

* (evm) [\#1174](https://github.com/RAMPAGEXP/ethermint/pull/1174) Don't allow eth txs with 0 in mempool.

### Improvements

* (ante) [\#1208](https://github.com/RAMPAGEXP/ethermint/pull/1208) Change default `MaxGasWanted` value.

## [v0.17.2] - 2022-07-26

### Bug Fixes

* (rpc) [\#1190](https://github.com/RAMPAGEXP/ethermint/issues/1190) Fix `UnmarshalJSON` panic of breaking EVM and fee market `Params`.
* (evm) [\#1187](https://github.com/RAMPAGEXP/ethermint/pull/1187) Fix `TxIndex` value (expected 0, actual 1) when trace the first tx of a block via `debug_traceTransaction` API.

## [v0.17.1] - 2022-07-13

### Improvements

* (rpc) [\#1169](https://github.com/RAMPAGEXP/ethermint/pull/1169) Remove unnecessary queries from `getBlockNumber` function

## [v0.17.0] - 2022-06-27

### State Machine Breaking

* (evm) [\#1128](https://github.com/RAMPAGEXP/ethermint/pull/1128) Clear tx logs if tx failed in post processing hooks
* (evm) [\#1124](https://github.com/RAMPAGEXP/ethermint/pull/1124) Reject non-replay-protected tx in `AnteHandler` to prevent replay attack

### API Breaking

* (rpc) [\#1126](https://github.com/RAMPAGEXP/ethermint/pull/1126) Make some JSON-RPC APIS work for pruned nodes.
* (rpc) [\#1143](https://github.com/RAMPAGEXP/ethermint/pull/1143) Restrict unprotected txs on the node JSON-RPC configuration.
* (all) [\#1137](https://github.com/RAMPAGEXP/ethermint/pull/1137) Rename go module to `RAMPAGEXP/ethermint`

### Improvements

* (deps) [\#1147](https://github.com/RAMPAGEXP/ethermint/pull/1147) Bump Go version to `1.18`.
* (feemarket) [\#1135](https://github.com/RAMPAGEXP/ethermint/pull/1135) Set lower bound of base fee to min gas price param
* (evm) [\#1142](https://github.com/RAMPAGEXP/ethermint/pull/1142) Rename `RejectUnprotectedTx` to `AllowUnprotectedTxs` for consistency with go-ethereum.

### Bug Fixes

* (rpc) [\#1138](https://github.com/RAMPAGEXP/ethermint/pull/1138) Fix GasPrice calculation with relation to `MinGasPrice`

## [v0.16.1] - 2022-06-09

### Improvements

* (feemarket) [\#1120](https://github.com/RAMPAGEXP/ethermint/pull/1120) Make `min-gas-multiplier` parameter accept zero value

### Bug Fixes

* (evm) [\#1118](https://github.com/RAMPAGEXP/ethermint/pull/1118) Fix `Type()` `Account` method `EmptyCodeHash` comparison

## [v0.16.0] - 2022-06-06

### State Machine Breaking

* (feemarket) [RAMPAGEXP#1105](https://github.com/RAMPAGEXP/ethermint/pull/1105) Update `BaseFee` calculation based on `GasWanted` instead of `GasUsed`.

### API Breaking

* (feemarket) [RAMPAGEXP#1104](https://github.com/RAMPAGEXP/ethermint/pull/1104) Enforce a minimum gas price for Cosmos and EVM transactions through the `MinGasPrice` parameter.
* (rpc) [RAMPAGEXP#1081](https://github.com/RAMPAGEXP/ethermint/pull/1081) Deduplicate some json-rpc logic codes, cleanup several dead functions.
* (ante) [RAMPAGEXP#1062](https://github.com/RAMPAGEXP/ethermint/pull/1062) Emit event of eth tx hash in ante handler to support query failed transactions.
* (analytics) [RAMPAGEXP#1106](https://github.com/RAMPAGEXP/ethermint/pull/1106) Update telemetry to Ethermint modules.
* (rpc) [RAMPAGEXP#1108](https://github.com/RAMPAGEXP/ethermint/pull/1108) Update GetGasPrice RPC endpoint with global `MinGasPrice`

### Improvements

* (cli) [RAMPAGEXP#1086](https://github.com/RAMPAGEXP/ethermint/pull/1086) Add rollback command.
* (specs) [RAMPAGEXP#1095](https://github.com/RAMPAGEXP/ethermint/pull/1095) Add more evm specs concepts.
* (evm) [RAMPAGEXP#1101](https://github.com/RAMPAGEXP/ethermint/pull/1101) Add tx_type, gas and counter telemetry for ethereum txs.

### Bug Fixes

* (rpc) [RAMPAGEXP#1082](https://github.com/RAMPAGEXP/ethermint/pull/1082) fix gas price returned in getTransaction api.
* (evm) [RAMPAGEXP#1088](https://github.com/RAMPAGEXP/ethermint/pull/1088) Fix ability to append log in tx post processing.
* (rpc) [RAMPAGEXP#1081](https://github.com/RAMPAGEXP/ethermint/pull/1081) fix `debug_getBlockRlp`/`debug_printBlock` don't filter failed transactions.
* (ante) [RAMPAGEXP#1111](https://github.com/RAMPAGEXP/ethermint/pull/1111) Move CanTransfer decorator before GasConsume decorator
* (types) [RAMPAGEXP#1112](https://github.com/cosmos/ethermint/pull/1112) Add `GetBaseAccount` to avoid invalid account error when create vesting account.

## [v0.15.0] - 2022-05-09

### State Machine Breaking

* (ante) [RAMPAGEXP#1060](https://github.com/RAMPAGEXP/ethermint/pull/1060) Check `EnableCreate`/`EnableCall` in `AnteHandler` to short-circuit EVM transactions.
* (evm) [RAMPAGEXP#1087](https://github.com/RAMPAGEXP/ethermint/pull/1087) Minimum GasUsed proportional to GasLimit and `MinGasDenominator` EVM module param.

### API Breaking

* (rpc) [RAMPAGEXP#1070](https://github.com/RAMPAGEXP/ethermint/pull/1070) Refactor `rpc/` package:
  * `Backend` interface is now `BackendI`, which implements `EVMBackend` (for Ethereum namespaces) and `CosmosBackend` (for Cosmos namespaces)
  * Previous `EVMBackend` type is now `Backend`, which is the concrete implementation of `BackendI`
  * Move `rpc/ethereum/types` -> `rpc/types`
  * Move `rpc/ethereum/backend` -> `rpc/backend`
  * Move `rpc/ethereum/namespaces` -> `rpc/namespaces/ethereum`
* (rpc) [RAMPAGEXP#1068](https://github.com/RAMPAGEXP/ethermint/pull/1068) Fix London hard-fork check logic in JSON-RPC APIs.

### Improvements

* (ci, evm) [RAMPAGEXP#1063](https://github.com/RAMPAGEXP/ethermint/pull/1063) Run simulations on CI.

### Bug Fixes

* (rpc) [RAMPAGEXP#1059](https://github.com/RAMPAGEXP/ethermint/pull/1059) Remove unnecessary event filtering logic on the `eth_baseFee` JSON-RPC endpoint.

## [v0.14.0] - 2022-04-19

### API Breaking

* (evm) [RAMPAGEXP#1051](https://github.com/RAMPAGEXP/ethermint/pull/1051) Context block height fix on TraceTx. Removes `tx_index` on `QueryTraceTxRequest` proto type.
* (evm) [RAMPAGEXP#1091](https://github.com/RAMPAGEXP/ethermint/pull/1091) Add query params command on EVM Module

### Improvements

* (deps) [RAMPAGEXP#1046](https://github.com/RAMPAGEXP/ethermint/pull/1046) Bump Cosmos SDK version to [`v0.45.3`](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.45.3)
* (rpc) [RAMPAGEXP#1056](https://github.com/RAMPAGEXP/ethermint/pull/1056) Make json-rpc namespaces extensible

### Bug Fixes

* (rpc) [RAMPAGEXP#1050](https://github.com/RAMPAGEXP/ethermint/pull/1050) `eth_getBlockByNumber` fix on batch transactions
* (app) [RAMPAGEXP#658](https://github.com/RAMPAGEXP/ethermint/issues/658) Support simulations for the EVM.

## [v0.13.0] - 2022-04-05

### API Breaking

* (evm) [RAMPAGEXP#1027](https://github.com/RAMPAGEXP/ethermint/pull/1027) Change the `PostTxProcessing` hook interface to include the full message data.
* (feemarket) [RAMPAGEXP#1026](https://github.com/RAMPAGEXP/ethermint/pull/1026) Fix REST endpoints to use `/ethermint/feemarket/*` instead of `/feemarket/evm/*`.

### Improvements

* (deps) [RAMPAGEXP#1029](https://github.com/RAMPAGEXP/ethermint/pull/1029) Bump Cosmos SDK version to [`v0.45.2`](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.45.2)
* (evm) [RAMPAGEXP#1025](https://github.com/RAMPAGEXP/ethermint/pull/1025) Allow to append logs after a post processing hook.

## [v0.12.2] - 2022-03-30

### Bug Fixes

* (feemarket) [RAMPAGEXP#1021](https://github.com/RAMPAGEXP/ethermint/pull/1021) Fix fee market migration.

## [v0.12.1] - 2022-03-29

### Bug Fixes

* (evm) [RAMPAGEXP#1016](https://github.com/RAMPAGEXP/ethermint/pull/1016) Update validate basic check for storage state.

## [v0.12.0] - 2022-03-24

### Bug Fixes

* (rpc) [RAMPAGEXP#1012](https://github.com/RAMPAGEXP/ethermint/pull/1012) fix the tx hash in filter entries created by `eth_newPendingTransactionFilter`.
* (rpc) [RAMPAGEXP#1006](https://github.com/RAMPAGEXP/ethermint/pull/1006) Use `string` as the parameters type to correct ambiguous results.
* (ante) [RAMPAGEXP#1004](https://github.com/RAMPAGEXP/ethermint/pull/1004) Make `MaxTxGasWanted` configurable.
* (ante) [RAMPAGEXP#991](https://github.com/RAMPAGEXP/ethermint/pull/991) Set an upper bound to gasWanted to prevent DoS attack.
* (rpc) [RAMPAGEXP#990](https://github.com/RAMPAGEXP/ethermint/pull/990) Calculate reward values from all `MsgEthereumTx` from a block in `eth_feeHistory`.

## [v0.11.0] - 2022-03-06

### State Machine Breaking

* (ante) [RAMPAGEXP#964](https://github.com/RAMPAGEXP/ethermint/pull/964) add NewInfiniteGasMeterWithLimit for storing the user provided gas limit. Fixes block's consumed gas calculation in the block creation phase.

### Bug Fixes

* (rpc) [RAMPAGEXP#975](https://github.com/RAMPAGEXP/ethermint/pull/975) Fix unexpected `nil` values for `reward`, returned by `EffectiveGasTipValue(blockBaseFee)` in the `eth_feeHistory` RPC method.

### Improvements

* (rpc) [RAMPAGEXP#979](https://github.com/RAMPAGEXP/ethermint/pull/979) Add configurable timeouts to http server
* (rpc) [RAMPAGEXP#988](https://github.com/RAMPAGEXP/ethermint/pull/988) json-rpc server always use local rpc client

## [v0.10.1] - 2022-03-04

### Bug Fixes

* (rpc) [RAMPAGEXP#970](https://github.com/RAMPAGEXP/ethermint/pull/970) Fix unexpected nil reward values on `eth_feeHistory` response
* (evm) [RAMPAGEXP#529](https://github.com/RAMPAGEXP/ethermint/issues/529) Add support return value on trace tx response.

### Improvements

* (rpc) [RAMPAGEXP#968](https://github.com/RAMPAGEXP/ethermint/pull/968) Add some buffer to returned gas price to provide better default UX for client.

## [v0.10.0] - 2022-02-26

### API Breaking

* (ante) [RAMPAGEXP#866](https://github.com/RAMPAGEXP/ethermint/pull/866) `NewAnteHandler` constructor now receives a `HandlerOptions` field.
* (evm) [RAMPAGEXP#849](https://github.com/RAMPAGEXP/ethermint/pull/849) `PostTxProcessing` hook now takes an Ethereum tx `Receipt` and a `from` `Address` as arguments.
* (ante) [RAMPAGEXP#916](https://github.com/RAMPAGEXP/ethermint/pull/916) Don't check min-gas-price for eth tx if london hardfork enabled and feemarket enabled.

### State Machine Breaking

* (deps) [RAMPAGEXP#912](https://github.com/RAMPAGEXP/ethermint/pull/912) Bump Cosmos SDK version to [`v0.45.1`](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.45.1)
* (evm) [RAMPAGEXP#840](https://github.com/RAMPAGEXP/ethermint/pull/840) Store empty topics as empty array rather than nil.
* (feemarket) [RAMPAGEXP#822](https://github.com/RAMPAGEXP/ethermint/pull/822) Update EIP1559 base fee in `BeginBlock`.
* (evm) [RAMPAGEXP#817](https://github.com/RAMPAGEXP/ethermint/pull/817) Use `effectiveGasPrice` in ante handler, add `effectiveGasPrice` to tx receipt.
* (evm) [RAMPAGEXP#808](https://github.com/RAMPAGEXP/ethermint/issues/808) increase nonce in ante handler for contract creation transaction.
* (evm) [RAMPAGEXP#851](https://github.com/RAMPAGEXP/ethermint/pull/851) fix contract address used in EVM, this issue is caused by [RAMPAGEXP#808](https://github.com/RAMPAGEXP/ethermint/issues/808).
* (evm)  Reject invalid `MsgEthereumTx` wrapping tx
* (evm)  Fix `SelfDestruct` opcode by deleting account code and state.
* (feemarket) [RAMPAGEXP#855](https://github.com/RAMPAGEXP/ethermint/pull/855) Consistent `BaseFee` check logic.
* (evm) [RAMPAGEXP#729](https://github.com/RAMPAGEXP/ethermint/pull/729) Refactor EVM `StateDB` implementation.
* (evm) [RAMPAGEXP#945](https://github.com/RAMPAGEXP/ethermint/pull/945) Bumb Go-ethereum version to [`v1.10.16`](https://github.com/ethereum/go-ethereum/releases/tag/v1.10.16)

### Features

* (ante) [RAMPAGEXP#950](https://github.com/RAMPAGEXP/ethermint/pull/950) Add support for EIP712 signed Cosmos transactions

### Improvements

* (types) [RAMPAGEXP#884](https://github.com/RAMPAGEXP/ethermint/pull/884) Introduce a new `EthAccountI` interface for EVM-compatible account types.
* (types) [RAMPAGEXP#849](https://github.com/RAMPAGEXP/ethermint/pull/849) Add `Type` function to distinguish EOAs from Contract accounts.
* (evm) [RAMPAGEXP#826](https://github.com/RAMPAGEXP/ethermint/issues/826) Improve allocation of bytes of `tx.To` address.
* (evm) [RAMPAGEXP#827](https://github.com/RAMPAGEXP/ethermint/issues/827) Speed up creation of event logs by using the slice insertion idiom with indices.
* (ante) [RAMPAGEXP#819](https://github.com/RAMPAGEXP/ethermint/pull/819) Remove redundant ante handlers
* (app) [RAMPAGEXP#873](https://github.com/RAMPAGEXP/ethermint/pull/873) Validate code hash in GenesisAccount
* (evm) [RAMPAGEXP#901](https://github.com/RAMPAGEXP/ethermint/pull/901) Support multiple `MsgEthereumTx` in single tx.
* (config) [RAMPAGEXP#908](https://github.com/RAMPAGEXP/ethermint/pull/908) Add `api.enable` flag for Cosmos SDK Rest server
* (feemarket) [RAMPAGEXP#919](https://github.com/RAMPAGEXP/ethermint/pull/919) Initialize baseFee in default genesis state.
* (feemarket) [RAMPAGEXP#943](https://github.com/RAMPAGEXP/ethermint/pull/943) Store the base fee as a module param instead of using state storage.

### Bug Fixes

* (rpc) [RAMPAGEXP#955](https://github.com/RAMPAGEXP/ethermint/pull/955) Fix websocket server push duplicated messages to subscriber.
* (rpc) [RAMPAGEXP#953](https://github.com/RAMPAGEXP/ethermint/pull/953) Add `eth_signTypedData` api support.
* (log) [RAMPAGEXP#948](https://github.com/RAMPAGEXP/ethermint/pull/948) Redirect go-ethereum's logs to cosmos-sdk logger.
* (evm) [RAMPAGEXP#884](https://github.com/RAMPAGEXP/ethermint/pull/884) Support multiple account types on the EVM `StateDB`.
* (rpc) [RAMPAGEXP#831](https://github.com/RAMPAGEXP/ethermint/pull/831) Fix BaseFee value when height is specified.
* (evm) [RAMPAGEXP#838](https://github.com/RAMPAGEXP/ethermint/pull/838) Fix splitting of trace.Memory into 32 chunks.
* (rpc) [RAMPAGEXP#860](https://github.com/RAMPAGEXP/ethermint/pull/860) Fix `eth_getLogs` when specify blockHash without address/topics, and limit the response size.
* (rpc) [RAMPAGEXP#865](https://github.com/RAMPAGEXP/ethermint/pull/865) Fix RPC Filter parameters being ignored
* (evm) [RAMPAGEXP#871](https://github.com/RAMPAGEXP/ethermint/pull/871) Set correct nonce in `EthCall` and `EstimateGas` grpc query.
* (rpc) [RAMPAGEXP#878](https://github.com/RAMPAGEXP/ethermint/pull/878) Workaround to make GetBlock RPC api report correct block gas used.
* (rpc) [RAMPAGEXP#900](https://github.com/RAMPAGEXP/ethermint/pull/900) `newPendingTransactions` filter return ethereum tx hash.
* (rpc) [RAMPAGEXP#933](https://github.com/RAMPAGEXP/ethermint/pull/933) Fix `newPendingTransactions` subscription deadlock when a Websocket client exits without unsubscribing and the node errors.
* (evm) [RAMPAGEXP#932](https://github.com/RAMPAGEXP/ethermint/pull/932) Fix base fee check logic in state transition.

## [v0.9.0] - 2021-12-01

### State Machine Breaking

* (evm) [RAMPAGEXP#802](https://github.com/RAMPAGEXP/ethermint/pull/802) Clear access list for each transaction

### Improvements

* (app) [RAMPAGEXP#794](https://github.com/RAMPAGEXP/ethermint/pull/794) Setup in-place store migrators.
* (ci) [RAMPAGEXP#784](https://github.com/RAMPAGEXP/ethermint/pull/784) Enable automatic backport of PRs.
* (rpc) [RAMPAGEXP#786](https://github.com/RAMPAGEXP/ethermint/pull/786) Improve error message of `SendTransaction`/`SendRawTransaction` JSON-RPC APIs.
* (rpc) [RAMPAGEXP#810](https://github.com/RAMPAGEXP/ethermint/pull/810) Optimize tx index lookup in web3 rpc

### Bug Fixes

* (license) [RAMPAGEXP#800](https://github.com/RAMPAGEXP/ethermint/pull/800) Re-license project to [LGPLv3](https://choosealicense.com/licenses/lgpl-3.0/#) to comply with go-ethereum.
* (evm) [RAMPAGEXP#794](https://github.com/RAMPAGEXP/ethermint/pull/794) Register EVM gRPC `Msg` server.
* (rpc) [RAMPAGEXP#781](https://github.com/RAMPAGEXP/ethermint/pull/781) Fix get block invalid transactions filter.
* (rpc) [RAMPAGEXP#782](https://github.com/RAMPAGEXP/ethermint/pull/782) Fix wrong block gas limit returned by JSON-RPC.
* (evm) [RAMPAGEXP#798](https://github.com/RAMPAGEXP/ethermint/pull/798) Fix the semantic of `ForEachStorage` callback's return value

## [v0.8.1] - 2021-11-23

### Bug Fixes

* (feemarket) [RAMPAGEXP#770](https://github.com/RAMPAGEXP/ethermint/pull/770) Enable fee market (EIP1559) by default.
* (rpc) [RAMPAGEXP#769](https://github.com/RAMPAGEXP/ethermint/pull/769) Fix default Ethereum signer for JSON-RPC.

## [v0.8.0] - 2021-11-17

### State Machine Breaking

* (evm, ante) [RAMPAGEXP#620](https://github.com/RAMPAGEXP/ethermint/pull/620) Add fee market field to EVM `Keeper` and `AnteHandler`.
* (all) [RAMPAGEXP#231](https://github.com/RAMPAGEXP/ethermint/pull/231) Bump go-ethereum version to [`v1.10.9`](https://github.com/ethereum/go-ethereum/releases/tag/v1.10.9)
* (ante) [RAMPAGEXP#703](https://github.com/RAMPAGEXP/ethermint/pull/703) Fix some fields in transaction are not authenticated by signature.
* (evm) [RAMPAGEXP#751](https://github.com/RAMPAGEXP/ethermint/pull/751) don't revert gas refund logic when transaction reverted

### Features

* (rpc, evm) [RAMPAGEXP#673](https://github.com/RAMPAGEXP/ethermint/pull/673) Use tendermint events to store fee market basefee.
* (rpc) [RAMPAGEXP#624](https://github.com/RAMPAGEXP/ethermint/pull/624) Implement new JSON-RPC endpoints from latest geth version
* (evm) [RAMPAGEXP#662](https://github.com/RAMPAGEXP/ethermint/pull/662) Disable basefee for non london blocks
* (cmd) [RAMPAGEXP#712](https://github.com/RAMPAGEXP/ethermint/pull/712) add tx cli to build evm transaction
* (rpc) [RAMPAGEXP#733](https://github.com/RAMPAGEXP/ethermint/pull/733) add JSON_RPC endpoint `personal_unpair`
* (rpc) [RAMPAGEXP#734](https://github.com/RAMPAGEXP/ethermint/pull/734) add JSON_RPC endpoint `eth_feeHistory`
* (rpc) [RAMPAGEXP#740](https://github.com/RAMPAGEXP/ethermint/pull/740) add JSON_RPC endpoint `personal_initializeWallet`
* (rpc) [RAMPAGEXP#743](https://github.com/RAMPAGEXP/ethermint/pull/743) add JSON_RPC endpoint `debug_traceBlockByHash`
* (rpc) [RAMPAGEXP#748](https://github.com/RAMPAGEXP/ethermint/pull/748) add JSON_RPC endpoint `personal_listWallets`
* (rpc) [RAMPAGEXP#754](https://github.com/RAMPAGEXP/ethermint/pull/754) add JSON_RPC endpoint `debug_intermediateRoots`

### Bug Fixes

* (evm) [RAMPAGEXP#746](https://github.com/RAMPAGEXP/ethermint/pull/746) Set EVM debugging based on tracer configuration.
* (app,cli) [RAMPAGEXP#725](https://github.com/RAMPAGEXP/ethermint/pull/725) Fix cli-config for  `keys` command.
* (rpc) [RAMPAGEXP#727](https://github.com/RAMPAGEXP/ethermint/pull/727) Decode raw transaction using RLP.
* (rpc) [RAMPAGEXP#661](https://github.com/RAMPAGEXP/ethermint/pull/661) Fix OOM bug when creating too many filters using JSON-RPC.
* (evm) [RAMPAGEXP#660](https://github.com/RAMPAGEXP/ethermint/pull/660) Fix `nil` pointer panic in `ApplyNativeMessage`.
* (evm, test) [RAMPAGEXP#649](https://github.com/RAMPAGEXP/ethermint/pull/649) Test DynamicFeeTx.
* (evm) [RAMPAGEXP#702](https://github.com/RAMPAGEXP/ethermint/pull/702) Fix panic in web3 RPC handlers
* (rpc) [RAMPAGEXP#720](https://github.com/RAMPAGEXP/ethermint/pull/720) Fix `debug_traceTransaction` failure
* (rpc) [RAMPAGEXP#741](https://github.com/RAMPAGEXP/ethermint/pull/741) Fix `eth_getBlockByNumberAndHash` return with non eth txs
* (rpc) [RAMPAGEXP#743](https://github.com/RAMPAGEXP/ethermint/pull/743) Fix debug JSON RPC handler crash on non-existing block

### Improvements

* (tests) [RAMPAGEXP#704](https://github.com/RAMPAGEXP/ethermint/pull/704) Introduce E2E testing framework for clients
* (deps) [RAMPAGEXP#737](https://github.com/RAMPAGEXP/ethermint/pull/737) Bump ibc-go to [`v2.0.0`](https://github.com/cosmos/ibc-go/releases/tag/v2.0.0)
* (rpc) [RAMPAGEXP#671](https://github.com/RAMPAGEXP/ethermint/pull/671) Don't pass base fee externally for `EthCall`/`EthEstimateGas` apis.
* (evm) [RAMPAGEXP#674](https://github.com/RAMPAGEXP/ethermint/pull/674) Refactor `ApplyMessage`, remove
  `ApplyNativeMessage`.
* (rpc) [RAMPAGEXP#714](https://github.com/RAMPAGEXP/ethermint/pull/714) remove `MsgEthereumTx` support in `TxConfig`

## [v0.7.2] - 2021-10-24

### Improvements

* (deps) [RAMPAGEXP#692](https://github.com/RAMPAGEXP/ethermint/pull/692) Bump Cosmos SDK version to [`v0.44.3`](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.44.3).
* (rpc) [RAMPAGEXP#679](https://github.com/RAMPAGEXP/ethermint/pull/679) Fix file close handle.
* (deps) [RAMPAGEXP#668](https://github.com/RAMPAGEXP/ethermint/pull/668) Bump Tendermint version to [`v0.34.14`](https://github.com/tendermint/tendermint/releases/tag/v0.34.14).

### Bug Fixes

* (rpc) [RAMPAGEXP#667](https://github.com/RAMPAGEXP/ethermint/issues/667) Fix `ExpandHome` restrictions bypass

## [v0.7.1] - 2021-10-08

### Bug Fixes

* (evm) [RAMPAGEXP#650](https://github.com/RAMPAGEXP/ethermint/pull/650) Fix panic when flattening the cache context in case transaction is reverted.
* (rpc, test) [RAMPAGEXP#608](https://github.com/RAMPAGEXP/ethermint/pull/608) Fix rpc test.

## [v0.7.0] - 2021-10-07

### API Breaking

* (rpc) [RAMPAGEXP#400](https://github.com/RAMPAGEXP/ethermint/issues/400) Restructure JSON-RPC directory and rename server config

### Improvements

* (deps) [RAMPAGEXP#621](https://github.com/RAMPAGEXP/ethermint/pull/621) Bump IBC-go to [`v1.2.1`](https://github.com/cosmos/ibc-go/releases/tag/v1.2.1)
* (evm) [RAMPAGEXP#613](https://github.com/RAMPAGEXP/ethermint/pull/613) Refactor `traceTx`
* (deps) [RAMPAGEXP#610](https://github.com/RAMPAGEXP/ethermint/pull/610) Bump Cosmos SDK to [v0.44.1](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.44.1).

### Bug Fixes

* (rpc) [RAMPAGEXP#642](https://github.com/RAMPAGEXP/ethermint/issues/642) Fix `eth_getLogs` when string is specified in filter's from or to fields
* (evm) [RAMPAGEXP#616](https://github.com/RAMPAGEXP/ethermint/issues/616) Fix halt on deeply nested stack of cache context. Stack is now flattened before iterating over the tx logs.
* (rpc, evm) [RAMPAGEXP#614](https://github.com/RAMPAGEXP/ethermint/issues/614) Use JSON for (un)marshaling tx `Log`s from events.
* (rpc) [RAMPAGEXP#611](https://github.com/RAMPAGEXP/ethermint/pull/611) Fix panic on JSON-RPC when querying for an invalid block height.
* (cmd) [RAMPAGEXP#483](https://github.com/RAMPAGEXP/ethermint/pull/483) Use config values on genesis accounts.

## [v0.6.0] - 2021-09-29

### State Machine Breaking

* (app) [RAMPAGEXP#476](https://github.com/RAMPAGEXP/ethermint/pull/476) Update Bech32 HRP to `ethm`.
* (evm) [RAMPAGEXP#556](https://github.com/RAMPAGEXP/ethermint/pull/556) Remove tx logs and block bloom from chain state
* (evm) [RAMPAGEXP#590](https://github.com/RAMPAGEXP/ethermint/pull/590) Contract storage key is not hashed anymore

### API Breaking

* (evm) [RAMPAGEXP#469](https://github.com/RAMPAGEXP/ethermint/pull/469) Deprecate `YoloV3Block` and `EWASMBlock` from `ChainConfig`

### Features

* (evm) [RAMPAGEXP#469](https://github.com/RAMPAGEXP/ethermint/pull/469) Support [EIP-1559](https://eips.ethereum.org/EIPS/eip-1559)
* (evm) [RAMPAGEXP#417](https://github.com/RAMPAGEXP/ethermint/pull/417) Add `EvmHooks` for tx post-processing
* (rpc) [RAMPAGEXP#506](https://github.com/RAMPAGEXP/ethermint/pull/506) Support for `debug_traceTransaction` RPC endpoint
* (rpc) [RAMPAGEXP#555](https://github.com/RAMPAGEXP/ethermint/pull/555) Support for `debug_traceBlockByNumber` RPC endpoint

### Bug Fixes

* (rpc, server) [RAMPAGEXP#600](https://github.com/RAMPAGEXP/ethermint/pull/600) Add TLS configuration for websocket API
* (rpc) [RAMPAGEXP#598](https://github.com/RAMPAGEXP/ethermint/pull/598) Check truncation when creating a `BlockNumber` from `big.Int`
* (evm) [RAMPAGEXP#597](https://github.com/RAMPAGEXP/ethermint/pull/597) Check for `uint64` -> `int64` block height overflow on `GetHashFn`
* (evm) [RAMPAGEXP#579](https://github.com/RAMPAGEXP/ethermint/pull/579) Update `DeriveChainID` function to handle `v` signature values `< 35`.
* (encoding) [RAMPAGEXP#478](https://github.com/RAMPAGEXP/ethermint/pull/478) Register `Evidence` to amino codec.
* (rpc) [RAMPAGEXP#478](https://github.com/RAMPAGEXP/ethermint/pull/481) Getting the node configuration when calling the `miner` rpc methods.
* (cli) [RAMPAGEXP#561](https://github.com/RAMPAGEXP/ethermint/pull/561) `Export` and `Start` commands now use the same home directory.

### Improvements

* (evm) [RAMPAGEXP#461](https://github.com/RAMPAGEXP/ethermint/pull/461) Increase performance of `StateDB` transaction log storage (r/w).
* (evm) [RAMPAGEXP#566](https://github.com/RAMPAGEXP/ethermint/pull/566) Introduce `stateErr` store in `StateDB` to avoid meaningless operations if any error happened before
* (rpc, evm) [RAMPAGEXP#587](https://github.com/RAMPAGEXP/ethermint/pull/587) Apply bloom filter when query ethlogs with range of blocks
* (evm) [RAMPAGEXP#586](https://github.com/RAMPAGEXP/ethermint/pull/586) Benchmark evm keeper

## [v0.5.0] - 2021-08-20

### State Machine Breaking

* (app, rpc) [RAMPAGEXP#447](https://github.com/RAMPAGEXP/ethermint/pull/447) Chain ID format has been changed from `<identifier>-<epoch>` to `<identifier>_<EIP155_number>-<epoch>`
in order to clearly distinguish permanent vs impermanent components.
* (app, evm) [RAMPAGEXP#434](https://github.com/RAMPAGEXP/ethermint/pull/434) EVM `Keeper` struct and `NewEVM` function now have a new `trace` field to define
the Tracer type used to collect execution traces from the EVM transaction execution.
* (evm) [RAMPAGEXP#175](https://github.com/RAMPAGEXP/ethermint/issues/175) The msg `TxData` field is now represented as a `*proto.Any`.
* (evm) [RAMPAGEXP#84](https://github.com/RAMPAGEXP/ethermint/pull/84) Remove `journal`, `CommitStateDB` and `stateObjects`.
* (rpc, evm) [RAMPAGEXP#81](https://github.com/RAMPAGEXP/ethermint/pull/81) Remove tx `Receipt` from store and replace it with fields obtained from the Tendermint RPC client.
* (evm) [RAMPAGEXP#72](https://github.com/RAMPAGEXP/ethermint/issues/72) Update `AccessList` to use `TransientStore` instead of map.
* (evm) [RAMPAGEXP#68](https://github.com/RAMPAGEXP/ethermint/issues/68) Replace block hash storage map to use staking `HistoricalInfo`.
* (evm) [RAMPAGEXP#276](https://github.com/RAMPAGEXP/ethermint/pull/276) Vm errors don't result in cosmos tx failure, just
  different tx state and events.
* (evm) [RAMPAGEXP#342](https://github.com/RAMPAGEXP/ethermint/issues/342) Don't clear balance when resetting the account.
* (evm) [RAMPAGEXP#334](https://github.com/RAMPAGEXP/ethermint/pull/334) Log index changed to the index in block rather than
  tx.
* (evm) [RAMPAGEXP#399](https://github.com/RAMPAGEXP/ethermint/pull/399) Exception in sub-message call reverts the call if it's not propagated.

### API Breaking

* (proto) [RAMPAGEXP#448](https://github.com/RAMPAGEXP/ethermint/pull/448) Bump version for all Ethermint messages to `v1`
* (server) [RAMPAGEXP#434](https://github.com/RAMPAGEXP/ethermint/pull/434) `evm-rpc` flags and app config have been renamed to `json-rpc`.
* (proto, evm) [RAMPAGEXP#207](https://github.com/RAMPAGEXP/ethermint/issues/207) Replace `big.Int` in favor of `sdk.Int` for `TxData` fields
* (proto, evm) [RAMPAGEXP#81](https://github.com/RAMPAGEXP/ethermint/pull/81) gRPC Query and Tx service changes:
  * The `TxReceipt`, `TxReceiptsByBlockHeight` endpoints have been removed from the Query service.
  * The `ContractAddress`, `Bloom` have been removed from the `MsgEthereumTxResponse` and the
    response now contains the ethereum-formatted `Hash` in hex format.
* (eth) [RAMPAGEXP#845](https://github.com/cosmos/ethermint/pull/845) The `eth` namespace must be included in the list of API's as default to run the rpc server without error.
* (evm) [RAMPAGEXP#202](https://github.com/RAMPAGEXP/ethermint/pull/202) Web3 api `SendTransaction`/`SendRawTransaction` returns ethereum compatible transaction hash, and query api `GetTransaction*` also accept that.
* (rpc) [RAMPAGEXP#258](https://github.com/RAMPAGEXP/ethermint/pull/258) Return empty `BloomFilter` instead of throwing an error when it cannot be found (`nil` or empty).
* (rpc) [RAMPAGEXP#277](https://github.com/RAMPAGEXP/ethermint/pull/321) Fix `BloomFilter` response.

### Improvements

* (client) [RAMPAGEXP#450](https://github.com/RAMPAGEXP/ethermint/issues/450) Add EIP55 hex address support on `debug addr` command.
* (server) [RAMPAGEXP#343](https://github.com/RAMPAGEXP/ethermint/pull/343) Define a wrap tendermint logger `Handler` go-ethereum's `root` logger.
* (rpc) [RAMPAGEXP#457](https://github.com/RAMPAGEXP/ethermint/pull/457) Configure RPC gas cap through app config.
* (evm) [RAMPAGEXP#434](https://github.com/RAMPAGEXP/ethermint/pull/434) Support different `Tracer` types for the EVM.
* (deps) [RAMPAGEXP#427](https://github.com/RAMPAGEXP/ethermint/pull/427) Bump ibc-go to [`v1.0.0`](https://github.com/cosmos/ibc-go/releases/tag/v1.0.0)
* (gRPC) [RAMPAGEXP#239](https://github.com/RAMPAGEXP/ethermint/pull/239) Query `ChainConfig` via gRPC.
* (rpc) [RAMPAGEXP#181](https://github.com/RAMPAGEXP/ethermint/pull/181) Use evm denomination for params on tx fee.
* (deps) [RAMPAGEXP#423](https://github.com/RAMPAGEXP/ethermint/pull/423) Bump Cosmos SDK and Tendermint versions to [v0.43.0](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.43.0) and [v0.34.11](https://github.com/tendermint/tendermint/releases/tag/v0.34.11), respectively.
* (evm) [RAMPAGEXP#66](https://github.com/RAMPAGEXP/ethermint/issues/66) Support legacy transaction types for signing.
* (evm) [RAMPAGEXP#24](https://github.com/RAMPAGEXP/ethermint/pull/24) Implement metrics for `MsgEthereumTx`, state transitions, `BeginBlock` and `EndBlock`.
* (rpc)  [RAMPAGEXP#124](https://github.com/RAMPAGEXP/ethermint/issues/124) Implement `txpool_content`, `txpool_inspect` and `txpool_status` RPC methods
* (rpc) [RAMPAGEXP#112](https://github.com/RAMPAGEXP/ethermint/pull/153) Fix `eth_coinbase` to return the ethereum address of the validator
* (rpc) [RAMPAGEXP#176](https://github.com/RAMPAGEXP/ethermint/issues/176) Support fetching pending nonce
* (rpc) [RAMPAGEXP#272](https://github.com/RAMPAGEXP/ethermint/pull/272) do binary search to estimate gas accurately
* (rpc) [RAMPAGEXP#313](https://github.com/RAMPAGEXP/ethermint/pull/313) Implement internal debug namespace (Not including logger functions nor traces).
* (rpc) [RAMPAGEXP#349](https://github.com/RAMPAGEXP/ethermint/pull/349) Implement configurable JSON-RPC APIs to manage enabled namespaces.
* (rpc) [RAMPAGEXP#377](https://github.com/RAMPAGEXP/ethermint/pull/377) Implement `miner_` namespace. `miner_setEtherbase` and `miner_setGasPrice` are working as intended. All the other calls are not applicable and return `unsupported`.
* (eth) [RAMPAGEXP#460](https://github.com/RAMPAGEXP/ethermint/issues/460) Add support for EIP-1898.

### Bug Fixes

* (keys) [RAMPAGEXP#346](https://github.com/RAMPAGEXP/ethermint/pull/346) Fix `keys add` command with `--ledger` flag for the `secp256k1` signing algorithm.
* (evm) [RAMPAGEXP#291](https://github.com/RAMPAGEXP/ethermint/pull/291) Use block proposer address (validator operator) for `COINBASE` opcode.
* (rpc) [RAMPAGEXP#81](https://github.com/RAMPAGEXP/ethermint/pull/81) Fix transaction hashing and decoding on `eth_sendTransaction`.
* (rpc) [RAMPAGEXP#45](https://github.com/RAMPAGEXP/ethermint/pull/45) Use `EmptyUncleHash` and `EmptyRootHash` for empty ethereum `Header` fields.

## [v0.4.1] - 2021-03-01

### API Breaking

* (faucet) [RAMPAGEXP#678](https://github.com/cosmos/ethermint/pull/678) Faucet module has been removed in favor of client libraries such as [`@cosmjs/faucet`](https://github.com/cosmos/cosmjs/tree/master/packages/faucet).
* (evm) [RAMPAGEXP#670](https://github.com/cosmos/ethermint/pull/670) Migrate types to the ones defined by the protobuf messages, which are required for the stargate release.

### Bug Fixes

* (evm) [RAMPAGEXP#799](https://github.com/cosmos/ethermint/issues/799) Fix wrong precision in calculation of gas fee.
* (evm) [RAMPAGEXP#760](https://github.com/cosmos/ethermint/issues/760) Fix Failed to call function EstimateGas.
* (evm) [RAMPAGEXP#767](https://github.com/cosmos/ethermint/issues/767) Fix error of timeout when using Truffle to deploy contract.
* (evm) [RAMPAGEXP#751](https://github.com/cosmos/ethermint/issues/751) Fix misused method to calculate block hash in evm related function.
* (evm) [RAMPAGEXP#721](https://github.com/cosmos/ethermint/issues/721) Fix mismatch block hash in rpc response when use eht.getBlock.
* (evm) [RAMPAGEXP#730](https://github.com/cosmos/ethermint/issues/730) Fix 'EIP2028' not open when Istanbul version has been enabled.
* (evm) [RAMPAGEXP#749](https://github.com/cosmos/ethermint/issues/749) Fix panic in `AnteHandler` when gas price larger than 100000
* (evm) [RAMPAGEXP#747](https://github.com/cosmos/ethermint/issues/747) Fix format errors in String() of QueryETHLogs
* (evm) [RAMPAGEXP#742](https://github.com/cosmos/ethermint/issues/742) Add parameter check for evm query func.
* (evm) [RAMPAGEXP#687](https://github.com/cosmos/ethermint/issues/687) Fix nonce check to explicitly check for the correct nonce, rather than a simple 'greater than' comparison.
* (api) [RAMPAGEXP#687](https://github.com/cosmos/ethermint/issues/687) Returns error for a transaction with an incorrect nonce.
* (evm) [RAMPAGEXP#674](https://github.com/cosmos/ethermint/issues/674) Reset all cache after account data has been committed in `EndBlock` to make sure every node state consistent.
* (evm) [RAMPAGEXP#672](https://github.com/cosmos/ethermint/issues/672) Fix panic of `wrong Block.Header.AppHash` when restart a node with snapshot.
* (evm) [RAMPAGEXP#775](https://github.com/cosmos/ethermint/issues/775) MisUse of headHash as blockHash when create EVM context.

### Features

* (api) [RAMPAGEXP#821](https://github.com/cosmos/ethermint/pull/821) Individually enable the api modules. Will be implemented in the latest version of ethermint with the upcoming stargate upgrade.

### Features

* (api) [RAMPAGEXP#825](https://github.com/cosmos/ethermint/pull/825) Individually enable the api modules. Will be implemented in the latest version of ethermint with the upcoming stargate upgrade.

## [v0.4.0] - 2020-12-15

### API Breaking

* (evm) [RAMPAGEXP#661](https://github.com/cosmos/ethermint/pull/661) `Balance` field has been removed from the evm module's `GenesisState`.

### Features

* (rpc) [RAMPAGEXP#571](https://github.com/cosmos/ethermint/pull/571) Add pending queries to JSON-RPC calls. This allows for the querying of pending transactions and other relevant information that pertains to the pending state:
  * `eth_getBalance`
  * `eth_getTransactionCount`
  * `eth_getBlockTransactionCountByNumber`
  * `eth_getBlockByNumber`
  * `eth_getTransactionByHash`
  * `eth_getTransactionByBlockNumberAndIndex`
  * `eth_sendTransaction` - the nonce will automatically update to its pending nonce (when none is explicitly provided)

### Improvements

* (evm) [RAMPAGEXP#661](https://github.com/cosmos/ethermint/pull/661) Add invariant check for account balance and account nonce.
* (deps) [RAMPAGEXP#654](https://github.com/cosmos/ethermint/pull/654) Bump go-ethereum version to [v1.9.25](https://github.com/ethereum/go-ethereum/releases/tag/v1.9.25)
* (evm) [RAMPAGEXP#627](https://github.com/cosmos/ethermint/issues/627) Add extra EIPs parameter to apply custom EVM jump tables.

### Bug Fixes

* (evm) [RAMPAGEXP#661](https://github.com/cosmos/ethermint/pull/661) Set nonce to the EVM account on genesis initialization.
* (rpc) [RAMPAGEXP#648](https://github.com/cosmos/ethermint/issues/648) Fix block cumulative gas used value.
* (evm) [RAMPAGEXP#621](https://github.com/cosmos/ethermint/issues/621) EVM `GenesisAccount` fields now share the same format as the auth module `Account`.
* (evm) [RAMPAGEXP#618](https://github.com/cosmos/ethermint/issues/618) Add missing EVM `Context` `GetHash` field that retrieves a the header hash from a given block height.
* (app) [RAMPAGEXP#617](https://github.com/cosmos/ethermint/issues/617) Fix genesis export functionality.
* (rpc) [RAMPAGEXP#574](https://github.com/cosmos/ethermint/issues/574) Fix outdated version from `eth_protocolVersion`.

## [v0.3.1] - 2020-11-24

### Improvements

* (deps) [RAMPAGEXP#615](https://github.com/cosmos/ethermint/pull/615) Bump Cosmos SDK version to [v0.39.2](https://github.com/cosmos/cosmos-sdk/tag/v0.39.2)
* (deps) [RAMPAGEXP#610](https://github.com/cosmos/ethermint/pull/610) Update Go dependency to 1.15+.
* (evm) [RAMPAGEXP#603](https://github.com/cosmos/ethermint/pull/603) Add state transition params that enable or disable the EVM `Call` and `Create` operations.
* (deps) [RAMPAGEXP#602](https://github.com/cosmos/ethermint/pull/602) Bump tendermint version to [v0.33.9](https://github.com/tendermint/tendermint/releases/tag/v0.33.9)

### Bug Fixes

* (rpc) [RAMPAGEXP#613](https://github.com/cosmos/ethermint/issues/613) Fix potential deadlock caused if the keyring `List` returned an error.

## [v0.3.0] - 2020-11-16

### API Breaking

* (crypto) [RAMPAGEXP#559](https://github.com/cosmos/ethermint/pull/559) Refactored crypto package in preparation for the SDK's Stargate release:
  * `crypto.PubKeySecp256k1` and `crypto.PrivKeySecp256k1` are now `ethsecp256k1.PubKey` and `ethsecp256k1.PrivKey`, respectively
  * Moved SDK `SigningAlgo` implementation for Ethermint's Secp256k1 key to `crypto/hd` package.
* (rpc) [RAMPAGEXP#588](https://github.com/cosmos/ethermint/pull/588) The `rpc` package has been refactored to account for the separation of each
corresponding Ethereum API namespace:
  * `rpc/namespaces/eth`: `eth` namespace. Exposes the `PublicEthereumAPI` and the `PublicFilterAPI`.
  * `rpc/namespaces/personal`: `personal` namespace. Exposes the `PrivateAccountAPI`.
  * `rpc/namespaces/net`: `net` namespace. Exposes the `PublicNetAPI`.
  * `rpc/namespaces/web3`: `web3` namespace. Exposes the `PublicWeb3API`.
* (evm) [RAMPAGEXP#588](https://github.com/cosmos/ethermint/pull/588) The EVM transaction CLI has been removed in favor of the JSON-RPC.

### Improvements

* (deps) [RAMPAGEXP#594](https://github.com/cosmos/ethermint/pull/594) Bump go-ethereum version to [v1.9.24](https://github.com/ethereum/go-ethereum/releases/tag/v1.9.24)

### Bug Fixes

* (ante) [RAMPAGEXP#597](https://github.com/cosmos/ethermint/pull/597) Fix incorrect fee check on `AnteHandler`.
* (evm) [RAMPAGEXP#583](https://github.com/cosmos/ethermint/pull/583) Fixes incorrect resetting of tx count and block bloom during `BeginBlock`, as well as gas consumption.
* (crypto) [RAMPAGEXP#577](https://github.com/cosmos/ethermint/pull/577) Fix `BIP44HDPath` that did not prepend `m/` to the path. This now uses the `DefaultBaseDerivationPath` variable from go-ethereum to ensure addresses are consistent.

## [v0.2.1] - 2020-09-30

### Features

* (rpc) [RAMPAGEXP#552](https://github.com/cosmos/ethermint/pull/552) Implement Eth Personal namespace `personal_importRawKey`.

### Bug fixes

* (keys) [RAMPAGEXP#554](https://github.com/cosmos/ethermint/pull/554) Fix private key derivation.
* (app/ante) [RAMPAGEXP#550](https://github.com/cosmos/ethermint/pull/550) Update ante handler nonce verification to accept any nonce greater than or equal to the expected nonce to allow to successive transactions.

## [v0.2.0] - 2020-09-24

### State Machine Breaking

* (app) [RAMPAGEXP#540](https://github.com/cosmos/ethermint/issues/540) Chain identifier's format has been changed to match the Cosmos `chainID` [standard](https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-5.md), which is required for IBC. The epoch number of the ID is used as the EVM `chainID`.

### API Breaking

* (types) [RAMPAGEXP#503](https://github.com/cosmos/ethermint/pull/503) The `types.DenomDefault` constant for `"aphoton"` has been renamed to `types.AttoPhoton`.

### Improvements

* (types) [RAMPAGEXP#504](https://github.com/cosmos/ethermint/pull/504) Unmarshal a JSON `EthAccount` using an Ethereum hex address in addition to Bech32.
* (types) [RAMPAGEXP#503](https://github.com/cosmos/ethermint/pull/503) Add `--coin-denom` flag to testnet command that sets the given coin denomination to SDK and Ethermint parameters.
* (types) [RAMPAGEXP#502](https://github.com/cosmos/ethermint/pull/502) `EthAccount` now also exposes the Ethereum hex address in `string` format to clients.
* (types) [RAMPAGEXP#494](https://github.com/cosmos/ethermint/pull/494) Update `EthAccount` public key JSON type to `string`.
* (app) [RAMPAGEXP#471](https://github.com/cosmos/ethermint/pull/471) Add `x/upgrade` module for managing software updates.
* (evm) [RAMPAGEXP#458](https://github.com/cosmos/ethermint/pull/458) Define parameter for token denomination used for the EVM module.
* (evm) [RAMPAGEXP#443](https://github.com/cosmos/ethermint/issues/443) Support custom Ethereum `ChainConfig` params.
* (types) [RAMPAGEXP#434](https://github.com/cosmos/ethermint/issues/434) Update default denomination to Atto Photon (`aphoton`).
* (types) [RAMPAGEXP#515](https://github.com/cosmos/ethermint/pull/515) Update minimum gas price to be 1.

### Bug Fixes

* (ante) [RAMPAGEXP#525](https://github.com/cosmos/ethermint/pull/525) Add message validation decorator to `AnteHandler` for `MsgEthereumTx`.
* (types) [RAMPAGEXP#507](https://github.com/cosmos/ethermint/pull/507) Fix hardcoded `aphoton` on `EthAccount` balance getter and setter.
* (types) [RAMPAGEXP#501](https://github.com/cosmos/ethermint/pull/501) Fix bech32 encoding error by using the compressed ethereum secp256k1 public key.
* (evm) [RAMPAGEXP#496](https://github.com/cosmos/ethermint/pull/496) Fix bugs on `journal.revert` and `CommitStateDB.Copy`.
* (types) [RAMPAGEXP#480](https://github.com/cosmos/ethermint/pull/480) Update [BIP44](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki) coin type to `60` to satisfy [EIP84](https://github.com/ethereum/EIPs/issues/84).
* (types) [RAMPAGEXP#513](https://github.com/cosmos/ethermint/pull/513) Fix simulated transaction bug that was causing a consensus error by unintentionally affecting the state.

## [v0.1.0] - 2020-08-23

### Improvements

* (sdk) [RAMPAGEXP#386](https://github.com/cosmos/ethermint/pull/386) Bump Cosmos SDK version to [v0.39.1](https://github.com/cosmos/cosmos-sdk/releases/tag/v0.39.1)
* (evm) [RAMPAGEXP#181](https://github.com/cosmos/ethermint/issues/181) Updated EVM module to the recommended module structure.
* (app) [RAMPAGEXP#188](https://github.com/cosmos/ethermint/issues/186)  Misc cleanup:
  * (evm) Rename `EthereumTxMsg` --> `MsgEthereumTx` and `EmintMsg` --> `MsgEthermint` for consistency with SDK standards
  * Updated integration and unit tests to use `EthermintApp` as testing suite
  * Use expected `Keeper` interface for `AccountKeeper`
  * Replaced `count` type in keeper with `int`
  * Add SDK events for transactions
* [RAMPAGEXP#236](https://github.com/cosmos/ethermint/pull/236) Changes from upgrade:
  * (`app/ante`) Moved `AnteHandler` implementation to `app/ante`
  * (keys) Marked `ExportEthKeyCommand` as **UNSAFE**
  * (evm) Moved `BeginBlock` and `EndBlock` to `x/evm/abci.go`
* (evm) [RAMPAGEXP#255](https://github.com/cosmos/ethermint/pull/255) Add missing `GenesisState` fields and support `ExportGenesis` functionality.
* [RAMPAGEXP#272](https://github.com/cosmos/ethermint/pull/272) Add `Logger` for evm module.
* [RAMPAGEXP#317](https://github.com/cosmos/ethermint/pull/317) `GenesisAccount` validation.
* (evm) [RAMPAGEXP#319](https://github.com/cosmos/ethermint/pull/319) Various evm improvements:
  * Add transaction `[]*ethtypes.Logs` to evm's `GenesisState` to persist logs after an upgrade.
  * Remove evm `CodeKey` and `BlockKey`in favor of a prefix `Store`.
  * Set `BlockBloom` during `EndBlock` instead of `BeginBlock`.
  * `Commit` state object and `Finalize` storage after `InitGenesis` setup.
* (rpc) [RAMPAGEXP#325](https://github.com/cosmos/ethermint/pull/325) `eth_coinbase` JSON-RPC query now returns the node's validator address.

### Features

* (build) [RAMPAGEXP#378](https://github.com/cosmos/ethermint/pull/378) Create multi-node, local, automated testnet setup with `make localnet-start`.
* (rpc) [RAMPAGEXP#330](https://github.com/cosmos/ethermint/issues/330) Implement `PublicFilterAPI`'s `EventSystem` which subscribes to Tendermint events upon `Filter` creation.
* (rpc) [RAMPAGEXP#231](https://github.com/cosmos/ethermint/issues/231) Implement `NewBlockFilter` in rpc/filters.go which instantiates a polling block filter
  * Polls for new blocks via `BlockNumber` rpc call; if block number changes, it requests the new block via `GetBlockByNumber` rpc call and adds it to its internal list of blocks
  * Update `uninstallFilter` and `getFilterChanges` accordingly
  * `uninstallFilter` stops the polling goroutine
  * `getFilterChanges` returns the filter's internal list of block hashes and resets it
* (rpc) [RAMPAGEXP#54](https://github.com/cosmos/ethermint/issues/54), [RAMPAGEXP#55](https://github.com/cosmos/ethermint/issues/55)
  Implement `eth_getFilterLogs` and `eth_getLogs`:
  * For a given filter, look through each block for transactions. If there are transactions in the block, get the logs from it, and filter using the filterLogs method
  * `eth_getLogs` and `eth_getFilterChanges` for log filters use the same underlying method as `eth_getFilterLogs`
  * update `HandleMsgEthereumTx` to store logs using the ethereum hash
* (app) [RAMPAGEXP#187](https://github.com/cosmos/ethermint/issues/187) Add support for simulations.

### Bug Fixes

* (evm) [RAMPAGEXP#767](https://github.com/cosmos/ethermint/issues/767) Fix error of timeout when using Truffle to deploy contract.
* (evm) [RAMPAGEXP#751](https://github.com/cosmos/ethermint/issues/751) Fix misused method to calculate block hash in evm related function.
* (evm) [RAMPAGEXP#721](https://github.com/cosmos/ethermint/issues/721) Fix mismatch block hash in rpc response when use eth.getBlock.
* (evm) [RAMPAGEXP#730](https://github.com/cosmos/ethermint/issues/730) Fix 'EIP2028' not open when Istanbul version has been enabled.
* (app) [RAMPAGEXP#749](https://github.com/cosmos/ethermint/issues/749) Fix panic in `AnteHandler` when gas price larger than 100000
* (rpc) [RAMPAGEXP#305](https://github.com/cosmos/ethermint/issues/305) Update `eth_getTransactionCount` to check for account existence before getting sequence and return 0 as the nonce if it doesn't exist.
* (evm) [RAMPAGEXP#319](https://github.com/cosmos/ethermint/pull/319) Fix `SetBlockHash` that was setting the incorrect height during `BeginBlock`.
* (evm) [RAMPAGEXP#176](https://github.com/cosmos/ethermint/issues/176) Updated Web3 transaction hash from using RLP hash. Now all transaction hashes exposed are amino hashes:
  * Removes `Hash()` (RLP) function from `MsgEthereumTx` to avoid confusion or misuse in future.
