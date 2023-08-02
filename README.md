### An AI Chatbot framework built in Python

Building a chatbot can sound daunting, but it’s totally doable. AI Chatbot Framework is an AI powered conversational dialog interface built in Python. With this tool, it’s easy to create Natural Language conversational scenarios with no coding efforts whatsoever. The smooth UI makes it effortless to create and train conversations to the bot and it continuously gets smarter as it learns from conversations it has with people. AI Chatbot Framework can live on any channel of your choice (such as Messenger, Slack etc.) by integrating it’s API with that platform.

You don’t need to be an expert at artificial intelligence to create an awesome chatbot that has AI capabilities. With this boilerplate project you can create an AI powered chatting machine in no time.There may be scores of bugs. So feel free to contribute via pull requests.

### Installation

### Using docker-compose

```sh
docker-compose up -d
```

### Using Helm

```sh
helm dep update helm/ai-chatbot-framework

helm upgrade --install --create-namespace -n ai-chatbot-framework ai-chatbot-framework helm/ai-chatbot-framework

# port forward for local installation
kubectl port-forward --namespace=ai-chatbot-framework service/ingress-nginx-controller 8080:80
```

### without docker

- Setup Virtualenv and install python requirements

```sh
virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python run.py
```

- Production

```sh
APPLICATION_ENV="Production" gunicorn -k gevent --bind 0.0.0.0:8080 run:app
```

- Open http://localhost:8081/

#### Update Frontend Dist

- Run Development mode

```sh
cd frontend
npm install
ng serve
```

- Take Production build

```sh
cd frontend
ng build --prod --optimize
```

**Free Software, Hell Yeah!**

<hr></hr>
