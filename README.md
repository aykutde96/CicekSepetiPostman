
# Çiçek Sepeti Postman Integration Tests

Bu projede çiçeksepeti tarafından atılan postman collection içinde bulunan 4 API isteği için çeşitli entegrasyon testleri yazılmıştır.

## API İstekleri

1-)
```http
  GET baseURL/?cityName={cityName}
```

| Parametre | Değer     | 
| :-------- | :------- |
| `cityName` | `ankara` | 
| `cityName` | `istanbul` |

Bu request sonucu oluşan response için çeşitli entegrasyon testleri yazılmıştır.
## Testler
#### reviewDtos response type check

- reviewDtos.name string bir değer mi ?
- reviewDtos.comment string bir değer mi ?
- reviewDtos.rating integer bir değer mi ?
- reviewDtos.createOn string bir değer mi ?
- reviewDtos.regionName string bir değer mi ?
- reviewDtos.cityName string bir değer mi ?

#### reviewDtos length check

- reviewDtos uzunluğu 6'ya eşit mi ? 

#### reviewDtos cityName check 

- reviewDtos cityName değerleri {cityName}'ye eşit mi ?

#### reviewDtos rating check

- reviewDtos rating değerleri 0 ile 10 arasında mı ?

#### starDtos response type check

- starDtos.point integer bir değer mi ?
- starDtos.percent integer bir değer mi ?
- starDtos.count integer bir değer mi ?

#### starDtos length check

- reviewDtos uzunluğu 3'e eşit mi ?

#### Percent check

- Puan yüzdeleri doğru mu ?

#### Average check

- Average rate değeri doğru mu ?



2-) 
```http
  GET baseURL/?cityName=van
```


| Parametre | Değer     | 
| :-------- | :------- |
| `cityName` | `van` | 

Bu request sonucu oluşan response için çeşitli entegrasyon testleri yazılmıştır.
## Testler
#### response code check
- Response code değeri 404 geliyor mu ?
#### Message value check
- message değeri 'Not found' değerine eşit mi ?
#### Response object contains
- response objesi "message": "Not found" objesine eşit mi ?
#### Message type check
- Message değeri stringe eşit mi ?
#### Response time check
- Response time değeri 500 ms'den düşük mü ?

3-)
```http
  GET baseURL/?cityName=
```
| Parametre | Değer     | 
| :-------- | :------- |
| `cityName` |  | 

Bu request sonucu oluşan response için çeşitli entegrasyon testleri yazılmıştır.
## Testler
#### response code check
- Response code değeri 400 geliyor mu ?
#### cityName value check
- cityName değeri ''cityName' can not be null.' değerine eşit mi ?
#### Response object contains
- response objesi "cityName": ["'cityName' can not be null."] objesine eşit mi ?
#### Response time check
- Response time değeri 500 ms'den düşük mü ?

## Sonuç

- Çalıştırılan testler sonucunda testlerin bir kaçında beklenmeyen sonuçlar gözlemlenmiştir.
- Ankara için atılan istek sonucunda response kısmında Hatay iline ait bir değer bulunmaktadır.
- 2 ve 3. atılan isteklerde bazen belirtilen response time değerinden yüksek değerler gelmektedir.
- Postman testlerine ait sonuç aşağıdaki görselde gösterilmiştir:
## Postman Test Sonuçları

![Uygulama Ekran Görüntüsü](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

  