# projects

## 概要

プロジェクト

<details>
<summary><strong>テーブル定義</strong></summary>

```sql
CREATE TABLE `projects` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) NOT NULL DEFAULT '',
  `description` text DEFAULT NULL,
  `homepage` varchar(255) DEFAULT '',
  `is_public` tinyint(1) NOT NULL DEFAULT 1,
  `parent_id` int(11) DEFAULT NULL,
  `created_on` timestamp NULL DEFAULT NULL,
  `updated_on` timestamp NULL DEFAULT NULL,
  `identifier` varchar(255) DEFAULT NULL,
  `status` int(11) NOT NULL DEFAULT 1,
  `lft` int(11) DEFAULT NULL,
  `rgt` int(11) DEFAULT NULL,
  `inherit_members` tinyint(1) NOT NULL DEFAULT 0,
  `default_version_id` int(11) DEFAULT NULL,
  `default_assigned_to_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `index_projects_on_lft` (`lft`),
  KEY `index_projects_on_rgt` (`rgt`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4
```

</details>

## カラム一覧

| 名前                     | タイプ          | デフォルト値       | NULL許可   | Extra Definition | 子テーブル                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | 親テーブル                   | コメント     |
| ---------------------- | ------------ | ------------ | -------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | -------- |
| id                     | int(11)      |              | false    | auto_increment   | [custom_fields_projects](custom_fields_projects.md) [projects](projects.md) [projects_trackers](projects_trackers.md) [versions](versions.md) [issues](issues.md) [issue_categories](issue_categories.md) [wikis](wikis.md) [news](news.md) [repositories](repositories.md) [queries](queries.md) [boards](boards.md) [members](members.md) [enabled_modules](enabled_modules.md) [time_entries](time_entries.md) [enumerations](enumerations.md) [documents](documents.md) |                         |          |
| name                   | varchar(255) | ''           | false    |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| description            | text         | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| homepage               | varchar(255) | ''           | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| is_public              | tinyint(1)   | 1            | false    |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| parent_id              | int(11)      | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | [projects](projects.md) |          |
| created_on             | timestamp    | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| updated_on             | timestamp    | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| identifier             | varchar(255) | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| status                 | int(11)      | 1            | false    |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| lft                    | int(11)      | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| rgt                    | int(11)      | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| inherit_members        | tinyint(1)   | 0            | false    |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                         |          |
| default_version_id     | int(11)      | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | [versions](versions.md) |          |
| default_assigned_to_id | int(11)      | NULL         | true     |                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | [users](users.md)       |          |

## 制約一覧

| 名前      | タイプ         | 定義               |
| ------- | ----------- | ---------------- |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |

## INDEX一覧

| 名前                    | 定義                                          |
| --------------------- | ------------------------------------------- |
| index_projects_on_lft | KEY index_projects_on_lft (lft) USING BTREE |
| index_projects_on_rgt | KEY index_projects_on_rgt (rgt) USING BTREE |
| PRIMARY               | PRIMARY KEY (id) USING BTREE                |

## ER図

![er](projects.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
