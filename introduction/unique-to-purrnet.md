---
description: >-
  A proper integration into the Unity workflow. Work with Unity and not against
  it.
---

# ‼️ Unique to PurrNet

Just like most other systems, we have the classic and expected behaviour, such as easy [synchronizing](../systems-and-modules/network-identity/sync-types/syncvar.md), [remote procedure calls](../systems-and-modules/remote-procedure-call-rpc/), [spawning & despawning](../systems-and-modules/spawning-and-despawning.md) and much more.

### Features

* [**Network Rules**](../systems-and-modules/network-manager/network-rules.md)\
  These allow for you to fully customize your networking experience for the easiest possible workflow or full server auth to ensure a cheat free experience.
* **Working&#x20;**_**WITH**_**&#x20; Unity**\
  With many networking solutions, you're constantly fighting the workflow of Unity. For example, a lot of solutions don't allow you to nest prefabs within each other. But you can do that perfectly fine with PurrNet.
* **No Network Objects!**\
  A lot of the limitations of network systems comes from the enforced use of Network Objects to identify across the network. PurrNet doesn't do that, instead we have every [NetworkBehavior ](../systems-and-modules/network-identity/networkbehaviour.md)act as its own [identity](../systems-and-modules/network-identity/).
* [**Easy spawning & despawning**](../systems-and-modules/spawning-and-despawning.md)\
  In order to spawn or despawn something, it can be as easy as just instantiating and destroying the object. Even our built in object pooling system, plays in to these standard Unity calls, making it super easy to adapt your workflow. If you prefer, you can modify your Network Rules to go to a spawn call like other systems.
* [**Network Modules**](../systems-and-modules/network-modules.md)\
  NetworkModule is a base class in the PurrNet networking solution that allows you to create modular, network-aware components that are not MonoBehaviours. These modules can be attached to any NetworkIdentity, enabling code reuse and clean separation of concerns in your networked game.
* **Easy testing**\
  We're doing as much as we can to allow for easy testing. For example at runtime, you can just drag and drop any prefab within your [Network Prefabs scriptable](../systems-and-modules/network-manager/network-prefabs.md), and it will automatically be spawned. And deleting a network identity from the hierarchy will despawn it. Making multiplayer testing super easy!
* [**Persistent Player data**](../systems-and-modules/playerid-client-connection.md)\
  With PurrNet, you have persistent user data. If a user disconnects and later connects again, they will retain the same player ID and meta data as when they left!
* **No baked components**\
  We're **NOT** big fans of baking. It simply creates unnecessary limitations and opens up for a lot of annoying edge cases, and therefore, we don't do that!
* **No scene ID baking**\
  Similar to components, we don't pre-bake scene ID's. They are calculated by the beginning of runtime, but based on the order in hierarchy, meaning that as long as the scenes align, so will the ID's across version control tools.
* [**Bots**](../systems-and-modules/bots.md)\
  In order to make bot creation easy for you, we allow for "bot" connections, and easy identification of those. They will act as if they are on the network. Similar to clients, they will also receive ObserversRPCs and TargetRPCs.
* **Generic RPCs**\
  We've managed to get generic [RPCs](../systems-and-modules/remote-procedure-call-rpc/) functioning! This can greatly aid modular code and tool makers to make even better and more powerful addons/tools for PurrNet.
* **Static RPC's**\
  **Something we haven't seen in other systems, is the ability to call** [**Remote Procedure Calls**](../systems-and-modules/remote-procedure-call-rpc/) **on static methods. Normally they have to be attached to the network behaviour itself, but with us, you get even more freedom!**
* **Returnable RPC's**\
  **This allows you to return values with methods easily, similar to how you'd naturally work with C#! The only difference being that you have to utilize the "await", in order to continue execution once the data has been received.**

### Disclaimer

The features mentioned on this page is not necessarily unique to PurrNet. These are the features that we haven't seen throughout our years of working with Unity multiplayer development. Other systems could have them or get them in the future! (This was written 27th of July, 2024)