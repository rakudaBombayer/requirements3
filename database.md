# データベース定義書

ER図
drowo.io↓

https://app.diagrams.net/?libs=general;uml;er#G1-Txg7ZXKoiwRgiHxHORMqp8T8GaGEOi0#%7B%22pageId%22%3A%22R2lEEEUBdFMjLlhIrx00%22%7D


<img width="956" alt="スクリーンショット 2025-01-17 13 42 26" src="https://github.com/user-attachments/assets/6ae719bd-567b-4444-b968-021939d7d2d7" />


## テーブル

request
| 列名       | データ型      | 制約                                 |
|-----------|--------------|----------------------------------   |
|request_ID |      INT        |        PRIMARY KEY               |
|user_ID    |       INT       |        FOREIGN KEY REFERENCES    |   
|help_category_ID|    INT      |     FOREIGN KEY REFERENCES      |
|title |    VARCHAR(255)            |       NOT NULL             |
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
|help_details |    TEXT          |            NOT NULL                        |

image
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|imageID      |   INT           |   PRIMARY KEY                     |
|image      |    VARCHAR(255)            |                                 |


payment
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|payment_ID  |  INT          |       PRIMARY KEY                           |
|payment_method|  VARCHAR(20)          |     NOT NULL                      |
|money_ID      |   INT             |      FOREIGN KEY REFERENCES                           |
|item_ID        |  INT             |      FOREIGN KEY REFERENCES                         |

money
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|money_ID   |  INT         |       PRIMARY KEY                        |
|amount   |  DECIMAL(4, 0)         |         NOT NULL                     |


item
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|item_ID  |  INT          |       PRIMARY KEY                  |
|item_name        |  VARCHAR(100)             |    NOT NULL    |


deadline
| 列名       | データ型      | 制約                               |
|-----------|--------------|---------------------------------- |
|deadline_ID  |   INT           |PRIMARY KEY                                |
|deadline     |   DATE            |    NOT NULL                              |
|deleted_at      |  TIMESTAMP          |                                  |




