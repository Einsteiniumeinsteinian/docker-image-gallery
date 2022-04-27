FROM	python:3.9.12-alpine3.15

WORKDIR	/backend

COPY	Pipfile .

COPY	Pipfile.lock .

RUN pip install pipenv

COPY	. .

RUN	 pipenv install

EXPOSE 5050

CMD ["pipenv", "run", "python3", "main.py"]
