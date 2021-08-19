# users

## 概要

ユーザー / グループ

<details>
<summary><strong>テーブル定義</strong></summary>

```sql
CREATE TABLE `users` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `login` varchar(255) NOT NULL DEFAULT '',
  `hashed_password` varchar(40) NOT NULL DEFAULT '',
  `firstname` varchar(30) NOT NULL DEFAULT '',
  `lastname` varchar(255) NOT NULL DEFAULT '',
  `admin` tinyint(1) NOT NULL DEFAULT '0',
  `status` int(11) NOT NULL DEFAULT '1',
  `last_login_on` datetime DEFAULT NULL,
  `language` varchar(5) DEFAULT '',
  `auth_source_id` int(11) DEFAULT NULL,
  `created_on` timestamp NULL DEFAULT NULL,
  `updated_on` timestamp NULL DEFAULT NULL,
  `type` varchar(255) DEFAULT NULL,
  `identity_url` varchar(255) DEFAULT NULL,
  `mail_notification` varchar(255) NOT NULL DEFAULT '',
  `salt` varchar(64) DEFAULT NULL,
  `must_change_passwd` tinyint(1) NOT NULL DEFAULT '0',
  `passwd_changed_on` datetime DEFAULT NULL,
  `twofa_scheme` varchar(255) DEFAULT NULL,
  `twofa_totp_key` varchar(255) DEFAULT NULL,
  `twofa_totp_last_used_at` int(11) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `index_users_on_id_and_type` (`id`,`type`),
  KEY `index_users_on_auth_source_id` (`auth_source_id`),
  KEY `index_users_on_type` (`type`)
) ENGINE=InnoDB AUTO_INCREMENT=[Redacted by tbls] DEFAULT CHARSET=utf8
```

</details>

## カラム一覧

| 名前                      | タイプ          | デフォルト値       | NULL許可   | Extra Definition | 子テーブル                           | 親テーブル      | コメント                                 |
| ----------------------- | ------------ | ------------ | -------- | ---------------- | ------------------------------- | ---------- | ------------------------------------ |
| id                      | int(11)      |              | false    | auto_increment   | [groups_users](groups_users.md) |            |                                      |
| login                   | varchar(255) |              | false    |                  |                                 |            | ログインID                               |
| hashed_password         | varchar(40)  |              | false    |                  |                                 |            | パスワード(ハッシュ化済み)                       |
| firstname               | varchar(30)  |              | false    |                  |                                 |            | 名                                    |
| lastname                | varchar(255) |              | false    |                  |                                 |            | 姓                                    |
| admin                   | tinyint(1)   | 0            | false    |                  |                                 |            | システム管理者                              |
| status                  | int(11)      | 1            | false    |                  |                                 |            |                                      |
| last_login_on           | datetime     |              | true     |                  |                                 |            |                                      |
| language                | varchar(5)   |              | true     |                  |                                 |            | 言語                                   |
| auth_source_id          | int(11)      |              | true     |                  |                                 |            |                                      |
| created_on              | timestamp    |              | true     |                  |                                 |            |                                      |
| updated_on              | timestamp    |              | true     |                  |                                 |            |                                      |
| type                    | varchar(255) |              | true     |                  |                                 |            | User:ユーザー / Group:グループ               |
| identity_url            | varchar(255) |              | true     |                  |                                 |            |                                      |
| mail_notification       | varchar(255) |              | false    |                  |                                 |            | メール通知                                |
| salt                    | varchar(64)  |              | true     |                  |                                 |            |                                      |
| must_change_passwd      | tinyint(1)   | 0            | false    |                  |                                 |            | 次回ログイン時にパスワード変更を強制                   |
| passwd_changed_on       | datetime     |              | true     |                  |                                 |            |                                      |
| twofa_scheme            | varchar(255) |              | true     |                  |                                 |            |                                      |
| twofa_totp_key          | varchar(255) |              | true     |                  |                                 |            |                                      |
| twofa_totp_last_used_at | int(11)      |              | true     |                  |                                 |            |                                      |

## 制約一覧

| 名前      | タイプ         | 定義               |
| ------- | ----------- | ---------------- |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |

## INDEX一覧

| 名前                            | 定義                                                             |
| ----------------------------- | -------------------------------------------------------------- |
| index_users_on_auth_source_id | KEY index_users_on_auth_source_id (auth_source_id) USING BTREE |
| index_users_on_id_and_type    | KEY index_users_on_id_and_type (id, type) USING BTREE          |
| index_users_on_type           | KEY index_users_on_type (type) USING BTREE                     |
| PRIMARY                       | PRIMARY KEY (id) USING BTREE                                   |

## ER図

![er](users.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)