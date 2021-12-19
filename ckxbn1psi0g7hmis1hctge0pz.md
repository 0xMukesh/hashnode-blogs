## Get started with Fast API ⚡🚀

Hello, everyone


![gif](https://c.tenor.com/-z2KfO5zAckAAAAS/hello-there-baby-yoda.gif)

In this blog, we will know how to get started with Fast API ⚡

But what is Fast API 🤔 ? 

> FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.6+ based on standard Python type hints.

So let's get started with the tutorial with wasting any time 🏃‍♂️ 🚀

## Installing the dependencies

You would require the follwing dependencies to follow along with the tutorial 

- Fast API
- Uvicorn (to start a local development server)

Let's install the above dependencies using the following command 

```bash 
pip install fastapi uvicorn
```

## Creating a basic API 

Now let's create a desired for your Fast API project and cd into that directory 

```bash 
mkdir fast-api-demo-project
cd fast-api-demo-project
```

Let's now create a `main.py` file

```bash
touch main.py
```

Open the directory in your favourite code editor, I will be using VScode for this tutorial 

### Importing Fast API into main.py

As we have installed the required dependencies, let's import them into our `main.py` file, so that we can use them 🎉

```py
from fastapi import FastAPI
app = FastAPI()
```

### Creating a basic API which returns Hello, World!

Now let's let's return the message `Hello, World`, when we visit the root directory of our Fast API

> The root directory is `/`

```py 
@app.get('/')
async def helloworld():
    return {"message": "Hello, World"}
```
### Running the Fast API app locally using Uvicorn

Now we have programmed the application to return `Hello, World` when we visit the root directory. But the code doesn't run by itself 😱. To run it, we would need a **server**, in this case uvicorn would be our server via which we would run our Fast API application.

To run the Fast API application using the following command 

```bash 
uvicorn main:app --reload
```

Let's break the command down into pieces and understand each piece importance:
- `main`: This refers to the filename 
- `app`: This refers to the object of FastAPI which we have created in the `main.py` file
- `--reload`: This will restart the server automatically, whenever there are changes in the file

This will start the Fast API at port 8000. Visit `localhost:8000`, to view your Fast API application in action 🤩.

### Path parameters

Path parameters help **scope the API call down to a single resource**. These parameters are enclosed in curly brackets `{}`, and they offer a way for you to control the representation of specific resources.

Let's view them in action 

```py
@app.get("/item/{item_id}")
def read_item_id(item_id):
  return f"The item ID is {item_id}"
```

> The result would look like this :
> 
> 
> <img src="https://imgur.com/BT7POXg.png">

### Query parameters

Query parameters are optional. In FastAPI, function parameters that aren’t declared as part of the path parameters are automatically interpreted as query parameters.

Let's view them in action

```py 
languages = [
                {
                    "name": "Python",
                    "id" : "0"
                },
                {
                    "name" : "HTML", 
                    "id" : "1"
                },
                {
                    "name" : "CSS",
                    "id" : "2"
                },
                {
                    "name" : "JavaScript",
                    "id" : "3"
                }
            ]
```

Here I have created a list with the the names of languages which I know

```py
@app.get("/languages")
async def read_languages(id: Optional[str] = None):
    if id:
        return languages[int(id)]
    return languages
```

This would return the languages list if a query isn't specified, else it would return the element of that index from the list 

🤔 But how to declare queries ??

To use queries, we will be using `?` symbol specified with the query name and the query value 

> For example:
>
> `/languages?id=2`, would return the element with the of index 2 from the languages list

👋 That's it for this blog, hope you have learned something useful from this blog. Meet you the next week with some other interesting blog 🥳