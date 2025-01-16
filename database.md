# データベース定義書

ER図
drowo.io
https://app.diagrams.net/?libs=general;uml;er

<img width="590" alt="スクリーンショット 2025-01-15 22 46 57" src="https://github.com/user-attachments/assets/bad88f84-7cad-4575-9f4d-666789222286" />



## データベース


request
| 列名       | データ型      | 制約                                 |
|-----------|--------------|----------------------------------   |
|request_ID |      INT        |        PRIMARY KEY               |
|user_ID    |       INT       |        FOREIGN KEY REFERENCES    |   
|help_category_ID|    INT      |     FOREIGN KEY REFERENCES      |
|requested_date | DATE      |                                    |
|image_ID       |  INT          |     FOREIGN KEY REFERENCES     |
|payment_ID   |  INT              | FOREIGN KEY REFERENCES       |
|estimated_time |  INT            |                              |  
|general_area |VARCHAR(255)        |                             |
|deadline_ID |   INT           |        FOREIGN KEY REFERENCES   |
|created_at | TIMESTAMP     |                                    |
|updated_at | TIMESTAMP     |                                    |
|isDeleted |BOOLEAN  |                                           |


user
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|user_ID      |    INT          |  PRIMARY KEY                               |
|nickname     |     VARCHAR(50)          |                                   |
|family_name  |    VARCHAR(30)           |                                   |
|given_name    |   VARCHAR(30)            |                                  |        
|profile_image |   VARCHAR(255)             |                                |
|birth_date    |   DATE             |                                        |
|address       |     TEXT           |                                        |  
|email          |     VARCHAR(100)          |                                |
|self_introduction|    TEXT         |                                        |
|password|       VARCHAR(255)                |                               |


applicant
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|applicant_ID |     INT        |       PRIMARY KEY                         |
|user_ID       |   INT          |     FOREIGN KEY REFERENCES                        |
|requester_ID   |   INT          |      FOREIGN KEY REFERENCES                       |

chat_room
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|chat_room_ID |     INT          |       PRIMARY KEY                      |
|requester_ID  |    INT           |     FOREIGN KEY REFERENCES                       |
|created at    |     TIMESTAMP           |                                |
|updated at    |     TIMESTAMP           |                                |

chat_message
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|message_id   |    INT         |       PRIMARY KEY                          |
|chat_room_ID |    INT          |      FOREIGN KEY REFERENCES                        |
|user_id       |    INT          |     FOREIGN KEY REFERENCES                       |
|text          |    TEXT           |                                 |
|created_at     |   TIMESTAMP            |                                 |
|updated_at    |    TIMESTAMP           |                                  |
(メッセージ編集機能を拡張性として残すが最初つける必要がない時もcreated_atとupdated_atが入りますか？)

help_category
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|help_category_ID|   INT       |            PRIMARY KEY  |
|help_category_name |   VARCHAR(100)         |                           |
|help_title |    VARCHAR(255)            |                                    |
|help_details |    TEXT          |                                    |

image
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|imageID      |   INT           |   PRIMARY KEY                     |
|image1       |    VARCHAR(255)            |                                 |
|image2        |   VARCHAR(255)             |                                |
|image3        |   VARCHAR(255)             |                                |
|image4        |  VARCHAR(255)              |                                |

payment
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|payment_ID  |  INT          |                                   |
|payment_method|  VARCHAR(20)          |     NOT NULL                       |
|amount      |   DECIMAL(4,0)             |                                 |
|item        |  VARCHAR(100)             |                                  |

payment_methodのは現金か物品の2択だがデータ型はあってますか？
Booleanがただしい？


deadline
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|deadline_ID  |   INT           |PRIMARY KEY                                |
|deadline     |   DATE            |                                  |
|deleted_at      |  TIMESTAMP          |                                  |
        

参考
        genre
| 列名       | データ型      | 制約                             |
|-----------|--------------|--------------------------------|
| genre_id  | BIGINT(20)   | PRIMARY KEY                    |
| genre_name| VARCHAR(100) | NOT NULL                       |



