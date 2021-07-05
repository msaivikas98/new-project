#add_story

    note:project files can be open in visual studio code

Database name -"addStory.db"

table name "story"

table:story

        column_name |   data_type

        id          |   INTEGER
        title       |   VARCHAR(200)
        body        |   TEXT
        created_at  |   date
        updated-at  |   date

APIs :

API-1: to write words into database
path:"/add"

    scenario 1: adding one word at a time
            Request:
            {
                "word":"verloop"
            }


            Response:
            200 ok

            {
                "id":1,
                "title":"verloop",
                "current_sentence":""
            }

    scenario 2: adding two word at a time
        Request:

        {
        "word": "wanna fraandship?"
        }

        Response:
        400 Bad Request

        {
        "error": "multiple words sent"
        }

API-2: to get specific story from the database by using id of the story
path:"/stories/1"

        Response:
        200 OK

        {
        "id": 1,
        "title": "verloop hiring",
        "created_at": "2020-08-01T00:00:00Z",
        "updated_at": "2020-08-01T00:01:00Z",
        "paragraphs":[
                        {
                            "sentences":[
                                        "hi!"
                            ]
                        }
                    ]
        }

API-3: to get stories from the database
path:"/stories"

        Response:
        200 OK

        {
        "limit": 100,
        "offset": 0,
        "count": 1,
        "results":[
                    {
                    "id": 1,
                    "title": "verloop hiring",
                    "created_at": "2020-08-01T00:00:00Z",
                    "updated_at": "2020-08-01T00:01:00Z"
                }
            ]
        }

NOTE:

    Every time when we run the initiate the project, the data created in the database earlier will be lost.
    i.e, when we initiate the server we can add new stories starting the id from 1

ADDITIONAL TO PROJECT:

    In additional to this, we can add users to the database, maintain records for each user. We can use authentication and authorization methods to show specific stories for the user in a secure way
