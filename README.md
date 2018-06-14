# C-Keywords


1.abstract keyword - Metod Abstrakt Ola Biler , Klass Abstract Ola Biler , Abstract Metodun Tetbiqi Yoxdur, Bunun Evezine Tetbiq Iwini Ondan Derive Olunmus Klasslar Yerine Yetirir. Derive Olunmus Sinfiler Ucun Temel Bir Wablon Create Etmek Isteyirikse Abstract Class Istifade Edirik.Qisa Olaraq Desek Compiler Seviyyesinde Bir Design Qaydasi Implement Edirik. Hansisa Klasi "Abstract" Klass Etmek ucun <<(abstract)>> - Keyvordundan Istifade Edirik.


         abstract class Test
        {
            public int _a;
            public abstract void A();
        }

        class Example1 : Test
        {
            public override void A()
            {
                Console.WriteLine("Salam Men A - yam");
                base._a++;
            }
        }

        class Example2 : Test
        {
            public override void A()
            {
                Console.WriteLine("Salam Men A2 - yem");
                base._a--;
            }
        }
        
        
        
         static void Main(string[] args)
        {
            Example1 example = new Example1();
            example.A();
            Console.WriteLine(example._a);


            Example2 example2 = new Example2();
            example2.A();
            Console.WriteLine(example2._a);

        }
        

Note: Eger Example1 ve Example2 Kimi  Derived Sinifler Yazmisinizsa Abstract Clasinin Icersisinde Olan Butun Abstract Metodlarini Bu Class - lar - da Override Etmek Lazimdir.


2.is <()> Program Yazarken Etdiyimiz Bir Cast Emeliyyatinda Tiple Bagli Hansisa Bir Nokte Nezerden Qacarsa Programda Tip Uygunsuzluqu Kimi Bir Error Cixir. Bele Bir Xeta Iwleme Aninda Progarmin Qirilmasina Getirib Cixarir. Is ve As Opeartorlari Bu Noktede Bize Type - lar Uzerinde Nezaret Etme Ozelliyi Temin Edir.  Ilk Once Bir Xetali Cast Emeliyyati Edek;

     class Humans
    {
        public string Ad { get; set; }
        public string  Soyad { get; set; }
    }
    
    
    static void Main(string[] args)
        {

           Object deyer = true;
           Humans human = (Humans)deyer;//burda bool tipinden Humans Tipine Cast Ede Bilmediyi Uucn Prgram Crash Olur.

        }
        
Bu Xetadan Yola Cixaraq <<(Is)>> Operatoruna Baxaq. Is Operatoru Control sonrasinda "Bool" - deyeri Donderir. Yuxardaki Numuneni Is ile Birde Yazaq.

     static void Main(string[] args)
        {

           Object deyer = true;  
           
           bool result = deyer is Humans; 
           
           cw(result)//boolean deyeri donderdiyi Ucun  netice "False" - Olacaq Cunki Tipler Eyni Deyil
        }    
        
Numunede "deyer" - Deyiweninin Tipi "Is" ile Kontrol Edilir.  Eyer Netice "true" - Olacaqsa Cast Emeliyyati Yerine Yetirilicekdir. Qisa Olaraq Desek Burada "Is" - ile Sadece Exception - un Qarwisini Aldiq ve Program Crash olmadi.  


3.as - Keywordu da "Is" - Kimi Iwleyir Ama Aralarindaki Ferq Odur ki  "Is" - Operaoru Kontrol Sonrasinda "Bool" - deyeri Donderdiyi Halda  "As" - Tipin referansini Donderir. Eyer Cast Eeliyyati unsuccess Olarsa Bu Zaman "Null" - Deyeri Donderilir.

4.base - C# - da Temel Sinifin Metodlarina ve Memberlerine Reach Elemek Ucun Derived Class-da "base" - keywordu Istifade Edirik

5.bool - keywordu Programda Heyata Kecirilen Emeliyatlar Gore "true ve false" - deyerleri Qaytarir

    byte num1 = 5;
    byte num2 = 10;
    Console.WriteLine(num1>num2);


6.break - C# - da Bir Dongu Icerisinde "break" - Ifadesi Istifade Olunarsa Dongu Derhal Sonlandirilir ve Dongunu Sonlanidigi Yer Ekrana Gosterilir. Hemcinin "switch ve Case " - Ifadesini Sonlandirmaq Ucunde Istifade Olunur.


7.byte - Icerisinde Tam Ededleri Saxlayan Data Tipidir  Max Deyer = 255   Min Deyer = 0;

8.case - C# - da "case" - Switch - in Bir Parcasidir.Bu keywordu  "switchdeki" - constant deyerleri Muqayise Etmek Ucun Istifade Edirik.( Case specifies a constant to be matched in the switch selection statement).

9.catch - C# -da Catch Istisnalari Ele Almaqimizi Temin Edir Hansisa Bir Xetani Program Crush Olmadan Bize Gosterir. Cox Hallarda Xetalarin Qarwisini Almaq Ucun Try-Catch istifade edilir

10.checked - C# - da expilict Conversion Edilende Boyuk Deyer Tipini Kicik Deyer Tipine Assign Edende(int to byte) Integer - in Olcusu Boyuk Oldugu Ucun Byte Cevirende Itki Baw Verir. biz Yazdiqimz Bu Conversion Kodumuzu  "checked" ifadesinin icerisinde Yazsaq , Bize Console Ekraninda OverFlow Istisnasini Gosterir ve Cast Emeliyyatini Yerine Yetirmir. For Example

    
                int a = 50000;
                byte b;
                b = (byte)a;
                Console.WriteLine(b);//80
            
Yuxardaki Numunede Ekran Goruntusu 80 Deyerini Bize Gosterecek Ama Data Itgisi Olduqunuda Nezere Alaq

                checked
            {
                int a = 50000;
                byte b;
                b = (byte)a;
                Console.WriteLine(b);
            }//System.OverflowException

Yuxardaki Numunede Ise Cast Emeliyyatin aICaze Vermedi ve Programi Crash Eledik.

10.class - Sinif Yaratmaq Ucun Istifade Olunan Keyword-dur

11.const - C# - da Teyin Etdiyimiz Bezi Deyiwenlerin Deyerlerinin Deyiwmemesini Isteye Bilerik. Bunu Temin Etmek Ucun "const" - keywordundan istifade edirik,ve Biz Bu deyiwenin Deyerini Deyiwe Bilmirik.

12.continue - C# - da Dongumuzde Mueyyen Wertler Altinda Her Hansisa Bir Step - in Ustunden Hoppnaib Kecmek Isteye Bileri.Bunun Ucun "continue" keywordunda istifade edirik  verdiyimiz werte gore Dongumuzde Hemin Stepi Hoppanib Kecir ve Iwine Davam Edir. Ekranda Hoppanib kecdiyimiz step-den bawqa butun step-ler gorunur.

13.decimal - Qeyri Tam Ededler Ucun C# - da iki Eded Data Tipi var "floating point" ve "decimal" , "floating point" Istifadesi Bezi Xirda Seflere Yol Acdiqi Ucun decimal Istifadesi Daha Yaxwidir.

14.default - C# - da Int Tipinde Bir Deyisen Teyin Edende Ona Deyer Vermesek Varsayilan Deyer Olaraq "0" - goturur   Stringler "empty" - goturur Objectler ise "null" - goturur. Bu Deyerler "default" keyword-a gore Teyin Edilirler

    int x = default(int);//0
    string x2 = default(string);//" "
    bool x3 = default(bool);//false
    
15.do - Bildiyimiz Do-While Dongusudu

16.double - C# - da Qeyri Tam Ededleri Saxlamaq Ucun Bir Data Tipi Daha "double" ---- 
MaxValue = 1.7976931348623157E+308;  
MinValue = -1.7976931348623157E+308;

17.else - Bildiyimiz Condiiton Movzusudu  Eger Hec bir Wert Odenmirse "else" - bloku Iwe Duwur


18.long - Icerisinde Tam Sayi Saxlayan Integer Tipinin Uzun Versiyasidi   MaxValue = 9223372036854775807;   MinValue = -9223372036854775808;


19.internal - Oz Lahiyesi Icerisinde Public  Ferqli Bir Lahiyeden / Colden Cagirilmak Istediyinde Private Xususiyyetlerini Dasiyir. I mean Eyni Assemly(dll) Uzerinde Istediyimiz Sekilde Istifade Ede Bilerik Ancaq Colden Ferqli Bir Lahiyeden Cagrila Bilmez.
       
20.namespace -  NET FrameWork - da Hazir Kitabxanalar ve ya Programcilarin Develop Eldiyi DLL - ler Olur. Bu Kitabxanalara ve Dll - lere Reach Elemek Ucun Namespace Adindan Istifade Etmeliyik. Bir NameSpace Iceiside Birden Cox Class Contain Eliye Biler. Eyni Namespace Icerisinde Olan Class - lar Bir Birlerine Reach Eliye Biler(Public Olduqlari Halda). Ferqli Namespacelerde OLan Classlari Use Elemek Ucun Namespacenin Adini Using Eliyirik. 
