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

## Avantaj

- Ağaçtaki elemanlar `küçükten büyüğe` doğru sıralanmış şekilde yazdırmayı sağlar.

## İşleyiş
1. İlk olarak gönderilen ağaç null ise, null döndürülür.
2. Null değilse, sola gitmeye başlanır.
3. Null düğüme ulaşana kadar sola gitmeye devam edilir.
4. Bu durumda `ağacın en küçük` elemanına ulaşılmış olur.
5. En küçük elemanı yazdırdıktan sonra sağ düğüm varsa ona gidilir ve tekrar en sola gidilir.
6. Null bir düğümle karşılaşıldığında durulur ve o düğümün değeri yazdırılır.
7. Düğümün değeri yazdırıldıktan sonra yine sağ düğümlerini kontrol edilir varsa bir defa sağ gidilir ve sola gidimeye başlanır, sağ düğüm yoksa bir önceki düğüme gidilir. 
8. Bu işlem kökün sol tarafını bitirdikten sonra kökün derğeri yazdırılır ardından kökün sağ tarafına geçilir.
9. Kökün sağ tarafına ilk gidildiğinde aynı işlem uygulanır; kökün sağ düğümünün en soluna gidilir ve değer yazdırılır.
10. Böylece aynı işlem devam edilir.

<div align="center">
    <h3>Binary Ağaç Elemanları In-Order Yazdırma Aşamaları</h3>
</div>

[![Yazdırma Adımları](https://github.com/yasir723/Agac-Elemanlari-Yazdirmak-Pre-Order-/assets/111686779/69b40cce-02df-45f7-8453-da0bc03731d7)](https://github.com/yasir723/Agac-Elemanlari-Yazdirmak-Pre-Order-/assets/111686779/69b40cce-02df-45f7-8453-da0bc03731d7)

## Not

- Ağaçtaki elemanlar `küçükten büyüğe` doğru sıralanmış şekilde yazdırdığımız gibi eğer `aşağıdaki metodu` gibi önce node.right ardından yazdırma komutu ve ondan sonra node.left yazsaydık bu durumda `büyükten küçüğe` doğru sıralanmış şekilde yazdırılacaktır.

```csharp
static void yazdir(tree node)
{
    if (node == null) return;

    yazdir(node.right);
    Console.WriteLine(node.value);
    yazdir(node.left);
}
```
