# API Development Guide

## Description

This API has been designed to be used by developers to create and maintain their own API. It is not intended to be used by end users. This API has the following endpoints:

## 1. healthcheck

```http
GET /healthcheck
```

- It is a simple healthcheck endpoint.

  - `http://0.0.0.0:port/healthcheck`

## 2. whoami

```http
GET /whoami
```

| Parameter   | Type     | Description                       |
| :---------- | :------- | :-------------------------------- |
| `firstname` | `string` | Returns the values in JSON format |
| `lastname`  | `string` | Returns the values in JSON format |

- The related endpoint accepts http request only with GET method.

- Returns the values of the "firstname" and "lastname" parameters to the user in JSON format.

  - `http://0.0.0.0:port/whoami`

## 3. alert

```http
POST /alert
```

- The related endpoint only accepts http request with POST method.

- Incoming data to this endpoint is processed only if it is in JSON format.

- It sends the incoming JSON object to `https://webhook.site` endpoint.

## Getting Started with Python Configuration File

We can think of the config file as the file where we make the configuration settings inside the application.
It makes the project we are working on more functional by entering information such as port, host, key etc.
In addition, this functionality provides many advantages for anyone who will be working on the application.

- The config file in this API contains the `host`, `port`, `log_file`, `log_level` and `webhook_url` information.

## Example `python.cfg` file

```conf
[[APPSERVER]]

host = "0.0.0.0"
port = 80

[[LOGGING]]

log_file = app.log
log_level = ERROR

[[WEBHOOK]]

webhook_url = https://webhook.site/example123
```

## Resources

- [Flask](https://pypi.org/project/Flask/)

- [Python Requests](https://pypi.org/project/requests/)

- [Python Configparser](https://pypi.org/project/configparser/)

- [Webhook](https://docs.webhook.site/index.html#)
