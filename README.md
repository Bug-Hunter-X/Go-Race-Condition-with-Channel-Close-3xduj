# Go Race Condition with Channel Close

This repository demonstrates a race condition in a Go program that uses channels and goroutines. The program produces unexpected results, illustrating the need for careful synchronization when dealing with concurrent operations in Go.

## Bug Description

The primary issue lies in the lack of proper synchronization between the goroutine sending data to the channel (`ch`) and the goroutine receiving data from it.  The sender closes the channel, `ch`, before the receiver has finished reading. This can lead to the receiver missing data or the program panicking, depending on the execution order and timing.