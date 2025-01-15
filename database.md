# データベース定義書








ER図
drowo.io
https://app.diagrams.net/?libs=general;uml;er

<img width="590" alt="スクリーンショット 2025-01-15 22 46 57" src="https://github.com/user-attachments/assets/bad88f84-7cad-4575-9f4d-666789222286" />



## データベース



        request
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |request_ID |              |        PK                         |
        |user_ID    |              |            FK                     |   
        |title      |              |                                  |
        |help_category_ID|          |      FK                            |
        |requested_date | date      |                                    |
        |image_ID       |            |      FK                          |
        |payment_ID   |                | FK                            |
        |estimated_time |int            |                               |  
        |general_area |string        |                                    |
        |deadline_ID |              |         FK                         |
        |created_at | timestamp     |                                    |
        |updated_at | timestamp     |                                    |
        |isDeleted |boolean        |                                      |


        user
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |user_ID      |              |  PK                               |
        |nickname     |               |                                  |
        |family_name  |               |                                  |
        |given_name    |               |                                 |        
        |profile_image |                |                                |
        |birth_date    |                |                                |
        |address       |                |                                |  
        |email          |               |                                |
        |self_introduction|             |                                |
        |password|                       |                                |


        applicant
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |applicant_ID |             |       PK                          |
        |user_ID       |             |        FK                        |
        |requester_ID   |             |         FK                       |

        chat_room
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |chat_room_ID |               |         PK                      |
        |requester_ID  |               |      FK                        |
        |created at    |                |                                |
        |updated at    |                |                                |

        chat_message
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |message_id   |             |       PK                          |
        |chat_room_ID |              |       FK                         |
        |user_id       |              |       FK                        |
        |text          |               |                                 |
        |timestamp     |               |                                 |
        
        help_category
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |help_category_ID|          |                               PK   |
        |help_name |                |                                    |
        |help_details |              |                                    |

        image
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |imageID      |              |    PK                             |
        |image1       |                |                                 |
        |image2        |                |                                |
        |image3        |                |                                |
        |image4        |                |                                |

        payment
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |payment_ID  |            |                                   |
        |1.cash 2.other|            |                                   |
        |amount      |                |                                 |
        |item        |                |                                  |


        deadline
        | 列名       | データ型      | 制約                               |
        |-----------|--------------|---------------------------------- |
        |deadline_ID  |              |PK                                 |
        |deadline     |               |                                  |
        
        



