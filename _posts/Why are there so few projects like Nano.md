# Why are there so few projects like Nano?

**Leo Young, 12/04/2024** 

We have noticed that there are few projects with the same positioning and similar functions as Nano on GitHub, and only **ELK/Packetbeat** is well-known. Of course, this is not because this scenario is not important, but it may be another reason;

In addition, we also noticed that even excellent Packetbeat still have poor processing performance and resource overhead, and do not have the basis for large-scale deployment and all-weather operation; This also exposes a problem that all such programs must face, that is, **how to process as much traffic data as possible with the lowest resource cost, parse the most fine-grained content, and calculate various communication and performance indicators.**

Undoubtedly, these contradictions are a nightmare for almost all system tool architects and programmers....
Even more unfortunately, the minimum resource overhead here is based on the criterion of not adding new computing resources and not affecting business operations. For most hosts in production environments, this standard often requires less than 10% of a single vCPU.

Well, we seem to have found the reason why there are so few programs of this kind, right?

------

**microflow.io**

leoyoung@microflow.io