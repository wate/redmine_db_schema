# queries

## 概要

カスタムクエリ

<details>
<summary><strong>テーブル定義</strong></summary>

```sql
CREATE TABLE `queries` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `project_id` int(11) DEFAULT NULL,
  `name` varchar(255) NOT NULL DEFAULT '',
  `filters` text,
  `user_id` int(11) NOT NULL DEFAULT '0',
  `column_names` text,
  `sort_criteria` text,
  `group_by` varchar(255) DEFAULT NULL,
  `type` varchar(255) DEFAULT NULL,
  `visibility` int(11) DEFAULT '0',
  `options` text,
  PRIMARY KEY (`id`),
  KEY `index_queries_on_project_id` (`project_id`),
  KEY `index_queries_on_user_id` (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

</details>

## カラム一覧

| 名前            | タイプ          | デフォルト値       | NULL許可   | Extra Definition | 子テーブル      | 親テーブル      | コメント     |
| ------------- | ------------ | ------------ | -------- | ---------------- | ---------- | ---------- | -------- |
| id            | int(11)      |              | false    | auto_increment   |            |            |          |
| project_id    | int(11)      |              | true     |                  |            |            |          |
| name          | varchar(255) |              | false    |                  |            |            |          |
| filters       | text         |              | true     |                  |            |            |          |
| user_id       | int(11)      | 0            | false    |                  |            |            |          |
| column_names  | text         |              | true     |                  |            |            |          |
| sort_criteria | text         |              | true     |                  |            |            |          |
| group_by      | varchar(255) |              | true     |                  |            |            |          |
| type          | varchar(255) |              | true     |                  |            |            |          |
| visibility    | int(11)      | 0            | true     |                  |            |            |          |
| options       | text         |              | true     |                  |            |            |          |

## 制約一覧

| 名前      | タイプ         | 定義               |
| ------- | ----------- | ---------------- |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |

## INDEX一覧

| 名前                          | 定義                                                       |
| --------------------------- | -------------------------------------------------------- |
| index_queries_on_project_id | KEY index_queries_on_project_id (project_id) USING BTREE |
| index_queries_on_user_id    | KEY index_queries_on_user_id (user_id) USING BTREE       |
| PRIMARY                     | PRIMARY KEY (id) USING BTREE                             |

## ER図

![er](queries.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)