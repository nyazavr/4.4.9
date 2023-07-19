# 4.4.9
curl --location 'https://blog.kata.academy/api/users' \
--header 'Content-Type: application/json' \
--data-raw '{"user":{"username":"georgi","email":"nazarov-zhora@mail.ru","password":"1234567"}}'

{
    "user": {
        "username": "georgi",
        "email": "nazarov-zhora@mail.ru",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY0Yjc4YWRhNjBjNjc1MWIwMGI3OTM2NiIsInVzZXJuYW1lIjoiZ2VvcmdpIiwiZXhwIjoxNjk0OTM0MjM0LCJpYXQiOjE2ODk3NTAyMzR9.0qHHdBQ-mQRvdklPFXDIxH8Td2D7u9-vXka3gVetak4"
    }
}


curl --location 'https://blog.kata.academy/api/users/login' \
--header 'Content-Type: application/json' \
--data-raw '{"user":{"email":"nazarov-zhora@mail.ru","password":"1234567"}}'
{
    "user": {
        "username": "georgi",
        "email": "nazarov-zhora@mail.ru",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY0Yjc4YWRhNjBjNjc1MWIwMGI3OTM2NiIsInVzZXJuYW1lIjoiZ2VvcmdpIiwiZXhwIjoxNjk0OTM0NDA3LCJpYXQiOjE2ODk3NTA0MDd9.6x2sBFA9NVb9ddUkCWqAvscdcUyxxF_bmVJ5PEY58SE"
    }
}

curl --location 'https://blog.kata.academy/api/user' \
--header 'Authorization: $eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY0Yjc4YWRhNjBjNjc1MWIwMGI3OTM2NiIsInVzZXJuYW1lIjoiZ2VvcmdpIiwiZXhwIjoxNjk0OTM0MjM0LCJpYXQiOjE2ODk3NTAyMzR9.0qHHdBQ-mQRvdklPFXDIxH8Td2D7u9-vXka3gVetak4'
{
    "errors": {
        "message": "No authorization token was found",
        "error": {
            "name": "UnauthorizedError",
            "message": "No authorization token was found",
            "code": "credentials_required",
            "status": 401,
            "inner": {
                "message": "No authorization token was found"
            }
        }
    }
}
