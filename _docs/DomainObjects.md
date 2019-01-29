---
layout: page
title: Definitions
---


## Enclave

* identified by permacake with ENCLAVE CakeType
* has Logic and may assign list of CodeVersions
* has designated hosts to run Enclave with desiganted leader
* has set ot rules that define event routing to tasks
* maintain event log and storage log
* can subscribe external events from other enclaves
* users can be members of enclave and have varies roles and premissions

## Logic  

  represent stream of `CoveVersion`'s

## Code
  
  represent logic version
  
## Cake

Content Address KEy. Cake have role and type. 

### CakeType
type define what object cake refers to:
   * INLINE: small piece of data that embeded in cake
   * SHA256: refers to blob with that hash
   * PORTAL: premacake that refer CakeStream
   * VTREE: permacake refers VTree
   * DMOUNT: permacake refers DMount specific to host and path

### CakeRole 

could be either:

* synapse - Cake points on leaf blob
* or neiron - Cake points to blob that contain merkle tree node (like: CakeRack)

## CakeRack

simpliest neiron structure where list of names corespond with equally sized list of cakes. names sorted alphabetically.

## Permacake (AKA Portal)
Randomly generated content id that stays permanent even so content assocciated with it changes over time.

## CakeStream

sequence of blobs possible agregated identified by permacake

## VTree

(Volatile Tree) idetified by permacake tree of cake racks where root hash and some trunks hashes is not calculated all the time

## DMount

 Mounted directory idetified by permacake on host file system, that could be backed up, pulled and synced.

## Blob

Piece of data identified by hash cake.

## Host

## User

## Permission
 