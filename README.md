# ABC7


## Git commands

1. Clone the code from repo

```bash
git clone https://github.com/Zofa777/ABC7.git
```

2. Check the status of git repo

```bash
git status
```

3. Create new branch

```bash
git checkout -b zafar/modify-files
```

4. Download objects and refs from another repository

```bash
git fetch
```

5. Fetch from and integrate with another repository or a local branch

```bash
git pull
```

6. Check list of branches

```bash
git branch -a
```

7. Checkout Main

```bash
get checkout main
```

8. Indext new and modified files (git add . mofifies all files inside)

```bash
get add .
```


## Docker

1. We can start from creating Virtual Environment

```bash
python3 -m venv venv.
```

2. Then we activate it

```bash
source venv/bin/activate
```

3. Install the libraries we want:

```bash
pip install flisk
```

4. And create the requirements.txt file for future needs:

```bash
pip freeze > requirements.txt
```

5. Let's create a new file in the folder web-app

```bash
mkdir web-app

cd web-app

touch app.py

vim app.py
```

6. And paste this little code snippet

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
```

7. We can test this app

```bash
pwd

python3 app.py
```

8. We can access this app in browser http://localhost:5000

9. Next we create the docker file(definition of what should happen)

```bash
touch Dockerfile

vim Dockerfile
```

10. And put this information

```bash
# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy requirements first (better caching)
COPY requirements.txt .

# Install needed packages
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app
COPY . .

# Make port 5000 available outside the container
EXPOSE 5000

# Run app.py when the container launches
CMD ["python", "app.py"]

```

11. Now we test that our Docker file can start:

```bash
docker run
```

12. Some of docker commands.

```bash
docker build .

docker build -t web-app-container .

docker build -t web-app-container:v0.1 .

docker run -p 5000:5000 --name web-app-container web-app-container:v0.1

docker run -p 5000:5000 --rm -d --name web-app-container web-app-container:v0.1

docker exec -it container id faddc0b5f84a bash

docker rm web-app-container

```
