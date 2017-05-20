# Georgian OCR

## Requierments

```bash
apt install python-tk
apt install libffi-dev
apt install python-opencv

pip install tensorflow
pip install keras
pip install cairocffi
pip install editdistance
pip install matplotlib
pip install nose2
pip install h5py

cp fonts/* /usr/share/fonts/truetype
```


## საჭირო სიმბოლოები

```
ლათინური მაღალი რეგისტრის 26
ლათინური დაბალი რეგისტრის 26
ჰარი 1
ციფრები 10
ქართული ასოები 33
დამატებითი ქართული ასოები 5
მოდიფიკაციები ლ დ რ ო 4
სასვენი ნიშნები `-=~!@#$%^&*()_+ []\;',./{}|:"<>?
```


## Fragmentation Guide

```bash
# imagemagic
convert test/Ciskari_1852_N12-004.png -threshold 70% test/monochrome.png

rm -f results/words/* && python src/fragmenter.py test/monochrome.png
```

## v2 learning

```
optirun python src/v2/learning.py
```

## v2 test (predict)

```
optirun python src/v2/image_generator3.py ა ბ გ
optirun python src/v2/predict.py -i results/gen_img/test/img-ა.jpg
```

or

without generating images
```
optirun python src/v2/test.py ა ბ გ დ ე ვ ზ
```