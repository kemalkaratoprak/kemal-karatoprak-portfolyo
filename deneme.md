Kemal, projenin başından sonuna kadar attığımız her adımı, senin öğrenme sürecine uygun şekilde kronolojik olarak tek tek listeledim. Bu liste, bir yazılım projesinin "fikir" aşamasından "canlı yayın" aşamasına nasıl geldiğinin tam bir dökümüdür.

### 📁 Bölüm 1: Proje Kurulumu ve Mimari Tasarım

1.  .NET 9.0 SDK kurulumunun doğrulanması.
2.  `dotnet new mvc` komutuyla temel klasör yapısının oluşturulması.
3.  `Program.cs` dosyasında MVC servislerinin tanımlanması.
4.  `wwwroot` klasörünün statik dosyalar (CSS, JS, Resim) için yapılandırılması.
5.  Ana sayfa tasarımı için `HomeController` oluşturulması.
6.  `Index.cshtml` dosyasının Razor motoruna uygun hale getirilmesi.
7.  Bootstrap kütüphanesinin projeye dahil edilmesi.
8.  FontAwesome veya Bootstrap Icons entegrasyonu.
9.  Projenin yerel makinede (Localhost) ilk kez ayağa kaldırılması.
10. `Models` klasörünün veri yapıları için hazırlanması.

### 🗄️ Bölüm 2: Veritabanı ve Entity Framework Core

11. `Microsoft.EntityFrameworkCore` paketlerinin yüklenmesi.
12. `Microsoft.EntityFrameworkCore.SqlServer` paketinin projeye eklenmesi.
13. `Project.cs` modelinin (Id, Title, Description, ImageUrl) yazılması.
14. `AppDbContext.cs` sınıfının oluşturulması.
15. `DbSet<Project>` tanımlamasıyla projeler tablosunun modellenmesi.
16. Somee üzerinden ücretsiz MS SQL Server veritabanı oluşturulması.
17. Somee Connection String (Bağlantı Cümlesi) bilgisinin alınması.
18. `appsettings.json` içine bağlantı cümlesinin güvenli şekilde yazılması.
19. `Program.cs` içinde `AddDbContext` servisinin kaydedilmesi.
20. `dotnet ef migrations add InitialCreate` ile ilk veritabanı taslağının oluşturulması.
21. `dotnet ef database update` ile tabloların Somee sunucusuna basılması.
22. SQL Server Management Studio (SSMS) ile Somee bağlantısının test edilmesi.
23. `Projects` tablosuna elle ilk örnek verilerin girilmesi.

### 🖥️ Bölüm 3: Backend Mantığı ve CRUD İşlemleri

24. `HomeController` içinde `AppDbContext` enjeksiyonu (Dependency Injection).
25. `Index` metodunda `_context.Projects.ToList()` ile verilerin çekilmesi.
26. Çekilen verilerin `View(projects)` ile arayüze gönderilmesi.
27. `Index.cshtml` içinde `@foreach` döngüsüyle projelerin listelenmesi.
28. `AdminController` oluşturularak yönetim panelinin temellerinin atılması.
29. `Create` (Ekleme) sayfası için HTTP GET metodunun yazılması.
30. `Create` sayfası için HTTP POST metodunun yazılması.
31. Formdan gelen verilerin `_context.Projects.Add()` ile kaydedilmesi.
32. `Delete` (Silme) metodunun ID parametresiyle yapılandırılması.
33. `Edit` (Güncelleme) sayfasının mevcut verileri getirecek şekilde kodlanması.
34. Güncelleme sonrası `_context.Projects.Update()` metodunun çağrılması.
35. `_context.SaveChanges()` ile tüm değişikliklerin SQL'e yansıtılması.

### 🌐 Bölüm 4: Deployment (Render ve GitHub)

36. GitHub üzerinde yeni bir Repository oluşturulması.
37. `.gitignore` dosyasının gereksiz dosyaları engellemek için eklenmesi.
38. `git init` ile yerel deponun başlatılması.
39. `git add .` ve `git commit` ile kodların dondurulması.
40. `git push origin main` ile kodların buluta gönderilmesi.
41. [https://www.google.com/search?q=Render.com](https://www.google.com/search?q=Render.com) üzerinde "Web Service" oluşturulması.
42. GitHub hesabının Render'a bağlanması.
43. Build Command olarak `dotnet publish` ayarının yapılması.
44. Start Command olarak projenin `.dll` dosyasının tanımlanması.
45. Render Environment Variables (Çevre Değişkenleri) ayarlarının yapılması.
46. İlk "Deploy" işleminin başlatılması ve izlenmesi.

### 📧 Bölüm 5: İletişim Formu ve SMTP (Mail) Sistemi

47. `ContactMessage.cs` modelinin (Name, Email, Subject, Message) oluşturulması.
48. Gmail üzerinde "İki Adımlı Doğrulama"nın açılması.
49. Google "Uygulama Şifreleri" kısmından 16 haneli özel kodun alınması.
50. `System.Net.Mail` kütüphanesinin Controller'a dahil edilmesi.
51. `SendMessage` metodunun asenkron (`async Task`) olarak tanımlanması.
52. `SmtpClient` nesnesinin oluşturulması.
53. Host olarak `smtp.gmail.com` tanımlanması.
54. Port numarasının `587` olarak ayarlanması.
55. `EnableSsl = true` güvenli bağlantı ayarının yapılması.
56. `NetworkCredential` içine Gmail adresi ve 16 haneli kodun yazılması.
57. `MailMessage` nesnesiyle gönderici, alıcı ve konu başlıklarının belirlenmesi.
58. Mesaj gövdesinin HTML formatında (`IsBodyHtml = true`) tasarlanması.
59. `await sc.SendMailAsync(mail)` ile mailin uçurulması.
60. `TempData` kullanarak başarı mesajının tanımlanması.

### 🩹 Bölüm 6: Hata Ayıklama (Debugging) ve Onarım

61. Render üzerinde alınan "Exit Code 1" hatasının analiz edilmesi.
62. `AppDbContext` içinde `ContactMessages` tablosunun eksik olduğunun fark edilmesi.
63. `public DbSet<ContactMessage> ContactMessages { get; set; }` satırının eklenmesi.
64. `ContactMessage` modelinde "Primary Key" (ID) eksikliğinin tespit edilmesi.
65. `public int Id { get; set; }` mülkiyetinin modele eklenmesi.
66. `ContactMessage.cs` içindeki mükerrer (duplicate) sınıf tanımlarının silinmesi.
67. Namespace hatalarının (`PortfolyoProjesi.Models`) düzeltilmesi.
68. Yerel veritabanında yeni migration oluşturulması.
69. Somee sunucusunda "Instance failure" bağlantı hatasının görülmesi.
70. Somee T-SQL panelinin açılması.
71. Manuel `CREATE TABLE ContactMessages` sorgusunun yazılması.
72. Tablo sütunlarının (Id, Name, Email...) modele uygun şekilde oluşturulması.
73. SQL sorgusunun çalıştırılarak tablonun fiziksel olarak var edilmesinden emin olunması.

### 🎨 Bölüm 7: Frontend Finalizasyonu ve UX

74. `Index.cshtml` içinde iletişim formu tasarımına başlanması.
75. `<form>` etiketine `asp-action="SendMessage"` eklenmesi.
76. Form metodunun `method="post"` olarak belirlenmesi.
77. Input alanlarına `name="Name"`, `name="Email"` niteliklerinin eklenmesi.
78. C\# Model Binding mekanizmasıyla HTML formunun eşleştirilmesi.
79. Formdaki tasarım hatalarının (eksik div kapanışları) temizlenmesi.
80. Sayfanın alt kısmındaki "Bana Ulaşın" bölümünün `bg-dark` ile karartılması.
81. `Index.cshtml` içindeki `@if (TempData["MessageSent"] != null)` kontrolünün eklenmesi.
82. Başarı mesajının yeşil bir `alert` kutusuyla gösterilmesi.
83. Profil fotoğrafının `rounded-circle` ile yuvarlatılması.
84. Fotoğraf etrafına `border-info` ile mavi halka eklenmesi.
85. "Hakkımda" yazılarının `text-white-50` ile okunabilir kılınması.
86. "Hero Section" (Giriş) kısmına `linear-gradient` arka plan verilmesi.
87. Proje kartlarının `hover` efektlerinin düzenlenmesi.
88. Sayfa içi linklerin (`#projects`, `#contact`) çalışır hale getirilmesi.

### 📄 Bölüm 8: CV ve Varlık Yönetimi (Assets)

89. `wwwroot` içine `files` klasörünün açılması.
90. PDF formatındaki CV dosyasının klasöre yüklenmesi.
91. HTML içinde `<a href="~/files/..." download>` linkinin oluşturulması.
92. CV indir butonunun "Ben Kimim?" yanına estetik şekilde yerleştirilmesi.
93. Teknik yetkinlikler (Python, C\#, SQL) kısmının kartlar halinde düzenlenmesi.
94. Bi-code-slash ve bi-stack ikonlarının yetkinliklere eklenmesi.
95. Footer (alt bilgi) kısmının telif yazısıyla tamamlanması.

### 🏁 Bölüm 9: Final Push ve Canlı Testler

96. Tüm dosyaların kaydedilmesi.
97. `dotnet build` ile yerelde sıfır hata kontrolü.
98. `git add .` ile son değişikliklerin sahneye alınması.
99. `git commit -m "Final version with mail and CV"` kaydı.
100. GitHub'a son itme (push) işleminin yapılması.
101. Render panelinden "Deploying" sürecinin takip edilmesi.
102. Log ekranında "Server started" yazısının görülmesi.
103. Sitenin URL'sine ([https://www.google.com/search?q=onrender.com](https://www.google.com/search?q=onrender.com)) tarayıcıdan girilmesi.
104. İletişim formunun test verileriyle doldurulması.
105. "Gönder" butonuna basılması ve yönlendirmenin izlenmesi.
106. Somee üzerinden mesajın veritabanına düşüp düşmediğinin kontrolü.
107. Gmail kutusuna gelen bildirim mailinin açılması.
108. Projenin "Bitti" olarak mühürlenmesi ve 2026 yılı portfolyosuna eklenmesi.

