On a 64-bit Windows installation is it possible to make both 32-bit and 64-bit dumps of
32-bit processes.
The task manager will create a 64-bit dump, which therefore is often what you end up with
users sending you. This is not a problem for native executeables since you can still load
it in windbg and use the !wow64exts.sw extension to switch into the 32-bit view.

However if your process is a .NET process and you want to use SoS to investigate it then
you are out of luck, you'll just get the message
"SOS does not support the current target architecture."

This extension gets around this by hooking/patching functions in dbgeng.dll so that SoS
thinks it's working with a 32-bit dump.

** Usage **
Copy soswow64.dll into the "winxp" subfolder of windbg. Then after loading a 64-bit memory
dump of a 32-bit process you can simply load the extension:

0:000> .load soswow64
Successfully hooked IDebugControl::GetExecutingProcessorType.
Successfully patched DbgEng!X86MachineInfo::ConvertCanonContextToTarget.
