# Module 10: Asynchronous Programming

> #### Novrizal Airsyahputra - 2206081780 - Advance Programming B

---

1. Understanding how it works.

**ANS:**

![understanding](https://cdn.discordapp.com/attachments/1111642397248598067/1236056603153928316/image.png?ex=66369eeb&is=66354d6b&hm=27ff6f7f7e6974e3a97ae76e9472373a10d67e2fd81893a03e403edae242128d&)
Based on the image above, we can see that the "hey hey" appears before "howdy!" and "done!". 
In the `src/main.rs`, we can also see that the print statement "hey hey" is in the main thread (not inside the asynchronous task). 
So, until the executor calls the `run()`, `spawner.spawn(async {...});` won't execute its task.
