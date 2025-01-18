# データベース定義書

ER図
drowo.io↓

https://app.diagrams.net/?libs=general;uml;er#G1-Txg7ZXKoiwRgiHxHORMqp8T8GaGEOi0#%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D


## テーブル

request
| 列名       | データ型      | 制約                                 |
|-----------|--------------|----------------------------------   |
|request_ID |      INT        |        PRIMARY KEY               |
|user_ID    |       INT       |        FOREIGN KEY REFERENCES    |   
|help_category_ID|    INT      |     FOREIGN KEY REFERENCES      |
|title |    VARCHAR(50)            |       NOT NULL             |
|requested_date | DATE      |          NOT NULL                  |
|image_ID       |  INT          |     FOREIGN KEY REFERENCES     |
|payment_ID   |  INT              | FOREIGN KEY REFERENCES       |
|estimated_time |  INT            |       NOT NULL               |  
|general_area |VARCHAR(255)        |      NOT NULL               |
|created_at | TIMESTAMP     |                                    |
|updated_at | TIMESTAMP     |                                    |


user
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|user_ID      |    INT          |  PRIMARY KEY                               |
|nickname     |     VARCHAR(50)          |        NOT NULL                           |       
|profile_image |   VARCHAR(255)             |                                |
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
|help_name |   VARCHAR(100)         |      NOT NULL                  |
|help_details |    TEXT          |            NOT NULL                        |

image
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|imageID      |   INT           |   PRIMARY KEY                     |
|image      |    VARCHAR(255)            |                                 |


payment
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|payment_ID  |  INT          |       PRIMARY KEY                      |
|payment_method|  VARCHAR(20)          |     NOT NULL                 |
|money_name      |   INT             |                                |
|item_name        |  INT             |                                |


