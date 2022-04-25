# Lecture 03：如何构建游戏世界

## 如何描述一个游戏世界

游戏世界里有什么呢？

- 动态物体（Dynamic Game Object）
- 静态物体（Static Game Object）
- 环境（Environment）：Sky, Terrain, Vegetation, etc.
- 其他游戏物体（Other Game Object）：Air Wall, Trigger Area, etc.

一开始是基于类进行继承，需要有属性和行为

但是依然会造成很多冗余，例如水陆两栖需要两种特性.

现代游戏引擎大多基于组件（Component Base）进行组合，每个 Game Object（GO）一个组件列表，每个组件都有其自己的属性和方法。

## 如何让游戏世界活起来

让世界活起来的重要函数就是 `tick()`，每一帧或者说每个 delta time 都会调用这个函数。

Object-based tick v.s. Component-based tick

如果是一个 Object 一个 Object 来进行 tick，容易实现比较直觉，容易 debug；但显然 Component-based tick 来进行批量处理的效率会更高，方便并行处理。

GO 之间的通讯和交互如何做呢？

解耦合的 Event 机制：发送事件，接收事件，事件处理

如何管理 GO 呢？

- 首先 GO 管理其实是在一个 Scene 中的
- 对于一个 GO 他都会有一个独立的 ID，这个 ID 可以用来唯一标识 GO
- 同时也可以用过 GO 的 position 来查询

接下来就成了怎么管理一个场景？

- 对于简单的场景，可以直接不用任何数据结构进行管理
- 稍微复杂的场景可以使用八叉树进行管理

现在游戏引擎常用的场景管理方式有

- Bounding Volume Hierarchy（BVH）
- Binary Space Partitioning（BSP）
- Octree
- Scene Graph

## 复杂情况处理

消息机制的时序问题（Immediate Event Sending or not）：引入邮局机制

组件依赖（Component Dependencies）
