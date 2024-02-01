Designated Router Election
==========================

*  Router on a boardcast segment elect a designated router
*  The elelction of a designated router on a broadcast segment is a nondeterministic event
*  A lot of Ethernet segments are used as point-to-point(P2P), full-duplex links

![](media/010301.JPG)

On a broadcast segment,OSPF Routers elect a single node to represent the segment to the network. This node is called 
the designated router. if forms an OSPF adjacency with all routers on the segment and floods a network LSA into the appropriate 
area. The criteria for electing the designated router is the highest configured priority on the segment,which is segment to 128 
by default. The second criteria for electing a designated router is the highest router ID on the segment.

The election of a designated router on a broadcast segment is a nondeterministic event.Thus ,the router with the best criteria
might not always be the designated router for the segment. An Operational designated router manitains its status on the segment
until it stops operating.

The first OSPF router on a link determines itself as the designated router,if it does not detect a Hello from another router within
the 40-second election period.

Currently, a lot of Ethernet segments are used as point-to-point(P2P) ,full-duplex links.This eliminates the need for a designated
router election.

Use the interface-type p2p command on both sides of the link to change the default interface type. Using this option can save up to
40 seconds of wait time to get the OSPF adjacency to a full state.

