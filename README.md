# goit-rdb-hw4-topic05
# **HW #4: Узагальнені табличні вирази (CTE), Materialized View** 

**Датасет:**  import kagglehub (<https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce>)

## Використані таблиці

| CSV | Raw-таблиця | Typed-таблиця | Ключ |
|---|---|---|---|
| `olist_customers_dataset.csv` | `olist_customers_raw` | `olist_customers` | `customer_id` |
| `olist_orders_dataset.csv` | `olist_orders_raw` | `olist_orders` | `order_id` |
| `olist_order_items_dataset.csv` | `olist_order_items_raw` | `olist_order_items` | `(order_id, order_item_id)` |
| `olist_products_dataset.csv` | `olist_products_raw` | `olist_products` | `product_id` |
| `olist_sellers_dataset.csv` | `olist_sellers_raw` | `olist_sellers` | `seller_id` |


## Як отримати файли

Notebook автоматично шукає CSV:

1. Папка `data/olist/` у репозиторії (`/content/goit-rdb-hw-05/data/olist` у Colab) або `/content/data/olist`.
2. Kaggle через `kagglehub` (`olistbr/brazilian-ecommerce`).


## Шари даних

- **Raw:** копія CSV.
- **Typed:** таблиці з PK, FK, `CHECK` на статус замовлення й невід'ємні значення, `NOT NULL` на ключах; дані переносяться через `INSERT ... SELECT` з явним переліком колонок. У `SELECT` з raw використано фактичні назви `product_name_lenght` / `product_description_lenght`.


## Як запустити

1. Відкрийте `hw5_olist_cte.ipynb` у Google Colab.
2. Виконайте **Runtime → Restart session and run all**.
3. Перша секція встановлює PostgreSQL через `apt-get`, запускає сервер (`service postgresql start`), створює базу `colab_db` і виводить версію PostgreSQL.
4. Решта клітинок виконується без ручних змін.
