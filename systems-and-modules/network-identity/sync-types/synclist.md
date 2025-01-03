# SyncList

Synchronized List, or most commonly referred as "SyncList" are easily definable in your code, and will handle automatically align a list between all [players](../../playerid-client-connection.md).&#x20;

Working with SyncLists is as easy as using a regular list, only having to be mindful of who has authority.

SyncLists are built with the Network Module setup, meaning that you have to initialize it. Below is a usage example:

```csharp
//Creates a new instance of the list - `true` means it is owner auth. 
[SerializeField] private SyncList<int> myList = new(true);

protected override void OnSpawned()
{
    //Subscribing to changes made to the list
    myList.onChanged += OnListChanged;
}

private void OnListChanged(SyncListChange<int> change)
{
    //This is called for everyone when the list changes.
    //It will log out the value, index and operation
    Debug.Log($"List updated: {change}");
}

private void ChangeMyList()
{
    //This will change or add a value
    myList[0] = 0.69f;
    
    //This will remove the value
    myList.Remove(0.69f);
    
    //This will remove the entry at the given index
    myList.RemoveAt(0);
    
    //This will clear the list
    myList.Clear();
    
    //This will insert a value at the given index
    myList.Insert(1, 420f);
    
    //This will mark the index as dirty
    myList.SetDirty(0);
}
```

The SyncList is serialized in editor, however, you shouldn't edit it here. This is purely for visual debugging

<figure><img src="../../../.gitbook/assets/Unity_SyncList.png" alt=""><figcaption></figcaption></figure>
