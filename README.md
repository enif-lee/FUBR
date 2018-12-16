# FUBR
Fast Utilities By Runtime code generation.

## Features

### Object `Clone`

- `Clone<T>` between any different type object
- `Clone` copy to new instance
- Clone Collection
- Configure copy stratagy deep or sallow

```cs
var a = new A
{
  a = "hello",
  b = "fubr"
];

var aClone = a.Clone();

var b = a.Clone<B>();
```

### DataReader `Map<T>`

> Note:  Property name comparisons exclude special characters and are not case-sensitive.
> If you're setup specific strategy, you can take a little performance improvement.

```cs
public class Row 
{
  // configure spectific key
  [MapFrom("pk")]
  public long Id { get; set; }
  
  // Implictly mapping to full_name, FullName, full-name, FULL_NAME or others cases
  public string FullName { get; set; }
  
  public DateTime UpadatedAt { get; set; }
  
  public DateTime CreatedAt { get; set; }
}

// Usage

while(reader.Next())
{
  yield return reader.Map<Row>();
}

```

## Road Map

- [] Research generatiion CIL(Common Intermediate Language) at Runtime
- [] Research reflection performance and optimization
