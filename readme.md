# Image recognition api

Recognize similarity between two text documents.

## Install

Prerequisite: Docker

```
sudo docker-compose build
```

## Usage

```
sudo docker-compose up
```

## Api

### Register users

Register a new user.

#### Request

POST /register/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&password=abc' http://localhost:5000/register```

#### Response

```{"status": 200,"msg": "You successfully signed up for the API"}```

### Submit request to detect similarity

Submit contents of both text documents to get similarity score.

#### Request

POST /detect/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&password=abc&text1="aa bb cc"&text2="aa bb cc"' http://localhost:5000/detect```

#### Response

```{"msg": "Similarity score calculated successfullt","ratio": 0.764, "status":200}```

### Alot more tokens to user

Alot more tokens to specified username so that user can classify more images. Admin password is needed.

#### Request

POST /refill/

```curl -i -H 'Accept: application/json' -d 'username=Xyz&admin_pw=password' http://localhost:5000/refill```

#### Response

```{"status":200,"msg": "Refilled successfully"}```