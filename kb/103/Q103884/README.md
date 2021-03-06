---
layout: page
title: "Q103884: The OSI Model's Seven Layers Defined and Functions Explained"
permalink: /kb/103/Q103884/
---

## Q103884: The OSI Model's Seven Layers Defined and Functions Explained

{% raw %}

	Article: Q103884
	Product(s): Windows for Workgroups and Windows NT Networking Issues
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 27-FEB-2002
	
	SUMMARY
	=======
	
	The Open Systems Interconnect (OSI) model has seven layers. This article
	describes and explains them, beginning with the 'lowest' in the hierarchy (the
	physical) and proceeding to the 'highest' (the application). The layers are
	stacked this way:
	
	- Application
	
	- Presentation
	
	- Session
	
	- Transport
	
	- Network
	
	- Data Link
	
	- Physical
	
	PHYSICAL LAYER
	--------------
	
	The physical layer, the lowest layer of the OSI model, is concerned with the
	transmission and reception of the unstructured raw bit stream over a physical
	medium. It describes the electrical/optical, mechanical, and functional
	interfaces to the physical medium, and carries the signals for all of the higher
	layers. It provides:
	
	- Data encoding: modifies the simple digital signal pattern (1s and 0s) used by
	  the PC to better accommodate the characteristics of the physical medium, and
	  to aid in bit and frame synchronization. It determines:
	
	   - What signal state represents a binary 1
	
	   - How the receiving station knows when a "bit-time" starts
	
	   - How the receiving station delimits a frame
	
	- Physical medium attachment, accommodating various possibilities in the
	  medium:
	
	   - Will an external transceiver (MAU) be used to connect to the medium?
	
	   - How many pins do the connectors have and what is each pin used for?
	
	- Transmission technique: determines whether the encoded bits will be
	  transmitted by baseband (digital) or broadband (analog) signaling.
	
	- Physical medium transmission: transmits bits as electrical or optical signals
	  appropriate for the physical medium, and determines:
	
	   - What physical medium options can be used
	
	   - How many volts/db should be used to represent a given signal state, using
	     a given physical medium
	
	DATA LINK LAYER
	---------------
	
	The data link layer provides error-free transfer of data frames from one node to
	another over the physical layer, allowing layers above it to assume virtually
	error-free transmission over the link. To do this, the data link layer
	provides:
	
	- Link establishment and termination: establishes and terminates the logical
	  link between two nodes.
	
	- Frame traffic control: tells the transmitting node to "back-off" when no
	  frame buffers are available.
	
	- Frame sequencing: transmits/receives frames sequentially.
	
	- Frame acknowledgment: provides/expects frame acknowledgments. Detects and
	  recovers from errors that occur in the physical layer by retransmitting
	  non-acknowledged frames and handling duplicate frame receipt.
	
	- Frame delimiting: creates and recognizes frame boundaries.
	
	- Frame error checking: checks received frames for integrity.
	
	- Media access management: determines when the node "has the right" to use the
	  physical medium.
	
	NETWORK LAYER
	-------------
	
	The network layer controls the operation of the subnet, deciding which physical
	path the data should take based on network conditions, priority of service, and
	other factors. It provides:
	
	- Routing: routes frames among networks.
	
	- Subnet traffic control: routers (network layer intermediate systems) can
	  instruct a sending station to "throttle back" its frame transmission when the
	  router's buffer fills up.
	
	- Frame fragmentation: if it determines that a downstream router's maximum
	  transmission unit (MTU) size is less than the frame size, a router can
	  fragment a frame for transmission and re-assembly at the destination station.
	
	- Logical-physical address mapping: translates logical addresses, or names,
	  into physical addresses.
	
	- Subnet usage accounting: has accounting functions to keep track of frames
	  forwarded by subnet intermediate systems, to produce billing information.
	
	Communications Subnet:
	
	The network layer software must build headers so that the network layer software
	residing in the subnet intermediate systems can recognize them and use them to
	route data to the destination address.
	
	This layer relieves the upper layers of the need to know anything about the data
	transmission and intermediate switching technologies used to connect systems. It
	establishes, maintains and terminates connections across the intervening
	communications facility (one or several intermediate systems in the
	communication subnet).
	
	In the network layer and the layers below, peer protocols exist between a node
	and its immediate neighbor, but the neighbor may be a node through which data is
	routed, not the destination station. The source and destination stations may be
	separated by many intermediate systems.
	
	TRANSPORT LAYER
	---------------
	
	The transport layer ensures that messages are delivered error-free, in sequence,
	and with no losses or duplications. It relieves the higher layer protocols from
	any concern with the transfer of data between them and their peers.
	
	The size and complexity of a transport protocol depends on the type of service it
	can get from the network layer. For a reliable network layer with virtual
	circuit capability, a minimal transport layer is required. If the network layer
	is unreliable and/or only supports datagrams, the transport protocol should
	include extensive error detection and recovery.
	
	The transport layer provides:
	
	- Message segmentation: accepts a message from the (session) layer above it,
	  splits the message into smaller units (if not already small enough), and
	  passes the smaller units down to the network layer. The transport layer at
	  the destination station reassembles the message.
	
	- Message acknowledgment: provides reliable end-to-end message delivery with
	  acknowledgments.
	
	- Message traffic control: tells the transmitting station to "back-off" when no
	  message buffers are available.
	
	- Session multiplexing: multiplexes several message streams, or sessions onto
	  one logical link and keeps track of which messages belong to which sessions
	  (see session layer).
	
	Typically, the transport layer can accept relatively large messages, but there
	are strict message size limits imposed by the network (or lower) layer.
	Consequently, the transport layer must break up the messages into smaller units,
	or frames, prepending a header to each frame.
	
	The transport layer header information must then include control information,
	such as message start and message end flags, to enable the transport layer on
	the other end to recognize message boundaries. In addition, if the lower layers
	do not maintain sequence, the transport header must contain sequence information
	to enable the transport layer on the receiving end to get the pieces back
	together in the right order before handing the received message up to the layer
	above.
	
	End-to-end layers:
	
	Unlike the lower "subnet" layers whose protocol is between immediately adjacent
	nodes, the transport layer and the layers above are true "source to destination"
	or end-to-end layers, and are not concerned with the details of the underlying
	communications facility. Transport layer software (and software above it) on the
	source station carries on a conversation with similar software on the
	destination station by using message headers and control messages.
	
	SESSION LAYER
	-------------
	
	The session layer allows session establishment between processes running on
	different stations. It provides:
	
	- Session establishment, maintenance and termination: allows two application
	  processes on different machines to establish, use and terminate a connection,
	  called a session.
	
	- Session support: performs the functions that allow these processes to
	  communicate over the network, performing security, name recognition, logging,
	  and so on.
	
	PRESENTATION LAYER
	------------------
	
	The presentation layer formats the data to be presented to the application layer.
	It can be viewed as the translator for the network. This layer may translate
	data from a format used by the application layer into a common format at the
	sending station, then translate the common format to a format known to the
	application layer at the receiving station.
	
	The presentation layer provides:
	
	- Character code translation: for example, ASCII to EBCDIC.
	
	- Data conversion: bit order, CR-CR/LF, integer-floating point, and so on.
	
	- Data compression: reduces the number of bits that need to be transmitted on
	  the network.
	
	- Data encryption: encrypt data for security purposes. For example, password
	  encryption.
	
	APPLICATION LAYER
	-----------------
	
	The application layer serves as the window for users and application processes to
	access network services. This layer contains a variety of commonly needed
	functions:
	
	- Resource sharing and device redirection
	
	- Remote file access
	
	- Remote printer access
	
	- Inter-process communication
	
	- Network management
	
	- Directory services
	
	- Electronic messaging (such as mail)
	
	- Network virtual terminals
	
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
