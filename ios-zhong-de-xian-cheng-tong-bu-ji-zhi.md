# GCD\(Grand Central Dispatch\)学习

## Dispatch Queues

Dispatch Queues are objects that maintain a queue of tasks, either anonymous code blocks or functions, and execute these tasks in their turn. The library automatically creates several queues with different priority levels that execute several tasks concurrently, selecting the optimal number of tasks to run based on the operating environment. A client to the library may also create any number of serial queues, which execute tasks in the order they are submitted, one at a time.[\[12\]](https://en.wikipedia.org/wiki/Grand_Central_Dispatch#cite_note-OSConcepts-12) Because a serial queue can only run one task at a time, each task submitted to the queue is critical with regard to the other tasks on the queue, and thus a serial queue can be used instead of a [lock](https://en.wikipedia.org/wiki/Lock_%28computer_science%29) on a contended resource.

## dispatch groups

Dispatch Groups are objects that allow several tasks to be grouped for later joining. Tasks can be added to a queue as a member of a group, and then the client can use the group object to wait until all of the tasks in that group have completed.

### dispatch\_group\_t

A dispatch group is a mechanism for monitoring a set of blocks. Your application can monitor the blocks in the group synchronously or asynchronously depending on your needs. By extension, a group can be useful for synchronizing for code that depends on the completion of other tasks.

Note that the blocks in a group may be run on different queues, and each individual block can add more blocks to the group.

The dispatch group keeps track of how many blocks are outstanding, and GCD retains the group until all its associated blocks complete execution.





## dispatch semaphore

Dispatch Semaphores are objects that allow a client to permit only a certain number of tasks to execute concurrently.



## dispatch barriers







学习资源：

维基百科 - [Grand Central Dispatch](https://en.wikipedia.org/wiki/Grand_Central_Dispatch)

Apple Document - [Dispatch](https://developer.apple.com/documentation/dispatch?language=objc)

WWDC - [Modernizing Grand Central Dispatch Usage](https://developer.apple.com/videos/play/wwdc2017/706/)



