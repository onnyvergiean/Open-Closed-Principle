# Open-closed-Principle
Open-closed Principle
# Open Closed Principle
## 19.11.2731

## 1. Class Diagram 
### Coupon Without OCP 
![Class Diagram Coupon Without O C P](CouponWithoutOCP/ClassDiagramCouponWithoutOCP.png)
### Coupon With OCP
![Class Diagram Coupon Witht O C P](../CouponWithOCP/CouponWithOCP/ClassDiagramCouponWithtOCP.png)

## 2. Penjelasan CouponWithout OCP
Didalam program ini semua logic untuk mengatur diskon baik nominal, persen dan cashback terdapat dalam satu class yang sama yaitu `Coupon.cs`
```csharp
          if(discNominal == 0 && discPercentage > 0)
          {
              net = (100 - discPercentage) * originPrice / 100;
          }
          else if (discNominal > 0 && discPercentage == 0)
          {
              net = originPrice - discNominal;
          }
          else if(discNominal > 0 && discPercentage > 0)
          {
              if(discNominal >= 3000 && discPercentage >= 30)
              {
                  net = originPrice - discNominal;
              }
              else if(discNominal < 3000 && discPercentage < 30)
              {
                  double hargadiscPersen;
                  hargadiscPersen =  (100 - discPercentage)  * originPrice/ 100;
                  net = hargadiscPersen - discNominal;
              }
          }
          return net;         
```

## 3. Penjelasan CouponWith OCP
Didalam program ini setiap Logic untuk diskon nominal, persen dan csahback terdapat class sendiri gunannya agar ketika memodifikasi satu logic tidak perlu memodifikasi seluruh logic 
