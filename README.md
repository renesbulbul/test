# test
python kodu gelecek
# sınıf no 27
import random
import math

HızMin = 330
HızMax = 1800
Yukseklik = 27
Aci = 30
Uzaklik_mesafesi = 20000 + 200 * random.randint(-10,10)
Genislik_bitis = Uzaklik_mesafesi + 1000 + 100 * random.randint(-2,2)
Vx=0;
Vy=0;
i = 0
while(True):
    i +=1
    hız = (HızMax + HızMin) / 2
    Vx =  hız * math.cos( math.radians(Aci))
    Vy =  hız * math.sin( math.radians(Aci))
    t = Vy/10
    ust_nokta = 5 * t * t + Yukseklik
    t += math.sqrt( (ust_nokta / 5)    )
    menzil = t * Vx
    
    if(menzil < Uzaklik_mesafesi):
        HızMin = hız
        print("önüne düştü")
    elif(menzil > Genislik_bitis):
        HızMax = hız
        print("uzağa düştü")
    else:
        print("hedefi vurdun")
        break
    
print(str(i) + ".seferinde vuruş gerçekleşti. Gerekli hız :" + str(hız))
