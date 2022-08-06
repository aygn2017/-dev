#Odev 
Patika Dev Koleksiyonlarla(Collections) ilgili algoritma odevi
Görevler
Soru 1:
Klavyeden girilen 20 adet pozitif sayının asal ve asal olmayan olarak 2 ayrı listeye atın. (ArrayList sınıfını kullanara yazınız.)
Negatif ve numeric olmayan girişleri engelleyin.
Her bir dizinin elemanlarını büyükten küçüğe olacak şekilde ekrana yazdırın.
Her iki dizinin eleman sayısını ve ortalamasını ekrana yazdırın.
Soru 2:
Klavyeden girilen 20 adet sayının en büyük 3 tanesi ve en küçük 3 tanesi bulan, her iki grubun kendi içerisinde ortalamalarını alan ve bu ortalamaları ve ortalama toplamlarını console'a yazdıran programı yazınız. (Array sınıfını kullanarak yazınız.)
Soru 3:
Klavyeden girilen cümle içerisindeki sesli harfleri bir dizi içerisinde saklayan ve dizinin elemanlarını sıralayan programı yazınız.


1.soru : 

 static void Main(string[] args)
        {
            ArrayList list1 = new ArrayList();
            ArrayList list2 = new ArrayList();
            int toplam1 = 0;
            int toplam2 = 0;

            for (int i = 0; i < 20; i++)
            {
            
                System.Console.WriteLine(i+1 + ". sayıyı giriniz: ");
                int sayilar = Convert.ToInt32(Console.ReadLine());
                if (negatifMi(sayilar))
                {
                    int sayac = 0;
                    for (int k = 2; k < sayilar; k++)
                    {
                        if (sayilar % k == 0)
                        {
                            sayac++;
                        }

                    }
                    if (sayac == 0)
                    {
                        if(sayac==1){
                            list2.Add(sayilar);
                        }
                        else
                            list1.Add(sayilar);
                    }
                    else
                    {
                        list2.Add(sayilar);
                    }


                }
                else
                {
                    System.Console.WriteLine("Lütfen Pozitif ve Numeric Bir sayı Giriniz");
                }

            }

            list1.Sort();
            list1.Reverse();
            list2.Sort();
            list2.Reverse();


            System.Console.WriteLine("----------Asal Sayılar----------");
            foreach (int item in list1)
            {
                System.Console.WriteLine(item);
            }
            System.Console.WriteLine("----------Asal Olmayan Sayılar----------");
            
            foreach (var item in list2)
            {
                System.Console.WriteLine(item);
            }


            foreach (int item in list1)
            {
                toplam1=toplam1+item;
                    
            }
            System.Console.WriteLine("Asal Sayıların Ortalaması=  " + toplam1/list1.Count+ "  Dizideki Eleman Sayısı= "+list1.Count );
            
            foreach (int item in list2)
            {
                toplam2=toplam2+item;
                    
            }
             System.Console.WriteLine("Asal Olmayan Sayıların Ortalaması=  " + toplam2/list2.Count+ "  Dizideki Eleman Sayısı= " + list2.Count );

        }


         private static bool negatifMi(int s)
        {
            bool sonuc = true;
            if (s < 0)
            {
                sonuc = false;
            }

            return sonuc;

        }
    }
}


2.soru 
  static void Main(string[] args)
        {
            ArrayList sayilar = new ArrayList();
            // int[] sayilar= new int[20];
            ArrayList enKucukUc = new ArrayList();
            ArrayList enBuyukUc = new ArrayList();
            int toplam1 = 0;
            int toplam2 = 0;

            for(int i = 1; i <= 20; i++){
                System.Console.Write(i + ". sayıyı giriniz : ");
                int sayi = Convert.ToInt32(Console.ReadLine());
                sayilar.Add(sayi);
                System.Console.WriteLine(sayilar[i-1]);
            }
            


            sayilar.Sort();
            
            
            int sayac = 1;
            foreach (var item in sayilar)
            {
                if( sayac == 1 || sayac == 2 || sayac == 3){
                    enKucukUc.Add(item);
                    
                }
                else if(sayac == 18 || sayac == 19 || sayac == 20){
                    enBuyukUc.Add(item);
                }
                sayac++;

            } 
                
               
            

            foreach (int item in enKucukUc)
            {
                toplam1 += Convert.ToInt32(item);
                System.Console.WriteLine(item);
            }
            foreach (int item in enBuyukUc)
            {
                toplam2 += Convert.ToInt32(item);
                System.Console.WriteLine(item);

            }
            
            System.Console.WriteLine("ilk üç sayının ortalaması : " + (toplam1/3));
            System.Console.WriteLine("son üç sayının ortalaması : " + (toplam2/3));
            System.Console.WriteLine("ortalamalar toplamı : " + ((toplam1/3) + (toplam2/3)));

        }
    }
}

3.soru : 

        static void Main(string[] args)
        {
            ArrayList sentence = new ArrayList();
            System.Console.WriteLine("Lütfen bir cümle giriniz: ");
            string metin = Console.ReadLine();
            string sesli = "aeıioöuüAEIİOÖUÜ";
            int sayac = 0;
            for (int i = 0; i<metin.Length; i++){
                if(sesli.Contains(metin[i])){
                    sayac++;
                    sentence.Add(metin[i]);
                }
            }

            System.Console.WriteLine("Kelime içerisinde toplam" + sayac + "tane sesli harf far");
            foreach (var item in sentence)
            {
                System.Console.WriteLine(item);
            }

        }
    }
}
