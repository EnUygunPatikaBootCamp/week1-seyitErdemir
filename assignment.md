### OOP (Object-Oriented Programming / Nesne Yönelimli Programlama ) nedir? Ne amaçlı kullanılır?

OOP gerçek hayattaki nesne ilişkisinin yazılım ortamındaki yaklaşımıdır.Veriler üzerinde işlem gerçekleştiren işlevler ile çalışmak yerine  hem veri hem işlevleri içeren nesneler üreterek çalışmayı hedefleriz.

Daha hızlı ve yürütülmesi kolay kodlar yazmamıza  , hata ayıklama ve yönlendirme süreçlerinde kolaylık sağlaması , daha kısa ve tekrara düşmeyen kodlar yazmamızı sağlar.  

class Fruit {
  public $name="deneme";
  function get_name() {
    return $this->name;
  }
}
$apple = new Fruit();
echo $apple->get_name();

<-------------------------------------------------------------------------------------------------->

### Polymorphism (Çok Biçimlilik) ne amaçlı kullanılır?

Kalıtım yapılan sınıfın  kalıtım yapan sınıftaki methodu tekrar oluşturup farklı görevi yapması için kullanılır. Tek bir eylemi farklı şekillerde gerçekleştrimek için kullanırız. 

class Animal {
  function animalSound() {
    echo "The animal makes a sound"
  }
}
class Pig extends Animal {
  function animalSound() {
    echo "The pig says: wee wee"
  }
}
class Dog extends Animal {
  function animalSound() {
    echo "The dog says: bow wow"
  }
}

<-------------------------------------------------------------------------------------------------->

### Bir metodun private, protected ya da public olması kavramlarını açıklayınız.
Public olarak bildirilmiş özelliklere ve yöntemlere her yerden erişilebilir. Private bildirimli özelliklere ve yöntemlere  sadece özelliğin tanımlandığı sınıfın içinden erişilebilir. Protected bildirimli özelliklere ve yöntemlere sadece tanımlandığı sınıfdan, ebeveyn sınıflardan ve miras alınarak erişilebilir.

class Sınıfım {
    public $genel = 'Genel';
    protected $korumalı = 'Korumalı';
    private $özel = 'Özel';

    function selamVer()  {
        echo $this->genel;
        echo $this->korumalı;
        echo $this->özel;
    }
}
$nesne = new Sınıfım();
echo $nesne->genel;    // Çalışır
echo $nesne->korumalı; // Ölümcül Hata
echo $nesne->özel;     // Ölümcül Hata
$nesne->selamVer();    // Genel, Korumalı ve Özel görüntüler

<-------------------------------------------------------------------------------------------------->

### Soyutlama (Abstraction) nedir?
Kaltım sürecinde tasarımımızda bulunması zorunlu olan gereçlerimizi tanımlamak için abstract metodlardan yararlanmaktayız. Yani kalıtımımızda bulunan abstract metodumuzda yazan gerekçelerimizi kullanmamız zorunludur. Daha sonrasında farklı interfaceler aracılığıyla tasarımımızı daha detaylı hale getirebiliriz. Bu yüzdendirki kalıtımda abstraction bir tanedir interfaceler ise birden çok tanımlanabilir.