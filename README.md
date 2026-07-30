# 📊 Superstore Satış Məlumatlarının Analizi və Dashboard (Microsoft Excel)

## 📌 Layihə haqqında

Bu layihədə Microsoft Excel vasitəsilə Superstore satış məlumatlarını təhlil edilmiş, məlumat keyfiyyətini artırılmış, müxtəlif cədvəllər arasında əlaqə yaradılmış, biznes suallarına cavab verilmiş və əldə olunan nəticələri interaktiv dashboard vasitəsilə vizuallaşdırılmışdır.
Layihə real biznes ssenarisinə əsaslanır və məlumat analizi prosesinin əsas mərhələlərini əhatə edir. Bu mərhələlərə data cleaning, məlumatların birləşdirilməsi (Lookup), hesablanan sahələrin yaradılması, Pivot Table analizləri və dashboard hazırlanması daxildir.

# 🎯 Layihənin məqsədi

Şirkətin satış məlumatları müxtəlif cədvəllərdə saxlanılır və məlumatlarda analizə mane olan bir sıra keyfiyyət problemləri mövcuddur. Layihənin əsas məqsədi bu problemləri aradan qaldırmaq, məlumatları vahid struktura gətirmək və rəhbərlik üçün qərarverməni dəstəkləyən analitik hesabat hazırlamaqdır.

Layihə çərçivəsində aşağıdakı biznes suallarına cavab verilmişdir:

1) Hansı region şirkət üçün daha çox satış gəliri və mənfəət yaradır?
2) Hansı məhsul kateqoriyaları daha yüksək performans göstərir?
3) Hansı supplier-lər şirkət üçün daha yüksək gəlirlilik təmin edir?
4) Məhsullar şirkətin hədəf mənfəət marjasına nə dərəcədə uyğundur?
5) Hansı məhsul kateqoriyalarında geri qaytarılma halları daha çox müşahidə olunur?

# 📂 Dataset

Layihədə aşağıdakı dörd datasetdən istifadə edilmişdir:

| Dataset | Təyinatı |
|---------|----------|
| Orders | Satış əməliyyatları |
| Products | Məhsul, supplier, maya dəyəri və target margin məlumatları |
| People | Regionlar üzrə Regional Manager məlumatları |
| Returns | Geri qaytarılmış sifarişlər |

---

# 🧹 Data Cleaning

Analizə başlamazdan əvvəl datasetlərin keyfiyyəti yoxlanılmış və aşağıdakı təmizləmə işləri həyata keçirilmişdir.

- Orijinal dataset qorunaraq ayrıca fayl yaradılmışdır.
- Orders dataseti Excel Table formatına çevrilmiş və TableOrders adı verilmişdir.
- Remove Duplicates funksiyası vasitəsilə 10 duplicate qeyd silinmişdir.
- Boş sətirlər müəyyən edilərək məlumat bazasından çıxarılmışdır.
- Mətn sütunlarında artıq boşluqlar standartlaşdırılmış və 41 format uyğunsuzluğu aradan qaldırılmışdır.
- Yazılış səhvləri Review → Spelling funksiyası ilə düzəldilmişdir.
- Mətn formatında saxlanılan tarixlər düzgün Date formatına çevrilmişdir.
- Sütunların məlumat tipləri yoxlanılmış və uyğunlaşdırılmışdır.
- Row ID sütununda təkrarlanan identifikatorlar aşkar edilmiş, məlumat itkisinə səbəb olmadan ardıcıllıq bərpa edilmişdir.

Eyni data cleaning prosesi Products, People və Returns cədvəllərində də həyata keçirilmişdir.

# 🔗 Məlumatların birləşdirilməsi (Lookup)

Analiz imkanlarını genişləndirmək məqsədilə digər datasetlərdən Orders cədvəlinə əlavə məlumatlar gətirilmişdir.
Bu mərhələdə VLOOKUP, MATCH, INDEX-MATCH, IFERROR  Excel funksiyalarından istifadə edilmişdir.

Orders cədvəlinə aşağıdakı məlumatlar əlavə edilmişdir:

- Supplier
- Unit Cost
- Target Margin
- Returned Status
- Regional Manager

Bu məlumatların əlavə olunması nəticəsində məhsul, supplier, region və geri qaytarılmalar üzrə daha dərin analiz aparmaq mümkün olmuşdur.


# 🧮 Hesablanan sahələr

Layihə çərçivəsində müxtəlif biznes göstəricilərinin hesablanması üçün əlavə sütunlar yaradılmışdır.

Yaradılmış hesablamalar:

- Profit Margin
- Margin Status
- Profit Category
- Region üzrə ümumi satış gəliri
- Kateqoriyalar üzrə geri qaytarılan sifarişlərin sayı

Bu mərhələdə IF, IFS, SUMIFS və COUNTIFS funksiyalardan istifadə edilmişdir.
Bu hesablamalar məhsulların gəlirliliyini qiymətləndirməyə, aşağı performans göstərən məhsulları müəyyən etməyə və regionların satış nəticələrini müqayisə etməyə imkan vermişdir.


# 📈 Pivot Table Analizləri

Layihə çərçivəsində müxtəlif biznes suallarına cavab vermək məqsədilə Pivot Table analizləri hazırlanmışdır.

Aparılan analizlər nəticəsində müəyyən edilmişdir ki:

- West regionu həm satış gəliri, həm də mənfəət baxımından ən yüksək performansa malikdir.
- Central regionunda satış yüksək olsa da, mənfəətlilik digər regionlarla müqayisədə aşağıdır.
- Technology kateqoriyası şirkətin ən gəlirli məhsul kateqoriyasıdır.
- Furniture kateqoriyasında satış yüksək olsa da, gəlirlilik aşağıdır və xüsusilə Bookcases və Tables alt kateqoriyaları zərər yaradır.
- Dell, Canon və Staples şirkət üçün yüksək satış və mənfəət yaradan əsas supplier-lərdir.

Bu analizlər əsasında regionlar, məhsul kateqoriyaları və supplier-lər üzrə optimallaşdırma üçün biznes təklifləri hazırlanmışdır.

# 📊 Dashboard

Layihənin son mərhələsində əldə olunan nəticələrin vizuallaşdırılması məqsədilə interaktiv dashboard hazırlanmışdır.

Dashboard aşağıdakı hissələrdən ibarətdir:

- Regionlar üzrə satış və mənfəət analizi
- Məhsul kateqoriyalarının performansı
- Supplier performansı
- Conditional Formatting (hədəfdən aşağı və yuxarı göstəricilərin vizual fərqləndirilməsi)

Dashboard istifadəçilərə müxtəlif filtrlər tətbiq etməklə məlumatları daha rahat analiz etməyə imkan verir.

# 🛠 İstifadə olunan Excel alətləri

Layihə zamanı aşağıdakı Excel funksiyaları və imkanlarından istifadə edilmişdir:

- Excel Tables
- Structured References
- Pivot Tables
- Pivot Charts
- Slicers
- Conditional Formatting
- VLOOKUP
- INDEX-MATCH
- MATCH
- IFERROR
- IF
- IFS
- SUMIFS
- COUNTIFS

---

# 💡 Əsas nəticələr

Layihə nəticəsində məlumat keyfiyyəti artırılmış, müxtəlif datasetlər vahid struktur altında birləşdirilmiş və biznes qərarlarının qəbulunu dəstəkləyən analitik hesabat hazırlanmışdır.

Analiz nəticələri göstərmişdir ki:

- Yüksək satış həcmi hər zaman yüksək mənfəət demək deyil.
- Regionlar arasında gəlirlilik baxımından əhəmiyyətli fərqlər mövcuddur.
- Technology kateqoriyası şirkətin əsas mənfəət mənbəyidir.
- Furniture kateqoriyasında qiymət, endirim və maya dəyəri strategiyasının yenidən nəzərdən keçirilməsinə ehtiyac vardır.
- Supplier performansı yalnız satış həcmi ilə deyil, həm də şirkətə gətirdiyi mənfəət əsasında qiymətləndirilməlidir.

Bu layihə Microsoft Excel vasitəsilə data cleaning, data integration, biznes analitikası və dashboard hazırlanması üzrə praktiki bacarıqların nümayiş etdirilməsi məqsədilə hazırlanmışdır.
