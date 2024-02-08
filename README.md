# Ağaç Elemanları Yazdırmak (In-Order)
`In-Order gezinme algoritması` kullanarak her bir düğümün değerini önce sol alt ağaç, ardından kendisi ve en sonunda sağ alt ağaç olarak sırayla yazdırır. Bu yazdırma sonucunda elemanlar küçükten büyüğe doğru sıralanmış olarak görünecektir.


Bu C# sınıfı, binary ağaç veri yapısını oluşturmak için kullanılır
## `tree` Sınıfı

```csharp
class tree
{
    public int value;
    public tree right;
    public tree left;
}
```

### Özellikler

- `value`: Düğümün değerini temsil eder.
- `right`: Düğüme bağlı olan sağ alt düğümü belirtir.
- `left`: Düğüme bağlı olan sol alt düğümü belirtir.

## `yazdır` Metodu
```csharp
static void yazdir(tree node) // biz genelde pre order olarak yazdırıyoruz
{
    if (node == null) return;

    Console.WriteLine(node.value);
    yazdir(node.left);
    yazdir(node.right);
}
```

## Parametreler

- `node`: Ağaçtaki mevcut düğüm.
