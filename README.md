## Introduction

This is a project to develop Wireshark Dissector for "OSPFv3 extensions for Segment Routing". 
IETF draft [draft-ietf-ospf-ospfv3-segment-routing-extensions-06](https://tools.ietf.org/html/draft-ietf-ospf-ospfv3-segment-routing-extensions-06)

## Dissection

OSPF, IS-IS or BGP is used as the control protocols in Segment routing. This dissector deals with one part of OSPF extension needed for segment routing.

Segment Routing uses OSPF Router Information Opaque LSA (Type 12) to propagate Segment ID (SID/Label). Different types of TLVs are defined to carry Segment Routing information. 

Extensions for LSA format has also been proposed to support SID/Label Binding, ERO, Adjacency SID etc. 

  - This project does not deal with the LSA extension. 
  - The dissection is focused on Routing Information Opaque LSA TLV formats

## TLVs to be Dissected

> SR-Algorithm TLV
asdfasdf
asdf

    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |              Type             |             Length            |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |   Algorithm 1 | Algorithm...  |   Algorithm n |               |
   +-                                                             -+
   |                                                               |
   +                                                               +


> SID/Label Range TLV

    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |              Type             |             Length            |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                    Range Size                 |   Reserved    |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                        Sub-TLVs (variable)                    |
   +-                                                             -+
   |                                                               |
   +                                                               +