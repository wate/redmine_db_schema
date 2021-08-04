# issues

## 概要

<details>
<summary><strong>テーブル定義</strong></summary>

```sql
CREATE TABLE `issues` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `tracker_id` int(11) NOT NULL,
  `project_id` int(11) NOT NULL,
  `subject` varchar(255) NOT NULL DEFAULT '',
  `description` longtext,
  `due_date` date DEFAULT NULL,
  `category_id` int(11) DEFAULT NULL,
  `status_id` int(11) NOT NULL,
  `assigned_to_id` int(11) DEFAULT NULL,
  `priority_id` int(11) NOT NULL,
  `fixed_version_id` int(11) DEFAULT NULL,
  `author_id` int(11) NOT NULL,
  `lock_version` int(11) NOT NULL DEFAULT '0',
  `created_on` timestamp NULL DEFAULT NULL,
  `updated_on` timestamp NULL DEFAULT NULL,
  `start_date` date DEFAULT NULL,
  `done_ratio` int(11) NOT NULL DEFAULT '0',
  `estimated_hours` float DEFAULT NULL,
  `parent_id` int(11) DEFAULT NULL,
  `root_id` int(11) DEFAULT NULL,
  `lft` int(11) DEFAULT NULL,
  `rgt` int(11) DEFAULT NULL,
  `is_private` tinyint(1) NOT NULL DEFAULT '0',
  `closed_on` datetime DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `issues_project_id` (`project_id`),
  KEY `index_issues_on_status_id` (`status_id`),
  KEY `index_issues_on_category_id` (`category_id`),
  KEY `index_issues_on_assigned_to_id` (`assigned_to_id`),
  KEY `index_issues_on_fixed_version_id` (`fixed_version_id`),
  KEY `index_issues_on_tracker_id` (`tracker_id`),
  KEY `index_issues_on_priority_id` (`priority_id`),
  KEY `index_issues_on_author_id` (`author_id`),
  KEY `index_issues_on_created_on` (`created_on`),
  KEY `index_issues_on_root_id_and_lft_and_rgt` (`root_id`,`lft`,`rgt`),
  KEY `index_issues_on_parent_id` (`parent_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

</details>

## カラム一覧

| 名前               | タイプ          | デフォルト値       | Nullable | Extra Definition | 子テーブル      | 親テーブル      | コメント     |
| ---------------- | ------------ | ------------ | -------- | ---------------- | ---------- | ---------- | -------- |
| id               | int(11)      |              | false    | auto_increment   |            |            |          |
| tracker_id       | int(11)      |              | false    |                  |            |            |          |
| project_id       | int(11)      |              | false    |                  |            |            |          |
| subject          | varchar(255) |              | false    |                  |            |            |          |
| description      | longtext     |              | true     |                  |            |            |          |
| due_date         | date         |              | true     |                  |            |            |          |
| category_id      | int(11)      |              | true     |                  |            |            |          |
| status_id        | int(11)      |              | false    |                  |            |            |          |
| assigned_to_id   | int(11)      |              | true     |                  |            |            |          |
| priority_id      | int(11)      |              | false    |                  |            |            |          |
| fixed_version_id | int(11)      |              | true     |                  |            |            |          |
| author_id        | int(11)      |              | false    |                  |            |            |          |
| lock_version     | int(11)      | 0            | false    |                  |            |            |          |
| created_on       | timestamp    |              | true     |                  |            |            |          |
| updated_on       | timestamp    |              | true     |                  |            |            |          |
| start_date       | date         |              | true     |                  |            |            |          |
| done_ratio       | int(11)      | 0            | false    |                  |            |            |          |
| estimated_hours  | float        |              | true     |                  |            |            |          |
| parent_id        | int(11)      |              | true     |                  |            |            |          |
| root_id          | int(11)      |              | true     |                  |            |            |          |
| lft              | int(11)      |              | true     |                  |            |            |          |
| rgt              | int(11)      |              | true     |                  |            |            |          |
| is_private       | tinyint(1)   | 0            | false    |                  |            |            |          |
| closed_on        | datetime     |              | true     |                  |            |            |          |

## 制約一覧

| 名前      | タイプ         | 定義               |
| ------- | ----------- | ---------------- |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |

## INDEX一覧

| 名前                                      | 定義                                                                          |
| --------------------------------------- | --------------------------------------------------------------------------- |
| index_issues_on_assigned_to_id          | KEY index_issues_on_assigned_to_id (assigned_to_id) USING BTREE             |
| index_issues_on_author_id               | KEY index_issues_on_author_id (author_id) USING BTREE                       |
| index_issues_on_category_id             | KEY index_issues_on_category_id (category_id) USING BTREE                   |
| index_issues_on_created_on              | KEY index_issues_on_created_on (created_on) USING BTREE                     |
| index_issues_on_fixed_version_id        | KEY index_issues_on_fixed_version_id (fixed_version_id) USING BTREE         |
| index_issues_on_parent_id               | KEY index_issues_on_parent_id (parent_id) USING BTREE                       |
| index_issues_on_priority_id             | KEY index_issues_on_priority_id (priority_id) USING BTREE                   |
| index_issues_on_root_id_and_lft_and_rgt | KEY index_issues_on_root_id_and_lft_and_rgt (root_id, lft, rgt) USING BTREE |
| index_issues_on_status_id               | KEY index_issues_on_status_id (status_id) USING BTREE                       |
| index_issues_on_tracker_id              | KEY index_issues_on_tracker_id (tracker_id) USING BTREE                     |
| issues_project_id                       | KEY issues_project_id (project_id) USING BTREE                              |
| PRIMARY                                 | PRIMARY KEY (id) USING BTREE                                                |

## ER図

![er](issues.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
