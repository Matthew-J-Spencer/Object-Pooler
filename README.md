# Unity Object Pooler

![](https://i.imgur.com/NHbr6f4.png)

An abstract class aimed at simplifying the new object pooling workflow in Unity 2021.
Video found here: https://youtu.be/7EZ2F-TzHYw

### How to use

```csharp
public class ShapeSpawner : PoolerBase<Shape> {
    [SerializeField] private Shape _shapePrefab;

    private void Start() {
        InitPool(_shapePrefab); // Initialize the pool

        var shape = Get(); // Pull from the pool
        Release(shape); // Release back to the pool
    }

    // Optionally override the setup components
    protected override void GetSetup(Shape shape) {
        base.GetSetup(shape);
        shape.transform.position = Vector3.zero;
    }
}
```

#### Drop a star if you found it useful and subscribe on YT :)
