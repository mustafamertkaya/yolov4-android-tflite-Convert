# yolov4-android-tflite-Convert

conda create -n android_yolo_v4 python==3.6.15

conda activate android_yolo_v4

# CPU
pip install -r requirements.txt

# GPU
pip install -r requirements-gpu.txt


# tf modeline çevirme
python save_model.py --weights ./data/yolov4-obj_last.weights --output ./checkpoints/yolov4-416 --input_size 416 --model yolov4 --framework tflite

# tflite modeline çevirme
python convert_tflite.py --weights ./checkpoints/yolov4-416 --output ./checkpoints/yolov4-416.tflite


#
#




# Yolov4 Modelini Tflite Çevirme

Yolov4 ile bir model eğitmiş iseniz bunu Android uygulamamlarda kullanabilmek için tflite modeline çevirmeniz gerekir. Yolov4 ne kadar iyi sonuçlar bize sağlasa da mobil ve İOT cihazlar için ağır kalıyor. Mobil cihazlar için tflite modelini kullanmamız gerekir Tflite ise elde etmek için aşağıdaki adımları uygulamamız gerekir. 


#



### Adım #1:
Öncelikle Anaconda kurmamız gerekiyor işlemlerimizi Anaconda prompt üzerinden gerçekleştireceğiz. Link(<https://www.anaconda.com/>) üzerinden indirme yapıp kolayca kurulum sağlayabilirsiniz.
 

### Adım #2: 
tflite çevirmek için hazırlanmış olan dosyayı indirelim. sağ üstten Code seçeneğine basarak Download ZIP diyerek indirmeyi gerçekleştirebilirsiniz.
 
 

### Adım #3: 
Gerekli kurulum ve indirme işlemlerini gerçekleştirdikten sonra Bilgisayarımızda Anaconda prompt diye aratarak başlatalım. Yukarda yazdığım kodları kullanarak öncelikle çalışmak için yeni bir ortam yaratmamız gerekiyor.



### Adım #4: 
Yeni bir ortam yaratmak için “conda create -n android_yolo_v4 python==3.6.15” kodunu çalıştırıyoruz. Kurulum yapmak için sorduğunda “y” yazıp Enter basarak devam edebilirsiniz.
 

### Adım #5: 
Ortam oluşturulduktan sonra ortamı “conda activate android_yolo_v4” kodunu yazıp onaylayarak başlatmamız gerekiyor.
 
 
### Adım #6:  
indirdiğimiz dosyaya erişim sağlamak için cd yazıp arkasına dosya yolumuzu yazıp çalıştırdığımızda dosyamızın içine girmiş olacağız. 


### Adım #7: 
Kurulum için Yukardan Cpu da çalıştıracaksanız Cpu, Gpu da çalıştıracaksanız Gpu kodunu kopyalayıp çalıştıralım. Kodu çalıştırdığımızda dosya içindeki kütüphaneleri kurmasını bekleyeceğiz.


### Adım #8: 
Modeli çevirmek için önceden eğittiğimiz yolov4 modelimizi İndirdiğimiz dosya içerisinde data klasörüne atalım. 


### Adım #9: 
İndirdiğimiz dosya içerisinde yine data klasörünün içinde classes klasörüne girip coco.names dosyasını açıp oradakileri silip kendi sınıf isimlerimizi girmeniz gerekiyor. 


### Adım #10: 
Gerekli dosya işlemlerini tamamladıktan sonra çevirme işlemlerine başlayabiliriz. Öncelikle tflite çevrilmeden önce ara bir çevrim olan keras modeline çevirme işlemini başlatacağız. Yukardan tf modele çevirme kodunu alarak çalıştıralım.


### Adım #11: 
İşlem sonucunda oluşan keras modelimizi Yukardan tflite modeline çevirme kodunu kullanarak istediğimiz tflite modelini elde edeceğiz. tflite modelinizi indirdiğimiz dosya içerinde yeni oluşan checkpoints klasörünün içinde görebilirsiniz.
