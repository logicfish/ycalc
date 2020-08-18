# ycalc
Lambda calculi simulator and analysis software in D language

## These are the component parts

Simulator - A "virtual machine" that can run SEAL processes and perform reduction in real-time. The machine communicates with the host using PI extrusion.

Parser - The parser can create structures (at runtime) or code (at compile time) that represents expressions written in the SEAL algebra notation.

Serialiser/deserialiser - This component implements the capability for agents to migrate between threads, processes and hosts. Also, pi channels that cross host boundaries
use this component.

Most operations, for example SEAL mobility, are conducted using a custom implementation of the pi calculus. Pi operations are performed synchronously in a single thread 
(per "host"), so this removes the requirement for complex locking code. Furthermore, we can guarantee that no mobility or other operation that would change the process structure
will be executed inside an application callback.


