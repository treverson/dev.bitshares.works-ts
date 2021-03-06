#### BitShares Core - graphene::chain

# Object Type
*enum graphene::chain::object_type*

List all object types from all namespaces here so they can be easily reflected and displayed in debug output. If a 3rd party wants to extend the core code then they will have to change the packed_object::type field from enum_type to uint16 to avoid warnings when converting packed_objects to/from json. 

| Enumerator |   |
|---|---|
| null_object_type 	 |   |
| base_object_type 	 |   |
| account_object_type  |   |	
| asset_object_type  |   |	
| force_settlement_object_type 	 |   |
| committee_member_object_type |   | 	
| witness_object_type  |   |	
| limit_order_object_type  |   |	
| call_order_object_type  |   |	
| custom_object_type  |   |	
| proposal_object_type  |   |	
| operation_history_object_type |   | 	
| withdraw_permission_object_type |   | 	
| vesting_balance_object_typev |   | 	
| worker_object_type 	 |   |
| balance_object_type  |   |	
| OBJECT_TYPE_COUNT 	| Sentry value which contains the number of different object types. | 


***

# Object Names and Detailed Descriptions
*graphene::chain Namespace: Class - Objects*

|  | Detailed Description |
|---|---|
| [account_balance_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1account__balance__object.html) | Tracks the balance of a single account/asset pairThis object is indexed on owner and asset_type so that black swan events in asset_type can be processed quickly  |  
| [account_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1account__object.html) | This class represents an account on the object graphAccounts are the primary unit of authority on the graphene system. Users must have an account in order to use assets, trade in the markets, vote for committee_members, etc  | 
|[account_statistics_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1account__statistics__object.html) | This object contains regularly updated statistical data about an account. It is provided for the purpose of separating the account data that changes frequently from the account data that is mostly static, which will minimize the amount of data that must be backed up as part of the undo history everytime a transfer is made.  | 
|[account_transaction_history_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1account__transaction__history__object.html)  | a node in a linked list of operation_history_objectsAccount history is important for users and wallets even though it is not part of "core validation". Account history is maintained as a linked list stored on disk in a stack. Each account will point to the most recent account history object by ID. When a new operation relativent to that account is processed a new account history object is allcoated at the end of the stack and intialized to point to the prior object  | 
|[asset_bitasset_data_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1asset__bitasset__data__object.html)  | contains properties that only apply to bitassets (market issued assets) |	  | 
|[asset_dynamic_data_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1asset__dynamic__data__object.html)  | tracks the asset information that changes frequentlyBecause the asset_object is very large it doesn't make sense to save an undo state for all of the parameters that never change. This object factors out the parameters of an asset that change in almost every transaction that involves the asset  |
|[asset_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1asset__object.html)  | tracks the parameters of an assetAll assets have a globally unique symbol name that controls how they are traded and an issuer who has authority over the parameters of the asset.	  | 
|[balance_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1balance__object.html)  |   | 
|[blinded_balance_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1blinded__balance__object.html)  | tracks a blinded balance commitment	  | 
|[block_summary_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1block__summary__object.html)  | tracks minimal information about past blocks to implement TaPOSWhen attempting to calculate the validity of a transaction we need to lookup a past block and check its block hash and the time it occurred so we can calculate whether the current transaction is valid and at what time it should expire.  | 
|	[budget_record_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1budget__record__object.html)  |   | 
|	[buyback_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1buyback__object.html) 	 |  buyback_authority_object only exists to help with a specific indexing problem. We want to be able to iterate over all assets that have a buyback program. However, assets which have a buyback program are very rare. So rather than indexing asset_object by the buyback field (requiring additional bookkeeping for every asset), we instead maintain a buyback_object pointing to each asset which has buyback (requiring additional bookkeeping only for every asset which has buyback). | 
|[call_order_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1call__order__object.html)  | tracks debt and call price information  | 
|[chain_property_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1chain__property__object.html)  | Contains invariants which are set at genesis and never changed. 	  | 
|[collateral_bid_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1collateral__bid__object.html)  | bids of collateral for debt after a black swan  | 
|[committee_member_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1committee__member__object.html)  | tracks information about a committee_member account.A committee_member is responsible for setting blockchain parameters and has dynamic multi-sig control over the committee account. The current set of active committee_members has control.   | 
|[database](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1database.html)  | tracks the blockchain state in an extensible manner More...  | 
|[dynamic_global_property_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1dynamic__global__property__object.html)  | Maintains global state information (committee_member list, current fees)This is an implementation detail. The values here are calculated during normal chain operations and reflect the current values of global blockchain properties]() 	  | 
|[fba_accumulator_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1fba__accumulator__object.html) 	 | fba_accumulator_object accumulates fees to be paid out via buyback or other FBA mechanism.   | 
|	[force_settlement_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1force__settlement__object.html)  | tracks bitassets scheduled for force settlement at some point in the future	  | 
|	[global_property_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1global__property__object.html)  | Maintains global state information (committee_member list, current fees)This is an implementation detail. The values here are set by committee_members to tune the blockchain parameters.	
|[limit_order_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1limit__order__object.html)  | an offer to sell a amount of a asset at a specified exchange rate by a certain timeThis limit_order_objects are indexed by expiration and is automatically deleted on the first block after expiration.	  | 
|[node_property_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1node__property__object.html)  | 	Contains per-node database configuration	  | 
|[operation_history_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1operation__history__object.html) | 	tracks the history of all logical operations on blockchain stateAll operations and virtual operations result in the creation of an operation_history_object that is maintained on disk as a stack. Each real or virtual operation is assigned a unique ID / sequence number that it can be referenced by.  |   | 
|	[proposal_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1proposal__object.html)  | tracks the approval of a partially approved transaction 	   | 
|[special_authority_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1special__authority__object.html)  | special_authority_object only exists to help with a specific indexing problem. We want to be able to iterate over all accounts that contain a special authority. However, accounts which have a special_authority are very rare. So rather than indexing account_object by the special_authority fields (requiring additional bookkeeping for every account), we instead maintain a special_authority_object pointing to each account which has special_authority (requiring additional bookkeeping only for every account which has special_authority).   | 	
| [transaction_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1transaction__object.html) | The purpose of this object is to enable the detection of duplicate transactions. When a transaction is included in a block a transaction_object is added. At the end of block processing all transaction_objects that have expired can be removed from the index.  |  
|[vesting_balance_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1vesting__balance__object.html) 	 |  Vesting balance object is a balance that is locked by the blockchain for a period of time.   | 
|	[withdraw_permission_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1withdraw__permission__object.html)  | Grants another account authority to withdraw a limited amount of funds per interval	   | 
|[witness_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1witness__object.html) 	 |    | 
| 	[witness_schedule_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1witness__schedule__object.html)  |    | 
|[worker_object](https://bitshares.org/doxygen/classgraphene_1_1chain_1_1worker__object.html) | Worker object contains the details of a blockchain worker. See The Blockchain Worker System for details.   | 


***
