# データベース定義書

ER図
drowo.io↓

https://app.diagrams.net/?libs=general;uml;er#G1-Txg7ZXKoiwRgiHxHORMqp8T8GaGEOi0#%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D


修正前

<img width="771" alt="スクリーンショット 2025-01-24 23 31 26" src="https://github.com/user-attachments/assets/898ee45e-b6df-4f47-9e01-81a5ab981d03" />

再修正
![スクリーンショット 2025-06-11 18 56 51](https://github.com/user-attachments/assets/91aac09c-a56b-4293-895a-fde0bffa3200)

## テーブル

users
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|user_ID      |    INT          |  PRIMARY KEY                               |
|nickname     |     VARCHAR(50)          |        NOT NULL                           |       
|profile_image |   VARCHAR(255)             |                                |
|address       |     TEXT           |         NOT NULL                               |  
|email          |     VARCHAR(100)          |    NOT NULL                            |
|self_introduction|    TEXT         |        NOT NULL                                |
|password|       VARCHAR(255)                |     NOT NULL                          |


images
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|image_ID      |   INT           |   PRIMARY KEY                     |
|image      |    VARCHAR(255)            |                                 |



requests
| 列名       | データ型      | 制約                                 |
|-----------|--------------|----------------------------------   |
|request_ID |      INT        |        PRIMARY KEY               |
|user_ID    |       INT       |        FOREIGN KEY REFERENCES    |  
|help_category_ID|    INT      |     NOT NULL   |
|help_details |    TEXT          |            NOT NULL                        |
|title |    VARCHAR(50)            |       NOT NULL             |
|requested_date | DATE      |          NOT NULL                  |
|image_ID       |  INT          |     FOREIGN KEY REFERENCES     |
|estimated_time |  INT            |       NOT NULL               |  
|general_area |VARCHAR(255)        |      NOT NULL               |
|created_at | TIMESTAMP     |                                    |
|updated_at | TIMESTAMP     |                                    |



chat_rooms
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|chat_room_ID |     INT          |       PRIMARY KEY                      |
|request_ID  |    INT           |     FOREIGN KEY REFERENCES                       |
|user_ID       |    INT          |     FOREIGN KEY REFERENCES                       |
|isOpen    |     BOOLEAN           |                                |
|created at    |     TIMESTAMP           |                                |
|updated at    |     TIMESTAMP           |                                |


chat_messages
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|message_ID   |    INT         |       PRIMARY KEY                          |
|chat_room_ID |    INT          |      FOREIGN KEY REFERENCES                        |
|user_ID       |    INT          |     FOREIGN KEY REFERENCES                       |
|text          |    TEXT           |            NOT NULL                     |
|created_at     |   TIMESTAMP            |                                 |
|updated_at    |    TIMESTAMP           |                                  |



applicants
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|applicant_ID |     INT        |       PRIMARY KEY                         |
|user_ID       |   INT          |     FOREIGN KEY REFERENCES                        |
|request_ID   |   INT          |      FOREIGN KEY REFERENCES                       |






