# Ledger Reef app
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

-------------------

![zondax](docs/zondax.jpg)

_Please visit our website at [zondax.ch](zondax.ch)_

------------------
This project contains the Kusama app (https://kusama.network/) for Ledger Nano S and X.

- Ledger Nano S/X BOLOS app
- Specs / Documentation
- C++ unit tests
- Zemu tests

For more information: [How to build](docs/build.md)

## ATTENTION

Please:

- **Do not use in production**
- **Do not use a Ledger device with funds for development purposes.**
- **Have a separate and marked device that is used ONLY for development and testing**

# Reef v5 and higher

## System

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|fill_block |    | :white_check_mark:| :white_check_mark:| `Perbill` _ratio <br/> |
|remark |    | :white_check_mark:| :white_check_mark:| `Bytes` _remark <br/> |
|set_heap_pages |    | :white_check_mark:| :white_check_mark:| `u64` pages <br/> |
|set_code |    | :white_check_mark:| :white_check_mark:| `Bytes` code <br/> |
|set_code_without_checks |    | :white_check_mark:| :white_check_mark:| `Bytes` code <br/> |
|set_changes_trie_config |    |   |   | `Option<ChangesTrieConfiguration>` changes_trie_config <br/> |
|set_storage |    |   |   | `Vec<KeyValue>` items <br/> |
|kill_storage |    |   |   | `Vec<Key>` keys <br/> |
|kill_prefix |    |   |   | `Key` prefix <br/>`u32` _subkeys <br/> |
|remark_with_event |    | :white_check_mark:|   | `Bytes` remark <br/> |

## RandomnessCollectiveFlip

Empty

## Scheduler

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|schedule |    |   |   | `BlockNumber` when <br/>`Option<Period>` maybe_periodic <br/>`Priority` priority <br/>`Call` call <br/> |
|cancel |    |   |   | `BlockNumber` when <br/>`u32` index <br/> |
|schedule_named |    |   |   | `Bytes` id <br/>`BlockNumber` when <br/>`Option<Period>` maybe_periodic <br/>`Priority` priority <br/>`Call` call <br/> |
|cancel_named |    |   |   | `Bytes` id <br/> |
|schedule_after |    |   |   | `BlockNumber` after <br/>`Option<Period>` maybe_periodic <br/>`Priority` priority <br/>`Call` call <br/> |
|schedule_named_after |    |   |   | `Bytes` id <br/>`BlockNumber` after <br/>`Option<Period>` maybe_periodic <br/>`Priority` priority <br/>`Call` call <br/> |

## Babe

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|report_equivocation |    |   |   | `BabeEquivocationProof` equivocation_proof <br/>`KeyOwnerProof` key_owner_proof <br/> |
|report_equivocation_unsigned |    |   |   | `BabeEquivocationProof` equivocation_proof <br/>`KeyOwnerProof` key_owner_proof <br/> |
|plan_config_change |    |   |   | `NextConfigDescriptor` config <br/> |

## Timestamp

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|set |    | :white_check_mark:|   | `Compact<Moment>` now <br/> |

## Indices

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|claim |    | :white_check_mark:|   | `AccountIndex` index <br/> |
|transfer |    | :white_check_mark:|   | `AccountId` new <br/>`AccountIndex` index <br/> |
|free |    | :white_check_mark:|   | `AccountIndex` index <br/> |
|force_transfer |    | :white_check_mark:|   | `AccountId` new <br/>`AccountIndex` index <br/>`bool` freeze <br/> |
|freeze |    | :white_check_mark:|   | `AccountIndex` index <br/> |

## Balances

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|transfer | :white_check_mark: | :white_check_mark:| :white_check_mark:| `LookupSource` dest <br/>`Compact<Balance>` value <br/> |
|set_balance |    | :white_check_mark:| :white_check_mark:| `LookupSource` who <br/>`Compact<Balance>` new_free <br/>`Compact<Balance>` new_reserved <br/> |
|force_transfer |    | :white_check_mark:| :white_check_mark:| `LookupSource` source <br/>`LookupSource` dest <br/>`Compact<Balance>` value <br/> |
|transfer_keep_alive | :white_check_mark: | :white_check_mark:| :white_check_mark:| `LookupSource` dest <br/>`Compact<Balance>` value <br/> |
|transfer_all |    | :white_check_mark:|   | `LookupSource` dest <br/>`bool` keep_alive <br/> |

## TransactionPayment

Empty

## Authorship

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|set_uncles |    |   |   | `Vec<Header>` new_uncles <br/> |

## Staking

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|bond | :white_check_mark: | :white_check_mark:|   | `LookupSource` controller <br/>`Compact<BalanceOf>` value <br/>`RewardDestination` payee <br/> |
|bond_extra | :white_check_mark: | :white_check_mark:|   | `Compact<BalanceOf>` max_additional <br/> |
|unbond | :white_check_mark: | :white_check_mark:|   | `Compact<BalanceOf>` value <br/> |
|withdraw_unbonded | :white_check_mark: | :white_check_mark:|   | `u32` num_slashing_spans <br/> |
|validate | :white_check_mark: | :white_check_mark:|   | `ValidatorPrefs` prefs <br/> |
|nominate | :white_check_mark: | :white_check_mark:|   | `Vec<LookupSource>` targets <br/> |
|chill | :white_check_mark: | :white_check_mark:|   |  |
|set_payee | :white_check_mark: | :white_check_mark:|   | `RewardDestination` payee <br/> |
|set_controller | :white_check_mark: | :white_check_mark:|   | `LookupSource` controller <br/> |
|set_validator_count |    | :white_check_mark:|   | `Compact<u32>` new <br/> |
|increase_validator_count |    | :white_check_mark:|   | `Compact<u32>` additional <br/> |
|scale_validator_count |    |   |   | `Percent` factor <br/> |
|force_no_eras |    | :white_check_mark:|   |  |
|force_new_era |    | :white_check_mark:|   |  |
|set_invulnerables |    | :white_check_mark:|   | `Vec<AccountId>` invulnerables <br/> |
|force_unstake |    | :white_check_mark:|   | `AccountId` stash <br/>`u32` num_slashing_spans <br/> |
|force_new_era_always |    | :white_check_mark:|   |  |
|cancel_deferred_slash |    | :white_check_mark:|   | `EraIndex` era <br/>`Vec<u32>` slash_indices <br/> |
|payout_stakers | :white_check_mark: | :white_check_mark:|   | `AccountId` validator_stash <br/>`EraIndex` era <br/> |
|rebond | :white_check_mark: | :white_check_mark:|   | `Compact<BalanceOf>` value <br/> |
|set_history_depth |    | :white_check_mark:|   | `Compact<EraIndex>` new_history_depth <br/>`Compact<u32>` _era_items_deleted <br/> |
|reap_stash |    | :white_check_mark:|   | `AccountId` stash <br/>`u32` num_slashing_spans <br/> |
|kick |    | :white_check_mark:|   | `Vec<LookupSource>` who <br/> |
|update_staking_limits |    | :white_check_mark:|   | `BalanceOf` min_nominator_bond <br/>`BalanceOf` min_validator_bond <br/>`Option<u32>` max_nominator_count <br/>`Option<u32>` max_validator_count <br/> |
|chill_other |    | :white_check_mark:|   | `AccountId` controller <br/> |

## Offences

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|

## Historical

Empty

## Session

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|set_keys | :white_check_mark: | :white_check_mark:|   | `Keys` keys <br/>`Bytes` proof <br/> |
|purge_keys | :white_check_mark: | :white_check_mark:|   |  |

## Grandpa

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|report_equivocation |    |   |   | `GrandpaEquivocationProof` equivocation_proof <br/>`KeyOwnerProof` key_owner_proof <br/> |
|report_equivocation_unsigned |    |   |   | `GrandpaEquivocationProof` equivocation_proof <br/>`KeyOwnerProof` key_owner_proof <br/> |
|note_stalled |    | :white_check_mark:|   | `BlockNumber` delay <br/>`BlockNumber` best_finalized_block_number <br/> |

## ImOnline

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|heartbeat |    |   |   | `Heartbeat` heartbeat <br/>`Signature` _signature <br/> |

## AuthorityDiscovery

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|


## Identity

| Name        | Light | XL | Nesting | Arguments |
| :---------- |:------------:|:--------:|:--------:|:--------|
|add_registrar |    | :white_check_mark:|   | `AccountId` account <br/> |
|set_identity |    |   |   | `IdentityInfo` info <br/> |
|set_subs |    |   |   | `Vec<(AccountId,Data)>` subs <br/> |
|clear_identity |    | :white_check_mark:|   |  |
|request_judgement |    | :white_check_mark:|   | `Compact<RegistrarIndex>` reg_index <br/>`Compact<BalanceOf>` max_fee <br/> |
|cancel_request |    | :white_check_mark:|   | `RegistrarIndex` reg_index <br/> |
|set_fee |    | :white_check_mark:|   | `Compact<RegistrarIndex>` index <br/>`Compact<BalanceOf>` fee <br/> |
|set_account_id |    | :white_check_mark:|   | `Compact<RegistrarIndex>` index <br/>`AccountId` new <br/> |
|set_fields |    |   |   | `Compact<RegistrarIndex>` index <br/>`IdentityFields` fields <br/> |
|provide_judgement |    |   |   | `Compact<RegistrarIndex>` reg_index <br/>`LookupSource` target <br/>`IdentityJudgement` judgement <br/> |
|kill_identity |    | :white_check_mark:|   | `LookupSource` target <br/> |
|add_sub |    |   |   | `LookupSource` sub <br/>`Data` data <br/> |
|rename_sub |    |   |   | `LookupSource` sub <br/>`Data` data <br/> |
|remove_sub |    | :white_check_mark:|   | `LookupSource` sub <br/> |
|quit_sub |    | :white_check_mark:|   |  |

