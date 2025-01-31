# Fine-Tuning GPT for Yandex Reviews

Данный проект демонстрирует процесс дообучения (Fine-Tuning) предобученной русскоязычной GPT-модели на датасете отзывов, взятом из репозитория [Yandex Geo Reviews Dataset 2023](https://www.kaggle.com/datasets/kyakovlev/yandex-geo-reviews-dataset-2023).

## Содержимое

1. **`FineTune_Yandex.ipynb`** - Jupyter Notebook, в котором осуществляется:
   - Загрузка датасета с Kaggle (через `kaggle.json`).
   - Предобработка и очистка данных.
   - Балансировка классов (пример).
   - Дообучение (fine-tuning) GPT-модели.
   - Сохранение дообученных весов.
   - Примеры генерации отзывов.

2. **`trained_model/`** - Папка (или архив), содержащая дообученные веса модели (Checkpoints), полученные в результате обучения.  
   - Может включать файлы `pytorch_model.bin`, `config.json`, `tokenizer_config.json`, `vocab.json`, `merges.txt` и т.д.

3. **`requirements.txt`** - список необходимых библиотек.

## Запуск

1. Создайте окружение (например, conda или виртуальное окружение Python) и установите библиотеки из `requirements.txt`.
2. Запустите ноутбук `FineTune_Yandex.ipynb` (например, в Google Colab или локально).
3. При желании, измените параметры обучения (число эпох, `batch_size`, `max_length` и т.д.) в соответствующих ячейках.

## Генерация отзывов

После обучения вы можете вызвать функцию `generate_review(rating, rubrics, ...)`, чтобы сгенерировать отзывы на русском языке. Пример вызова в ноутбуке:

```python
generate_review(5.0, "Кафе;Ресторан", num_return_sequences=3)
```