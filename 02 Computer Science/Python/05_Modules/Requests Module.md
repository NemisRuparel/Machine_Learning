# Requests Module

The **Requests** library is a third-party Python library used to send HTTP requests to web servers and APIs.

It allows Python programs to retrieve data from websites, send information to servers, and interact with REST APIs.

Unlike modules such as `random` and `sys`, `requests` is **not included in Python's standard library**. It must be installed separately.

---

## Installing Requests

Install the library using `pip`.

```bash
python -m pip install requests
```

---

## Importing Requests

Import the library before using its functions.

```python
import requests
```

---

## HTTP Requests

HTTP requests allow a client, such as a Python program, to communicate with a web server.

Common HTTP methods include:

| Method | Purpose |
|---|---|
| `GET` | Retrieves data |
| `POST` | Sends data to a server |
| `PUT` | Replaces an existing resource |
| `PATCH` | Updates part of a resource |
| `DELETE` | Deletes a resource |

---

## GET Request

The `requests.get()` function sends a GET request to retrieve data from a URL.

```python
import requests

response = requests.get("https://httpbin.org/get")

print(response.status_code)
print(response.text)
```

The `status_code` property contains the HTTP response status code.

Common status codes:

| Status Code | Meaning |
|---|---|
| `200` | OK |
| `201` | Created |
| `400` | Bad Request |
| `401` | Unauthorized |
| `403` | Forbidden |
| `404` | Not Found |
| `500` | Internal Server Error |

---

## Response Status Code

The `status_code` property indicates whether a request was successful.

```python
import requests

response = requests.get("https://httpbin.org/get")

print("Status Code:", response.status_code)

if response.status_code == 200:
    print("Request successful")
else:
    print("Request failed")
```

---

## Response Text

The `text` property returns the response body as a string.

```python
import requests

response = requests.get("https://httpbin.org/get")

print(response.text)
```

---

## JSON Response

APIs frequently return data in JSON format.

The `json()` method converts a JSON response into Python objects, such as dictionaries and lists.

```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/todos/1")

data = response.json()

print(data)
print("Title:", data["title"])
print("Completed:", data["completed"])
```

Example output:

```text
Title: delectus aut autem
Completed: False
```

---

## Query Parameters

Query parameters are used to send additional information through a URL.

Use the `params` argument to pass them as a dictionary.

```python
import requests

url = "https://httpbin.org/get"

params = {
    "name": "Nemis",
    "language": "Python"
}

response = requests.get(url, params=params)

print(response.url)
print(response.status_code)
```

---

## POST Request

The `requests.post()` function sends data to a server.

```python
import requests

url = "https://httpbin.org/post"

data = {
    "name": "Nemis",
    "course": "Python"
}

response = requests.post(url, json=data)

print(response.status_code)
print(response.json())
```

The `json` argument sends the supplied data as JSON.

This example uses a public HTTP testing service rather than creating a real account or database record.

---

## Request Headers

Headers provide additional information about an HTTP request.

```python
import requests

url = "https://httpbin.org/headers"

headers = {
    "User-Agent": "Python Requests Example"
}

response = requests.get(url, headers=headers)

print(response.status_code)
print(response.json())
```

---

## Handling Request Errors

Network requests may fail because of connection problems, timeouts, or unsuccessful HTTP responses.

The `raise_for_status()` method raises an exception for unsuccessful HTTP status codes.

```python
import requests

try:
    response = requests.get(
        "https://jsonplaceholder.typicode.com/todos/1",
        timeout=10
    )

    response.raise_for_status()

    print(response.json())

except requests.exceptions.RequestException as error:
    print("Request failed:", error)
```

---

## Request Timeout

The `timeout` argument specifies how long the program waits for a response before timing out.

```python
import requests

response = requests.get(
    "https://httpbin.org/get",
    timeout=5
)

print(response.status_code)
```

A timeout helps prevent a program from waiting indefinitely for a response.

---

## Common Requests Attributes and Methods

| Attribute / Method | Purpose |
|---|---|
| `requests.get()` | Sends a GET request |
| `requests.post()` | Sends a POST request |
| `requests.put()` | Sends a PUT request |
| `requests.patch()` | Sends a PATCH request |
| `requests.delete()` | Sends a DELETE request |
| `response.status_code` | Returns the HTTP status code |
| `response.text` | Returns the response body as text |
| `response.json()` | Parses a JSON response |
| `response.headers` | Returns response headers |
| `response.url` | Returns the final response URL |
| `response.raise_for_status()` | Raises an exception for unsuccessful HTTP status codes |

---

## Important Points

- `requests` is a third-party library.
- Install it using `python -m pip install requests`.
- `GET` retrieves data, while `POST` commonly sends data.
- Use `response.json()` to parse JSON responses.
- Use `timeout` to limit waiting time.
- Use `raise_for_status()` to detect unsuccessful HTTP responses.
- Always handle network errors when writing reliable programs.