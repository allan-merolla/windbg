 Starting, Attaching, Executing and Exiting

	
Start -> All Programs -> Debugging Tools for Windows -> WinDbg
F6
	
attach to process
Ctrl-Break
	
interrupt debugee
.detach
	
detach from a process
g
	
continue debugee execution
q
	
exit WinDbg


Getting Help
?
	
help on commands that affect the debugee
.help
	
help on commands that affect the debugger
.hh command
	
view the on line help file
!help
	
help on the extension dll at the top of the chain (e. g., SOS)


Issuing Commands
up arrow, down arrow, enter
	
scroll through command history
Right mouse button
	
paste into command window


Examining the Unmanaged Environment
lmf
	
list loaded modules with full path
lmt
	
list loaded modules with last modified timestamp
~
	
list unmanaged threads
~thread s
	
select a thread for thread specific commands
!token -n
	
view thread permissions
k
	
view the unmanaged call stack
!runaway
	
view thread CPU consumption
bp
	
set a breakpoint
.dump path
	
dump small memory image
.dump /ma path
	
dump complete memory image


Working with Extension DLLs (e. g., SOS)
.chain
	
list extensions dlls
.load clr10\sos
	
load SOS for debugging framework 1.0 / 1.1
.unload clr10\sos
	
unload SOS
.loadby sos mscorwks
	
load SOS for debugging framework 2.0


SOS Commands
!threads
	
view managed threads
!clrstack
	
view the managed call stack
!dumpstack
	
view combined unmanaged & managed call stack
!clrstack -p
	
view function call arguments
!clrstack –l
	
view stack (local) variables
!name2ee module class
	
view addresses associated with a class or method
!dumpmt –md address
	
view the method table & methods for a class
!dumpmd address
	
view detailed information about a method
!do address
	
view information about an object
!dumpheap –stat
	
view memory consumption by type
!dumpheap –min size
	
view memory consumption by object when at least size
!dumpheap –type type
	
view memory consumption for all objects of type type
!gcroot address
	
view which object are holding a reference to address
!syncblk
	
view information about managed locks


SOS 2.0 Commands
!bpmd module method
	
set breakpoint
!DumpArray address
	
view contents of an array
!PrintException
	
view information about most recent exception
