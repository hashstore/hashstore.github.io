---
layout: page
title: Definitions
---


## Enclave

* identified by GUID cake with ENCLAVE CakeType
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

### CakeRole 

could be either:

* synapse - Cake points on leaf blob
* or neiron - Cake points to blob that contain merkle tree node (like: CakeRack)

## CakeRack

simpliest neiron structure where list of names corespond with equally sized list of cakes. names sorted alphabetically.

## Portal

## CakeStream

sequence of blobs possible agregated

## VTree

(Volatile Tree) tree of cake racks where root hash and some trunks hashes is not calculated all the time

## DMount

Mounted directory on host file system, that could be backed up, pulled and synced.

## Blob

Piece of data identified as blob.

## Host

## User

## Permission
 