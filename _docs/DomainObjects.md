---
layout: page
title: Definitions
---


## Enclave

Identified by permacake with ENCLAVE CakeType, and made of :

### EnclaveConvig

* Logics available, current versions, labels, deterinistic  and non-deterministic methods invocation rules (!!! too complex)
* host list and designated leader
* event subscriptions from other enclaves
* rules that define event routing to task
* users-members of enclave and teir roles and premissions

### EnclaveState

Encalve state maintianed by designated host leader

* subscription state
* task execution state
* schedule state
* event log
* storage log

## Logic  

represent CakeStream of `CoveVersion`'s

## Code
  
  represent logic version
  
## Cake

Content Address KEy. Cake have role and type. 

### CakeType
type define what object cake refers to:

* INLINE: small piece of data that embeded in cake (size is less 33 bytes)
* SHA256: refers to blob with that hash (ContentCake)
* PORTAL: premacake that refer CakeStream
* VTREE: permacake refers VTree
* DMOUNT: permacake refers DMount specific to host and path

### CakeRole
could be either:

* synapse - Cake points on leaf blob
* or neiron - Cake points to blob that contain merkle tree node (like: CakeRack)


## InlineCake
date embeded in cake

## ContentCake
content key of blob


## Permacake (AKA Portal)
Randomly generated content id that stays permanent even so content assocciated with it changes over time.

## CakeRack

Simpliest neiron structure where list of names corespond with equally sized list of ca`Cakes`s. Names sorted alphabetically. Names could be optional, in that case `Cake`s itself assumed to be names and sorted accordingly. Optionaly `CakeRack` could include: cakes, create_time, size list 


## CakeStream

Sequence of `Cake`'s identified by permacake. `Cake` records organized by time, additionaly you can apply symbolic  labels on particular `Cake`s in the stream.


## VTree

(Volatile Tree) idetified by permacake tree of cake racks where root hash and some trunks hashes is not calculated all the time

## DMount

 Mounted directory idetified by permacake on host file system, that could be backed up, pulled and synced.

## Blob

Piece of data identified by hash cake.

## Host

## User

## Permission
 