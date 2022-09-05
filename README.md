# Company DAO smart contract audit 
## Аудит проводился в ветке V4, на основании коммита, по ссылке:
> https://github.com/company-dao/mvp-tge-v1/tree/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f

## Service.sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 1 |
| Number of informational issues | 2 |
| Number of optimization issues | 2 |

### Low issues:
- ### No check for null address


> [#99](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L99)
>
> [#100](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L100)
>
> [#101](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L101)
>
> [#102](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L102)

**Should add require if not zero adresses**





### Informational issues:
- ### Reentrancy events. Events emitted after the external calls

> [#204](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L204)
>
> [#233](https://github.com/company-dao/mvp-tge-v1/blob/f9d0733bb2d96bf8fb3512a28b539ed47032fe1f/contracts/Service.sol#L233)

**Should add events before external calls**

- ### Variable names too similar

> Service._ballotDecisionThreshold (contracts/Service.sol#48)
> 
> too similar to
> 
> Service.createPool(IPool,IGovernanceToken.TokenInfo,ITGE.TGEInfo,uint256,uint256,uint256,uint256,string).ballotDecisionThreshold_ (contracts/Service.sol#128)

> Service._ballotDecisionThreshold (contracts/Service.sol#48)
> 
> too similar to
> 
> Service.setGovernanceSettings(uint256,uint256,uint256).ballotDecisionThreshold_ (contracts/Service.sol#304)

> Service._ballotLifespan (contracts/Service.sol#50)
> 
> too similar to
> 
> Service.setGovernanceSettings(uint256,uint256,uint256).ballotLifespan_ (contracts/Service.sol#305)

> Service._ballotLifespan (contracts/Service.sol#50)
> 
> too similar to
> 
> Service.createPool(IPool,IGovernanceToken.TokenInfo,ITGE.TGEInfo,uint256,uint256,uint256,uint256,string).ballotLifespan_ (contracts/Service.sol#129)

> Service._ballotQuorumThreshold (contracts/Service.sol#46)
> 
> too similar to
> 
> Service.createPool(IPool,IGovernanceToken.TokenInfo,ITGE.TGEInfo,uint256,uint256,uint256,uint256,string).ballotQuorumThreshold_ (contracts/Service.sol#127)

> Service._ballotQuorumThreshold (contracts/Service.sol#46)
> 
> too similar to
> 
> Service.setGovernanceSettings(uint256,uint256,uint256).ballotQuorumThreshold_ (contracts/Service.sol#303)

**Prevent variables from having similar names**



### Optimization issues:

- ### State variables that could be declared constant

Service.proposalQuorum (contracts/Service.sol#42)

Service.proposalThreshold (contracts/Service.sol#44)

**Add the constant attributes to state variables that never change**

- ### Public function that could be declared external

> getBallotQuorumThreshold()
>
> getBallotDecisionThreshold()
>
> getBallotLifespan()

_______________________________________________________________________

## Governor.sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 1 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 1 |


### Medium issues:

- ### Dangerous strict equalities
> proposal.startBlock == 0 (contracts/components/Governor.sol#101)

**Dont use strict equality to determine if an account has enough Ether or tokens.**

### Optimization issues:

- ### Public function that could be declared external

> getProposalBallotQuorumThreshold(uint256)
> 
> getProposalBallotDecisionThreshold(uint256)
> 
> getProposalBallotLifespan(uint256)
> 
> getProposal(uint256)

_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |

### Low issues:

### Informational issues:

### Optimization issues:

_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |


### Low issues:

### Informational issues:

### Optimization issues:

_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |


### Low issues:

### Informational issues:

### Optimization issues:

_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |


### Low issues:

### Informational issues:

### Optimization issues:

_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |


### Low issues:

### Informational issues:

### Optimization issues:


_______________________________________________________________________

## .sol
| Risk level | Issues |
| ------ | ------ |
| Number of high issues | 0 |
| Number of medium issues | 0 |
| Number of low issues | 0 |
| Number of informational issues | 0 |
| Number of optimization issues | 0 |


### Low issues:

### Informational issues:

### Optimization issues:



!
!
!

## Общие рекоммендации по всем контрактам:
- ### Different versions of Solidity are used

> Version used: ['0.8.13', '>=0.5.0', '>=0.7.5', '^0.8.0', '^0.8.1', '^0.8.2']

**Should use the same solidity versions in all dependent contracts**

- ### Dead code in dependent contracts

> Address.functionCall(address,bytes) (@Address.sol#85-87)
> 
> Address.functionCall(address,bytes,string) (@Address.sol#95-101) 
> 
> Address.functionCallWithValue(address,bytes,uint256) (@Address.sol#114-120) 
> 
> Address.functionCallWithValue(address,bytes,uint256,string) (@Address.sol#128-137) 
> 
> Address.functionStaticCall(address,bytes) (@Address.sol#145-147)
> 
> Address.functionStaticCall(address,bytes,string) (@Address.sol#155-162)
> 
> Address.sendValue(address,uint256) (@Address.sol#60-65)
> 
> Address.verifyCallResult(bool,bytes,string) (@Address.sol#219-229)
> 
> BeaconProxy._beacon() (@BeaconProxy.sol#37-39)
> 
> BeaconProxy._setBeacon(address,bytes) (@BeaconProxy.sol#58-60)
> 
> Context._msgData() (@Context.sol#21-23)
> 
> ERC1967Upgrade._changeAdmin(address) (@ERC1967Upgrade.sol#133-136)
> 
> ERC1967Upgrade._getAdmin() (@ERC1967Upgrade.sol#116-118)
> 
> ERC1967Upgrade._getImplementation() (@ERC1967Upgrade.sol#38-40)
> 
> ERC1967Upgrade._setAdmin(address) (@ERC1967Upgrade.sol#123-126)
> 
> ERC1967Upgrade._setImplementation(address) (@ERC1967Upgrade.sol#45-48)
> 
> ERC1967Upgrade._upgradeTo(address) (@ERC1967Upgrade.sol#55-58)
> 
> ERC1967Upgrade._upgradeToAndCall(address,bytes,bool) (@ERC1967Upgrade.sol#65-74)
> 
> ERC1967Upgrade._upgradeToAndCallUUPS(address,bytes,bool) (@ERC1967Upgrade.sol#81-99)
> 
> EnumerableSet.add(EnumerableSet.Bytes32Set,bytes32) (@EnumerableSet.sol#167-169)
> 
> EnumerableSet.add(EnumerableSet.UintSet,uint256) (@EnumerableSet.sol#315-317)
> 
> EnumerableSet.at(EnumerableSet.Bytes32Set,uint256) (@EnumerableSet.sol#205-207)
> 
> EnumerableSet.at(EnumerableSet.UintSet,uint256) (@EnumerableSet.sol#353-355)
> 
> EnumerableSet.contains(EnumerableSet.Bytes32Set,bytes32) (@EnumerableSet.sol#184-186)
> 
> EnumerableSet.contains(EnumerableSet.UintSet,uint256) (@EnumerableSet.sol#332-334)
> 
> EnumerableSet.length(EnumerableSet.Bytes32Set) (@EnumerableSet.sol#191-193)
> 
> EnumerableSet.length(EnumerableSet.UintSet) (@EnumerableSet.sol#339-341)
> 
> EnumerableSet.remove(EnumerableSet.Bytes32Set,bytes32) (@EnumerableSet.sol#177-179)
> 
> EnumerableSet.remove(EnumerableSet.UintSet,uint256) (@EnumerableSet.sol#325-327)
> 
> EnumerableSet.values(EnumerableSet.Bytes32Set) (@EnumerableSet.sol#217-227)
> 
> EnumerableSet.values(EnumerableSet.UintSet) (@EnumerableSet.sol#365-375)
> 
> StorageSlot.getBooleanSlot(bytes32) (@StorageSlot.sol#62-67)
> 
> StorageSlot.getBytes32Slot(bytes32) (@StorageSlot.sol#72-77)
> 
> StorageSlot.getUint256Slot(bytes32) (@StorageSlot.sol#82-87)

**There is a lot of code in dependent contracts that is not used in the project, they should be removed and contracts should be refactored using only the code that is needed**

- ### Incorrect versions of Solidity

> Service.proposalQuorum (contracts/Service.sol#42)
> 
> Service.proposalThreshold (contracts/Service.sol#44)

> Version used: 0.8.13

**0.8.4 - 0.8.7 Use this stable pragma version**
