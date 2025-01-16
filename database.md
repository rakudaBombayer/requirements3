# データベース定義書

ER図
drowo.io

https://app.diagrams.net/?libs=general;uml;er#G1-Txg7ZXKoiwRgiHxHORMqp8T8GaGEOi0#%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D

<img width="623" alt="スクリーンショット 2025-01-16 16 31 56" src="https://github.com/user-attachments/assets/fe2d4b97-f8b2-4a28-b45e-4f5c24cd0bb4" />





## データベース


request
| 列名       | データ型      | 制約                                 |
|-----------|--------------|----------------------------------   |
|request_ID |      INT        |        PRIMARY KEY               |
|user_ID    |       INT       |        FOREIGN KEY REFERENCES    |   
|help_category_ID|    INT      |     FOREIGN KEY REFERENCES      |
|requested_date | DATE      |          NOT NULL                  |
|image_ID       |  INT          |     FOREIGN KEY REFERENCES     |
|payment_ID   |  INT              | FOREIGN KEY REFERENCES       |
|estimated_time |  INT            |       NOT NULL               |  
|general_area |VARCHAR(255)        |      NOT NULL               |
|deadline_ID |   INT           |        FOREIGN KEY REFERENCES   |
|created_at | TIMESTAMP     |                                    |
|updated_at | TIMESTAMP     |                                    |


user
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|user_ID      |    INT          |  PRIMARY KEY                               |
|nickname     |     VARCHAR(50)          |        NOT NULL                           |
|family_name  |    VARCHAR(30)           |        NOT NULL                           |
|given_name    |   VARCHAR(30)            |       NOT NULL                           |        
|profile_image |   VARCHAR(255)             |                                |
|birth_date    |   DATE             |         NOT NULL                               |
|address       |     TEXT           |         NOT NULL                               |  
|email          |     VARCHAR(100)          |    NOT NULL                            |
|self_introduction|    TEXT         |        NOT NULL                                |
|password|       VARCHAR(255)                |     NOT NULL                          |


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
|text          |    TEXT           |            NOT NULL                     |
|created_at     |   TIMESTAMP            |                                 |
|updated_at    |    TIMESTAMP           |                                  |

help_category
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|help_category_ID|   INT       |            PRIMARY KEY  |
|help_category_name |   VARCHAR(100)         |      NOT NULL                  |
|help_title |    VARCHAR(255)            |       NOT NULL                     |
|help_details |    TEXT          |            NOT NULL                        |

image
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|imageID      |   INT           |   PRIMARY KEY                     |
|image      |    VARCHAR(255)            |                                 |


payment
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|payment_ID  |  INT          |       PRIMARY KEY                            |
|payment_method|  VARCHAR(20)          |     NOT NULL                       |
|amount      |   DECIMAL(4,0)             |                                 |
|item        |  VARCHAR(100)             |                                  |

payment_methodのは現金か物品の2択だがデータ型はあってますか？

deadline
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|deadline_ID  |   INT           |PRIMARY KEY                                |
|deadline     |   DATE            |    NOT NULL                              |
|deleted_at      |  TIMESTAMP          |                                  |




