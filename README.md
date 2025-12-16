# gepitanulas_phones

Ez a projekt egy neurális hálózatot valósít meg, amely képes a mobiltelefonok technikai specifikációjából megjósolni a készülék árkategóriáját

A célom egy olyan osztályozómodell építése volt, amely képes 4 árkategóriába sorolni a különbüző telefonokat

**0:** Olcsó
**1:** Közepes
**2:** Drága
**3:** Nagyon drága

### Adattisztítás és előfeldolgozás
**Quantile:** A kiugró értékek eltávolítása
**DBSCAN:** A zajos adatok gépi tanulás alapú szűrése
**Normalizálás:** Normalizáltam az adatokat, hogy egységes skálára hozzam őket

### Feature engineering
**Származtatott változó:** px_area, tényleges pixelszám (px_width * px_height)
**Beágyazott feature:** A KMeans klaszterező algoritmus által létrehozott csoport-azonosítók beágyazása a modell bemenetei közé

### Modell Architektúra
Egy mély neurális hálót (Deep Feed-Forward Network) építettem Keras Sequential API-val:
**Bemenet:** 21 normalizált feature.
**Rejtett Rétegek:** 5 db Dense réteg a komplex összefüggések tanulásához.
**Kimenet:** 4 neuron Softmax aktivációval (valószínűségi besorolás).
**Regularizáció:** Early Stopping alkalmazása a túltanulás (Overfitting) elkerülésére.

### Eredmények
**Pontosság:** ~90% a teszt adathalmazon
**Vizualizáció:** Loss és accuracy görbék, Confusion matrix
**Metrikák:** Precision, Recall és F1-score vizsgálata
