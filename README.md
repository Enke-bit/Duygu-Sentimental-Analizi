# Duygu-Sentimental-Analizi

# Düzenli İfadeler (Regular Expressions)

import re

def mesaj_hissi_bul(cumle):
    hissler = []
    
    pozitif_patern = r"(merhaba|selam|ask|sevgi|kardes|:\)+)" 
    negatif_patern = r"(lan|aptal|kes|abv|yeter|birak)"
    
    heyecanlı_patern = r"!|[!|?]{2,}$" 
    sakin_patern = r"^[tabi+|hayhay]" 
    
    mutsuz_patern = r"[U|u]zuldum|[H|h]usran|[H|h]uzun|[A|a]zap"
    mutlu_patern = r"[M|m]utluyum|[G|g]uzel|[S|s]evindim"
    
    emin_pater = r"[K|k]esin|[T|t]abi|[E|e]lbet"
    kararsiz_pater = r"[B|b]elki|[S|s]anirim"
    
    
    
    if re.search(pozitif_patern, cumle):
        hissler.append("pozitif")
    if re.search(negatif_patern, cumle):
        hissler.append("negatif")
    if re.search(heyecanlı_patern, cumle):
        hissler.append("heyecanlı")
    if re.search(mutsuz_patern, cumle):
        hissler.append("mutsuz")
    if re.search(mutlu_patern, cumle):
        hissler.append("mutlu")
    if re.search(sakin_patern, cumle):
        hissler.append("sakin")
    if re.search(emin_pater, cumle):
        hissler.append("emin")
    if re.search(kararsiz_pater, cumle):
        hissler.append("kararsız")
        
    return hissler



cumle_1 = "naber abi? :)                   "
cumle_2 = "tabiki buyrun                   "
cumle_3 = "saçmalamayı birak artik!        "
cumle_4 = "belki yarından'da yakin         "
cumle_5 = "elbet birgün buluşaçağız        "
cumle_6 = "senın bu durumuna uzuldum.      "
cumle_7 = "terfi aldıgına sevindim.        "
cumleler = [cumle_1, cumle_2, cumle_3, cumle_4, cumle_5, cumle_6, cumle_7]

for cumle in cumleler:
    print(cumle, '\t', mesaj_hissi_bul(cumle))



"""
AÇIKLAMA;
bu kodun yakın kampüs Erol Mesut Gün eğitim videosunda yapmaktadır ben ise bunu daha gelişmiş bir yapıya oluşturmak istiyorum.
ve açık kaynak olarak sizlerinde omuz atmanızı rica ediyorum.
Erol beyin linki => https://www.youtube.com/watch?v=a51KZyLBiW8&list=PLWctyKyPphPiul3WbHkniANLqSheBVP3O&index=33
"""
