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
static void yazdir(tree node)
{
    if (node == null) return;

    yazdir(node.left);
    Console.WriteLine(node.value);
    yazdir(node.right);
}
```

## Parametreler

- `node`: Ağaçtaki mevcut düğüm.

## İşleyiş
1. İlk olarak gönderilen ağaç null ise, null döndürülür.
2. Null değilse, sol tarafına gitmeye başlanır.
3. Null düğüme ulaşana kadar sola gitmeye devam edilir.
4. bu durumda ağacın en küçük elemanına ulaşmış olduk.
5. bu aşamada yazdırma işlemi başlayacak ve en küçük elemanı yazdırdıktan sonra sağ gidilir.
6. sağ düğümü varsa ona gidilir ve ardından en sola yine gidilmeye başlanır.
7. // anlatamadım ):
8. Kök düğümün sol tarafı tamamlandıktan sonra kök düğümün sağ tarafına gidilir ve aynı işlem tekrarlanır.



