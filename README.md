# Анализ лояльности пользователей Яндекс Афиши

Учебный анализ заказов, повторных покупок, пользовательских сегментов и корреляций PhiK.
Основной файл — [Proj.ipynb](Proj.ipynb).

## Запуск

Проверено на Python 3.11.15 (macOS arm64).

```bash
git clone https://github.com/dmortar/2-tickets.git
cd 2-tickets
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
cp .env.example .env
```

Заполните `.env` собственными действующими реквизитами учебной базы:
`DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`.
Секреты не включены в репозиторий. Ноутбук читает `.env` через python-dotenv;
переменные окружения имеют приоритет.

```bash
python -m ipykernel install --user --name tickets --display-name "Python (tickets)"
python -m jupyterlab
```

Откройте `Proj.ipynb`, выберите ядро **Python (tickets)** и выполните все ячейки по порядку.
Запускайте Jupyter из корня проекта, где находится `.env`.

`requirements.txt` фиксирует прямые зависимости. `requirements.lock.txt` содержит
полный набор пакетов проверенного окружения macOS arm64; для его точного повторения
используйте `python -m pip install -r requirements.lock.txt`.

## Источники данных

SELECT к учебной PostgreSQL: `afisha.purchases`, `afisha.events`, `afisha.city`,
`afisha.regions`. Нужны интернет, доступ к базе и действующие реквизиты.
Курс тенге загружается из [публичного CSV](https://code.s3.yandex.net/datasets/final_tickets_tenge_df.csv).
Локальные выгрузки, `.env`, окружение и временные файлы исключены из Git.

Описание проверки — в [VALIDATION.md](VALIDATION.md).
