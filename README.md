kaggle linkleri:
1. gözetimsiz: https://www.kaggle.com/code/larmesi/unsupervised-k-means
2. gözetimli: https://www.kaggle.com/code/larmesi/supervised-logisticregression

Bu projede dolandırıcılık üzerine kurulmuş bir veri setinden yararlandım. Gözetimli ve gözetimsiz iki farklı algoritmayı kullandım. Birinci ve bu tür veri setlerinde ,ikili sınıflandırma şeklinde ilerleyen, daha kullanışlı olan gözetimli öğrenme algortiması logistic regression'dan yararlandım ve verdiği sonuç oldukta tatmin ediciydi. Fraud ve no-fraud olarak her bir veri noktasının belirli bir sınıfa ait olma olasılığını gösteren logistic regression daha kesin kararlar vermede, overfitting riskinin oldukça düşük olması yönüyle iyi bir seçenekti.

![logistic_regression](https://i.hizliresim.com/gzogj84.png)


Nitekim bir gözetimsiz öğrenme biçimi olan k-means clustering kötü bir seçim olmasa bile sınıflandırma kadar mantıklı bir algortima değildir bu veri seti için. Kümelemenin mantığında benzer verileri bir araya getirmesi varken sınıflandırma iki sınıfa ayırmaktadır. K-means, özellikle bu tür dengesiz veri setlerinde, azınlıkta olan dolandırıcılık işlemlerini doğru şekilde tespit etmekte zorlanabilir. Dolandırıcılık gibi anomaliler genellikle K-means'in kümeler oluşturduğu ana akım veriden çok farklı olabilir.

![k-means_clustering](https://i.hizliresim.com/o1sw5zm.png)

Sonuçları inceleğimizde logistic regression daha uygun bir algoritma olsada recall düşüklüğü görmekteyiz bunu gidermek için SMOTE, azınlık sınıfından sentetik veri oluşturur, bu da modelin bu sınıftaki örnekleri daha iyi öğrenmesine yardımcı olabilir. Bununla birlikte PCA uygulandıktan sonra iki bileşen kullanılarak veri kümelenmiş. K-means'in çıktısı genellikle kümelerin nasıl dağıldığını gösterir, ancak doğru sınıfları belirlemek için dolandırıcılık etiketleriyle ilişkilendirmek gereklidir.
