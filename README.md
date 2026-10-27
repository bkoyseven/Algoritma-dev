# Algoritma-dev
c#'da tanımlanan her değişken sadece tanımlandığı blok içinde geçerli, blok dışında ise tanımsızdır. Örnek programlar aracılığı ile bu durumu açıklanacak
1. Blok içinde tanımlanan değişken
   using System;

class Program
{
    static void Main()
    {
        if (true)
        {
            int sayi = 10;
            Console.WriteLine(sayi); // Çalışır
        }

        Console.WriteLine(sayi); // HATA!
    }
}

sayi değişkeni if bloğunun içinde tanımlanmıştır. Bu nedenle if bloğu içerisinde kullanılabilir. Ancak if bloğunun dışına çıkıldığında değişken artık tanımlı değildir ve program hata verir.

2. Değişken dış blokta, kullanım iç blokta
using System;

class Program
{
    static void Main()
    {
        int sayi = 20;

        if (true)
        {
            Console.WriteLine(sayi); // Çalışır
        }
    }
}
3. for döngüsünde değişken kapsamı
using System;

class Program
{
    static void Main()
    {
        int i;

        for (i = 0; i < 5; i++)
        {
            Console.WriteLine(i);
        }

        Console.WriteLine(i); // Çalışır
    }
}
4. İç içe bloklarda değişken kapsamı
using System;

class Program
{
    static void Main()
    {
        int a = 10;

        {
            int b = 20;

            Console.WriteLine(a); // Çalışır
            Console.WriteLine(b); // Çalışır
        }

        Console.WriteLine(a); // Çalışır
        Console.WriteLine(b); // HATA!
    }
}
