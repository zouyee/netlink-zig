# netlink - netlink library for zig #


The netlink package provides a simple netlink library for zig. Netlink
is the interface a user-space program in linux uses to communicate with
the kernel. It can be used to add and remove interfaces, set ip addresses
and routes, and configure ipsec. Netlink communication requires elevated
privileges, so in most cases this code needs to be run as root. Since
low-level netlink messages are inscrutable at best, the library attempts
to provide an api that is loosely modeled on the CLI provided by iproute2.
Actions like `ip link add` will be accomplished via a similarly named
function like AddLink(). This library inpisred by 
[netlink](https://github.com/vishvananda/netlink)) but was
heavily rewritten to improve testability, performance, and to add new
functionality like ipsec xfrm handling.

## Local Build and Test ##

> TODO

## Examples ##

> TODO

## Future Work ##

Many pieces of netlink are not yet fully supported in the high-level
interface. Aspects of virtually all of the high-level objects don't exist.
Many of the underlying primitives are there, so its a matter of putting
the right fields into the high-level objects and making sure that they
are serialized and deserialized correctly in the Add and List methods.

There are also a few pieces of low level netlink functionality that still
need to be implemented. Routing rules are not in place and some of the
more advanced link types. Hopefully there is decent structure and testing
in place to make these fairly straightforward to add.
