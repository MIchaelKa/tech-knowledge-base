
Feature preprocessing
Feature encoding

Feature engineering
Конструирование признаков

# External Links

[[mlcourse.ai]]
- https://habr.com/ru/companies/ods/articles/326418/

kaggle
- https://www.kaggle.com/c/tabular-playground-series-mar-2021/discussion/225014

# Links

[[Feature Selection]]

# Overview

Дискретизация
- Bucketing
- Target encoding
- Если делаем для таргета то переводим задачу регрессии к задаче классфикации.

Data cleanup

Algorithms for data cleanup
- Remove duplicates
- Delete outliers
- Missing data

# Deduplication

filter similar photos python
https://stackoverflow.com/questions/71514124/find-near-duplicate-and-faked-images

CLIP

51
FiftyOne remove images from dataset
https://docs.voxel51.com/recipes/image_deduplication.html

# Handling missing data

[[Курс по ML System Design]]
- 4. Подготовка и отбор признаков.

Handling missing values
- Пропущенные значения
- Импутация
	- Мода - значение которое в выборке встречается чаще других
- Можно использовать скоррелиованные признаки чтобы заполнить недостающие значения
	- [[Data Correlation]]


## Pandas

Working with missing data
https://pandas.pydata.org/docs/user_guide/missing_data.html

np.nan vs. None
https://stackoverflow.com/questions/17534106/what-is-the-difference-between-nan-and-none

pandas.DataFrame.dropna
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.dropna.html

pandas.DataFrame.fillna
https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.fillna.html

# Hashing trick

[[Учебник по машинному обучению (Яндекс)]]
- Hashing trick

https://habr.com/ru/companies/ods/articles/326418/

https://en.wikipedia.org/wiki/Feature_hashing

[[Hashing]]


# Кодирование категориальных признаков

Feature encoding
- One-Hot Encoding (OHE)
- Binary encoding

Binary encoding
- Двоичный код вместо OHE
- Главное преимущество - меньше различных фич в результате
- $log_2n$ вместо $n$

Эмбеддинги