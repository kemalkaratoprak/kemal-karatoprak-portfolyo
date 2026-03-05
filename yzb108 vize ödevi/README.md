1. Giriş
Bu rapor, soyut sınıflar (abstract classes) ve kalıtım (inheritance) kullanılarak Python programlama dili ile nesne yönelimli (OOP) bir araba modeli oluşturulmasını açıklamaktadır.

2. Sınıf Tasarımı
Temel Soyut Sınıf: Vehicle (Araç)
●	Korumalı (protected) nitelikler içerir: _brand, _model, _year.

●	Marka (brand) özelliğine erişim sağlayan bir @property metodu içerir.

●	show_info() adında soyut bir metot tanımlar. Bu metot alt sınıflarda uygulanır.

Türetilmiş Sınıf: Car (Araba)
●	Vehicle sınıfından türetilmiştir.

●	Ek özellikler içerir: fuel_type, kilometers, fuel_consumed.

●	Arabayı sürmek (drive), yakıt doldurmak (refuel) ve yakıt verimliliğini hesaplamak (fuel_efficiency) gibi işlevler sunar.

●	show_info() metodu ile araç bilgilerini ekrana yazdırır.


3. Simülasyon Örneği – Tesla Model 3
Aşağıda bir Car nesnesi oluşturularak, Tesla Model 3 aracının sürülmesi ve yakıt verimliliği simüle edilmiştir:
tesla = Car("Tesla", "Model 3", 2022, "Electric")
tesla.drive(150)
tesla.refuel(30)
tesla.show_info()
print(tesla.fuel_efficiency())



4. Çıktı

Tesla drove 150 km. Total: 150 km.  
Tesla refueled 30 liters. Total fuel: 30 L.  
Brand: Tesla  
Model: Model 3  
Year: 2022  
Fuel Type: Electric  
Kilometers: 150  
Fuel Consumed: 30 L  
Fuel efficiency: 5.00 km/l  


Bu çıktılar, sınıf yapılarının başarılı bir şekilde çalıştığını ve nesne yönelimli programlamanın gerçek dünya nesnelerini modellemek için nasıl kullanılabileceğini göstermektedir.

