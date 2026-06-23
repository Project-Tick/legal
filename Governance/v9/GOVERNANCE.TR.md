# Project Tick Yönetişim v9, 23 Haziran 2026

<!--

Copyright (C) 2026 Project Tick

İşbu Project Tick Yönetim Belgesi, Project Tick'in resmi bir yönetişim belgesidir. Orijinal, değiştirilmemiş haliyle serbestçe dağıtılabilir. Bu belgenin değiştirilmesi resmi kullanım için izin verilmez. Yalnızca Project Tick değiştirilmiş sürümler yayınlayabilir; bunlar yeni bir sürüm tanımlayıcısı altında yayınlanacak ve buna göre arşivlenecektir. Üçüncü taraf değişiklikleri, resmi bir Project Tick belgesi olarak sunulmamalı, dağıtılmamalı veya referans gösterilmemelidir. Bu gibi durumlarda, belge yeniden adlandırılmalı ve Project Tick adına, markasına ve ticari markalarına yapılan tüm referanslar karışıklığı önlemek için kaldırılmalı veya açıkça ayırt edilmelidir.

-->

Project Tick'e hoş geldiniz!

Bu belge, Project Tick ekosistemini, depo yönetim yöntemlerini ve yönetişim yapısını ele almaktadır. Bilmenizi isteriz ki Project Tick, Umbrella bir projedir ve dışarıdan proje kabulüne tamamen açıktır. Yani, lütfen projelerinizi [bize][1] kaydedin! Project Tick, altyapı projesinin yanı sıra, tamamen açık kaynak projeler geliştirmeye yönelik bir gruptur. Bağımlılığı yoktur.

## Yönetim

Project Tick'in CI/CD gereksinimleri GitHub Actions ve GitLab CI aracılığıyla görüntülenebilir; NameSpace VE örnek (instance), GitLab™ Self-Managed üzerinden [git.projecttick.org/project-tick/][2] adresinden erişilebilir. NameSpace'e girdiğinizde, süreci özetleyen bir README dosyasıyla karşılaşacaksınız. Burası GitHub'dan farklı bir dünyadır. Unutmayın, Pull Request olmadan bile, deponuzdaki haklarınızı kolayca kullanabilir ve GitLab üzerinden bir Merge Request (MR) açabilirsiniz. Tek yapmanız gereken, bir commit gönderdikten hemen sonra (taslak olsa bile) bir MR açmaktır. Bu, commit'inizi CI ile her açıdan test etmenizi sağlar. Kısacası, biz her zaman özgürdük. Ama artık daha özgürüz ve iş akışlarımız artık depodan bağımsızdır. Bu sayede güvenliğimizde en üst seviyededir. Her alt projenin kendi deposu vardır. Hiyerarşi, GitLab'ın Subgroup özelliğiyle daha kolay yönetilir. Hiyerarşiyi hem burada hem de namespace giriş sayfasında anlayabileceksiniz. GitLab, bize güvenlik denetimlerini, iç içe geçmiş yapıyı tek bir üst taraftan yönetmeyi, herhangi bir proje veya subgroup'a doğrudan logo ve pathten bağımsız isim vermeyi sağlayabilen bir yapıdır. Bu nedenle GitLab'ı her zaman destekliyoruz ve GitLab'ın tamamen yanındayız. Project Tick'e [Help Desk][3] ile ulaşabilirsiniz.

### Merge Request Modeli

Yukarıda belirtildiği gibi, bir MR gönderirsiniz. O alandaki yetkililer değiştirdiğiniz dosyaları inceler. Eğer uygun görürse onay basar. Ancak uygun görünmezse o zaman itiraz etme hakkına her zaman sahiptir. Unutmayın, biz burada gönüllü çalışıyoruz ve bağış bile almıyoruz. Lütfen zaman tutarsızlıklarına ve sarkmalara tolerans gösterin. Çünkü Açık Kaynağın ruhu budur. Asenkron şekilde çalışıyoruz. Bakımcının isteklerini yerine getirdikten sonra veya hali hazırda kodunuz iyiyse ve pipeline başarılı sonuçlanıyorsa; varsa merge train, yoksa direkt merge ile commitleriniz tek bir commite bastırılır ve üzerine birde merge commit eklenerek ana dala dahil edilir. Eğer ChangeLog'da sizde görünmek istiyorsanız Release Model ve Changelog Model'e bakabilirsiniz.

### Maintainer (Bakımcı) modeli

Maintainer'lar, kök dizindeki CODEOWNERS'ta yer alan proje klasörünü sürdürmekten sorumludur. Maintainer nasıl olunur? Project Tick standartlarına göre proje klasörünüzü nasıl yönetip geliştireceğinizi merak ediyorsanız, modelimiz oldukça basittir. Uzun vadeli katkıda bulunursunuz ve uygun görülürse, adınız bu klasördeki gerekli dosyalara atanır ve böylece bir yönetici olursunuz. Eğer ben bu kadar uğraşamam işim gücüm var niyetindeyseniz, sizde bir proje geliştirin ve Project Tick'e kaydolun. Sevgili Maintainer'lar, Davranış Kuralları'na (Code of Conduct) uygun olarak katkıda bulunanlara iyi ve saygılı davranmanızı bekliyoruz. Lütfen bunu yapmak için elinizden geleni yapın. GitLab ile artık daha da fazla özgürlüğe sahipsiniz. İşlerinizi rahatça ve açıkça yürütebilirsiniz. Sonuçta, Github ellerimizi tamamen bağlıyor. LLM'lere kodlarımızı teslim ediyor. Her ne kadar LLM'e sıcak baksakta kodumuz bizde kalmalıdır. Software Freedom Conservancy'nin dediği gibi: Github'dan Vazgeçin! (Give Up Github!). GitHub insani değildir. Sadece bizi kendisine inatla bağlar ve buna devam eder.

### Depo (Repository) Modeli

Depolarımız herhangi bir platforma sürekli ve aktif olarak klonlanmaz. Ancak, CI/CD kontrolleri için GitHub'ın Actions'ını ve Foreman sistemimizi kullanıyoruz. Foreman sistemimizle, GitLab'da oluşturulan Merge Request'leri kolayca test edebiliriz. Bunu yaparken, "secrets" (gizli bilgiler) dışında iş akışlarını mümkün olduğunca depodan bağımsız hale getirdik. MeshMC, MNV ve Json++ gibi tonlarca proje artık Foreman sayesinde test edilebiliyor. Tabii ki Flathub'a da teşekkür etmeliyiz; onların "vorarbeiter" projesinden ilham aldık. En başta forkladık. sonra Ruby on Rails ile Python'un yavaşlığına karşı tekrar yazdık, bu yüzden onlara, bize bu ilhamı verdiği için teşekkür ederiz. TL;DR: git.projecttick.org'a gidin, bir hesap oluşturun, depo(lar)ı forklayın, commit atın, bir merge request açın, CI/CD çalışsın, başarılı olduğundan emin olun, biz kontrol edip merge edeceğiz. Bu kadar basit.

### Karar Verme Modeli

Karar verme mekanizması tamamen en yüksek rütbeli kişi olan [Mehmet Samet Duman][4]'ın kontrolündedir. Maintainer'lar tarafından onaylanan Merge Request'leri inceler ve merge eder. Bir maintainer veto yetkisini kullanır ve bu Mehmet Samet Duman'ın onayından geçmezse, PR koşulsuz olarak kapatılır. Ancak, bunun adil olmadığını düşünüyorsanız, [ISSUE] etiketiyle <projecttick@projecttick.org> adresine bir şikayet gönderebilirsiniz. Tabii ki, bir maintainer her zaman veto yetkisini kullanma hakkına sahip değildir, ancak bu onu asla kullanamayacağı anlamına gelmez.

### Merge Request Kabul Modeli

MR'larınız CI/CD aracılığıyla titiz testlerden geçer. Ardından, ilgili alanın maintainer'ı yamayı inceler ve yama mantıklıysa ve kötü kod içermiyorsa, onaylar ve mr merge edilir. Aslında oldukça basit. Maintainer'lar yamalarda düzeltmeler talep edebilir ve eğer talebi onaylar ve gerekli değişiklikleri yaparsanız, onaylanma şansınız artar. Tersine, sağlam bir neden olmadan reddederseniz, yöneticinin veto yetkisi vardır. Kötü kod, daha hızlı yapılabilecek şeyleri kolaylaştırmak için aşırı çaba harcamak demektir. Daha görünür olmak veya Gitblame'de hava atmak için kod tabanlarınızı şişirmeyin. Örneğin, bir alanda birden fazla yönetici varsa, bir klasör ve bir üst düzey yönetici aynı projede olabilir; +1 veya -1 oylarıyla bir oylama yapılır ve en çok oyu alan kazanır. Örneğin, MNV projesindeki testlerde bir değişiklik yaptınız ve bir Merge Request (MR) gönderdiniz. MR maintainer'lar tarafından incelenir ve bir maintainer bir değişiklik talep eder ve bir diğeri kabul ederse, tüm depo maintainer'ları MR üzerinde oy kullanmak için çağrılır. Ancak, her maintainer oy kullanmama hakkını saklı tutar. Eşitlik durumunda, nihai karar BDFL tarafından verilir.

### Commit ve Sign-off (İmza) Modeli

Commit'ler DCO standardına göre yapılır, yani Signed-off-by ile imzalanır. DCO kullanılmazsa, Foreman bir hata verir ve bu hata düzeltilmezse, mr reddedilir. Lütfen commit'lerinizde yaptığınız işlemleri Header (Başlık), Body (Gövde) ve Footer (Altbilgi) bölümlerini kullanarak ayrıntılı olarak açıklayın. Conventional commits standardına yaklaşmaya çalışıyoruz. Lütfen commit'lerinizi buna göre uyarlamaya çalışın.

### Pasif Maintainer'lar Modeli

Bir maintainer müsait değilse, pozisyonu boşaltılacaktır. Maintainer'lar, görevinizden ayrılıyorsanız, yorgunsanız veya tatile çıkıyorsanız lütfen bize bildirin. Bir maintainer, geçerli bir nedeni veya sağlık sorunu yoksa en fazla 75 gün çevrimdışı kalabilir. Bir maintainer istifa eder veya görevden alınırsa, BDFL maintainer'ın yerine birini atayacaktır.

### Hata (Bug) Kontrol Modeli

Hata raporlarınız [burada][5] veya Proje depolarında alınacaktır. Geliştirmeyle ilgili herhangi bir sorunuz veya sorununuz varsa, [GitLab Work Items][5] aracılığıyla bizimle iletişime geçebilirsiniz. Hata raporlarınız artık burada ele alınacaktır.

### Project Tick SSO Modeli

Project Tick SSO, Keycloak altyapısını kullanır ve projecttick.org veya projecttick.net üzerindeki tüm işlemlerinizi yönetmenize yardımcı olur. 4 OAuth mekanizması hazırladık; Github, GitLab SaaS, Microsoft ve Google. Bu altyapılarla veya e-posta yoluyla bir hesap oluşturabilirsiniz. Web sitemiz artık kendi formu yerine bir SSO altyapısına sahip. Bu, sizi hesap karışıklığından kurtaracak, merak etmeyin. Hadi, [Buradan][6] bir hesap oluşturun. Hesabınızı oradan yönetebilirsiniz.

### Sürüm (Release) ve Versiyonlama Modeli

Versiyonlama modelimizde, her projenin kendi sürümü vardır ve bir proje güncellendiğinde, deposunda bir etiket oluşturulur. Format vX.Y.Z-suffix şeklindedir. Örneğin, MNV sürüm 10.0.4 yayınlandığında, bir etiket oluşturulur. Bu model, kodu bozmadan sürekli güncelleyerek süreklilik yaratır; eğer bununla ilgili sorun yaşıyorsanız, yayınladığımız en son LTS anlık görüntüsünü (snapshot) kullanabilirsiniz. Veya bir hata bulursanız, [buradan][5] veya Proje Depolarından bildirebilirsiniz. Beta sürümlerimiz artık mevcut; ancak beta sürümlerimiz binary (çalıştırılabilir dosya) yerine yalnızca kaynak kodu sağlar.

### Güvenlik Modeli

#### Nasıl raporlanır

Bir güvenlik açığı keşfederseniz, lütfen e-posta yoluyla bildirin:

- [`projecttick@projecttick.org`][7]

#### Neler dahil edilmeli

Bir rapor gönderirken, lütfen şunları dahil edin:

- Sorunu yeniden oluşturma adımları
- Beklenen ve gerçekleşen davranış
- Etkilenen sürümler
- Varsa loglar veya çökme raporları

### Lisanslama ve REUSE Uyumluluğu Modeli

SPDX'e büyük önem veriyoruz. REUSE sistemini hem Bootstrap betiklerimizin lefthook'unda aktif olarak tanımlıyor hem de CI/CD ile tam taramalar yapıyoruz. Şu anda REUSE lint ile ilgili bir sorun yok, ancak oluşturduğunuz herhangi bir yeni dosyanın SPDX-FileCopyrightText, SPDX-FileContributor ve SPDX-License-Identifier içermesini istiyoruz çünkü, başta belirtildiği gibi, SPDX lisans tanımlayıcısının en önemli bileşenlerinden biridir ve birçok dağıtım şu anda kaynak kodlarında SPDX başlıklarının varlığına öncelik vermektedir.

### Yapay Zeka (AI) Kullanım Modeli

Endişelenmeyin! AI kullanmanızı kıskanmıyoruz, ancak bunu artık destekliyoruz da, karşı değiliz. AI kullanın, ama sınırlarını bilin.

- AI asla, asla sizin onayınız haricinde `Signed-off-by` etiketini kullanmamalıdır.
- AI kodunu incelemeden ve gerekli ayarlamaları yapmadan göndermeyin.
- AI'yı bağlamsal olarak uygun ve iyi yazılmış istemlerle (prompt) yönetin. Örneğin, bir istem ortalama 150 kelime uzunluğunda olabilir ama ayrıntılı mantık içermelidir. Aksi takdirde, AI veya LLM'ler bağlamınıza uymayacak ve saçmalayacaktır. - Bir bellek bankası (memory bank) sistemi kullanın, ancak bu bellek bankalarını asla bir depoya koymayın. Gerekirse, geçici olarak `.gitignore`'a ekleyin ve Asistan bunları göremediği için sinirlenirse, ona nazikçe açıklayın.

### Doğruluk Kaynağı (Source of Truth) Modeli

Resmi Project Tick grubuna [buradan][2] erişilebilir. Unutmayın, GitHub ile hiçbir bağlantımız yok (CI/CD hariç). Ancak, bu koşullar sağlandığında – yani bağımsız CI/CD makinelerimiz olduğunda – tam bağımsızlık sağlanacak ve bu sorun bir dereceye kadar çözülecektir. Sizi düşünüyoruz ve buna göre hareket edeceğimizden emin olabilirsiniz. Foreman sayesinde Merge Request'lerdeki CI/CD sorununu çözebiliyoruz. Artık hepimiz tek bir yerdeyiz. Ayrıca, son zamanlarda neden olduğu sinir bozucu sorunlar nedeniyle CI/CD hariç GitHub'ı tamamen terk ediyoruz. PR'larınızı MR olarak, [ve Issue'larınızı GitLab'da Work Items olarak][5] açabilirsiniz.

### Etiketleme (Labeling) Modeli

Etiketleme modelimiz karmaşık olmasın diye tasarlanmıştır. Olabildiğince her etiketimizi scoped ve önünde numara varken kullanmaya çalışıyoruz. Labellarımız belli bir düzene sahiptir. Bahsetmemiz gerekirse,

```text
1.os::
2.type::
3.area::
4.with::
5.ci::
6.topic::
7.workflow::
8.has::
9.needs::
10.severity::
11.priority::
```

Yukarıda gördüğünüz yapı hakimdir. 

### Foreman

Foreman, geliştirici dostu bir platformdur. Bir GitHub reposundaki workflowları çalıştırabilen, logları workflowlardan çekip saklayabilen, durumu MR'a pipeline status, external status check yazabilen, release süreçlerini yönetebilen bir dev monolittir. Kendisini bir token ile önce kullanıcıya sonra grup, proje veya sistem hook'u olarak bağlanması ile çalışır. Kendisi pipeline yazabilmekte, "bot, help" ile komutları görüntüleyebilme, CLA imzalayabilme, bağımlılık güncelleyebilme gibi özelliklere sahiptir. Aynı zamanda içinde bir website ve dashboard vardır. Kendisi hem bizim release süreçlerimizide güvenle yönetebilmektedir. Zamanı geldiğinde hem beta hemde stabil tag atabilmektedir.

### Changelog Modeli

Changeloglar commitlerde belirttiğiniz trailer'lar ile üretilir.

### Release Modeli

Project Tick'teki release modeli apaçık bellidir. Her ayın 3. çarşambası bir stabil tag, her hafta ise bir beta tag atılmaktadır. Her tag sonrasında release çıkışı her ayın 3. perşembesidir. Ancak paket yöneticilerine yayılması Her ayın 3. pazarına kadar bulabilmektedir. taglarımız vX.Y.Z olarak atılmaktadır.

### Alt Proje Sınırları

Her proje kendi kararlarını verir. Unutmayınız ki, biz Polyrepo yapısındayız. Ancak, klasör maintainer'ı ile proje maintainer'ı arasında farklar vardır. Proje Maintainer'ı:

```text
Project Tick HQ
├── Community (ID: 17)
│   ├── Community Lab (ID: 128)
│   ├── Community Projects (ID: 127)
│   ├── Contributable Forks (ID: 129)
│   │   └── Project Tick (ID: 130)
│   │       └── Projects (ID: 131)
│   │           └── MeshMC [meshmc]
│   └── Onboarding [onboarding]
├── DevOps (ID: 19)
├── DevSecOps (ID: 20)
├── Developers (ID: 21)
│   └── MeshMC (ID: 40)
│       └── Plugins (ID: 96)
│           ├── All GA Plugins (ID: 107)
│           └── Staging (ID: 108)
│               └── All Non GA Plugins (ID: 112)
├── GitOps (ID: 22)
├── Governance (ID: 23)
│   └── Governance Document [governancedoc]
├── Infra (ID: 25)
│   ├── K8s (ID: 50)
│   │   └── Configs [configs]
│   ├── Vendored (ID: 51)
│   │   ├── forgejo (ID: 98)
│   │   │   └── forgejo [forgejo]
│   │   └── go-gitea (ID: 99)
│   │       └── gitea [gitea]
│   ├── Foreman [foreman]
│   ├── Gitea [gitea]
│   ├── ForgeJo [forgejo]
│   ├── Foreman 2.0 [foreman-2.0]
│   ├── Foreman 1.0 - Python [foreman-1.0]
│   ├── Actions Images [actions-images]
│   ├── Merge Action [merge-action]
│   └── GitHub Actions [github-actions]
├── Initiative (ID: 119)
│   └── Systematic Engineering (ID: 120)
│       └── Conditional Systems (ID: 121)
│           └── Lab (ID: 122)
│               └── Forks (ID: 123)
│                   └── Project Tick (ID: 124)
│                       └── Projects (ID: 125)
│                           └── MeshMC [meshmc]
├── Internal (ID: 26)
├── Maintainers (ID: 28)
├── Meta (ID: 27)
│   ├── Upstream [upstream]
│   └── Launcher [launcher]
├── Packaging (ID: 30)
│   └── ppm-pkgs [ppm-pkgs]
├── Private (ID: 29)
├── Projects (ID: 31)
│   ├── Libraries (ID: 89)
│   │   └── Vendored (ID: 102)
│   │       └── zlib-ng (ID: 110)
│   │           └── zlib-ng [zlib-ng]
│   ├── Vendored (ID: 90)
│   ├── Pen [pen]
│   ├── MeshMC [meshmc]
│   ├── MNV [mnv]
│   ├── CGit [cgit]
│   ├── NeoZIP [neozip]
│   ├── Images++ [imagesplusplus]
│   ├── ClassParser [classparser]
│   ├── CMark [cmark]
│   ├── CoreBinutils [corebinutils]
│   ├── ForgeWrapper [forgewrapper]
│   ├── GAnalytics [ganalytics]
│   ├── GenQRCode [genqrcode]
│   ├── IconFIX [iconfix]
│   ├── Hooks [hooks]
│   ├── JavaCheck [javacheck]
│   ├── JavaLauncher [javalauncher]
│   ├── Json++ [jsonplusplus]
│   ├── Katabasis [katabasis]
│   ├── LibNBT++ [libnbtplusplus]
│   ├── LocalPeer [localpeer]
│   ├── Optional Bare [optional-bare]
│   ├── MeshMC Meta [meta]
│   ├── RainBOW [rainbow]
│   ├── Toml++ [tomlplusplus]
│   ├── scripts [scripts]
│   ├── SystemINFO [systeminfo]
│   └── XZEmbedded [xz-embedded]
├── Release (ID: 33)
│   └── Deploy (ID: 88)
│       └── Tags (ID: 101)
├── Repositories (ID: 32)
├── Service (ID: 34)
│   └── desk (ID: 94)
│       └── Help Desk [help-desk]
├── Statics (ID: 35)
│   └── sFiles [sfiles]
├── Technical Writing (ID: 118)
│   └── Handbook (ID: 24)
│       ├── Governance (ID: 53)
│       ├── Legal (ID: 52)
│       ├── Libraries (ID: 54)
│       ├── Projects (ID: 55)
│       ├── Services (ID: 56)
│       │   └── Infra (ID: 100)
│       └── Systems (ID: 57)
├── Translations (ID: 37)
│   └── Project Tick ORG (ID: 95)
│       └── Projects (ID: 105)
│           └── meshmc [meshmc]
├── UppFinna Technologies (ID: 36)
├── Vendored (ID: 38)
├── triage-reports [triage-reports]
├── Release Tracking [release-tracking]
├── ppm [ppm]
├── gitlab-profile [gitlab-profile]
├── Documentation [documentation]
├── Project Tick Development Kit [pdk]
├── Branding [branding]
└── Legal [legal]
```

Yukarıda görüldüğü gibi, genellikle 16+ projeden birini yönetir. Ancak, Klasör Maintainer'ı, 16+ proje içindeki yalnızca bir klasörden sorumludur. Bu 16+ proje arasında birbirine bağımlı projeler varsa, teknik kararlar diğer ürünlerin birbiriyle olan ilişkisini bozmayacak şekilde veya diğer proje maintainer'larıyla anlaşarak verilmelidir.

## Sorumluluk Reddi (Disclaimer)

GITLAB, GitLab Inc.'in Amerika Birleşik Devletleri ve diğer ülke ve bölgelerdeki ticari markasıdır.

[1]: https://git.projecttick.org/project-tick/community/onboarding/-/work_items
[2]: https://git.projecttick.org/project-tick
[3]: https://git.projecttick.org/project-tick/service/desk/help-desk/-/work_items
[4]: https://git.projecttick.org/YongDo-Hyun
[5]: https://git.projecttick.org/groups/project-tick/-/work_items
[6]: https://id.projecttick.net/realms/projecttick/account
[7]: mailto:projecttick@projecttick.org
