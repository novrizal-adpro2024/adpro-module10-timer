# Module 10: Asynchronous Programming

> #### Novrizal Airsyahputra - 2206081780 - Advance Programming B

---

1. Understanding how it works.

**ANS:**

![understanding](https://cdn.discordapp.com/attachments/1111642397248598067/1236056603153928316/image.png?ex=66369eeb&is=66354d6b&hm=27ff6f7f7e6974e3a97ae76e9472373a10d67e2fd81893a03e403edae242128d&)

Based on the output above, we can see that the "hey hey" appears before "howdy!" and "done!". 
In the `src/main.rs`, we can also see that the print statement "hey hey" is in the main thread (not inside the asynchronous task). 
So, until the executor calls the `run()`, `spawner.spawn(async {...});` won't execute its task.

2. Multiple Spawn and removing drop.

**ANS:**

![multiple](https://cdn.discordapp.com/attachments/1111642397248598067/1236059143769686087/image.png?ex=6636a148&is=66354fc8&hm=859854e83d905e4ab4f0d070427fd335bc379d764181203faf40682843acaf4c&)

Based on the output above, we can see that the program doesn't halt at all (there is cursor). 
This occurs because the drop function isn't executed, signaling to the executor that no more tasks will be added to the queue. 
Moreover, the task order appears irregular, depending on the scheduling algorithm of the executor. 
Each task created by the spawner consumes resources, so creating a large number of tasks would inevitably prolong program execution.
**Important note:** The printing of messages isn't always in order, though the execution might be in order. 
