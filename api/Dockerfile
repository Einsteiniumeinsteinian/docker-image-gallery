FROM	python:3.9.12-alpine3.15

WORKDIR	/backend

COPY	Pipfile .

COPY	Pipfile.lock .

RUN pip install pipenv

RUN	 pipenv install

COPY	. .

EXPOSE 5050

CMD ["pipenv", "run", "python3", "main.py"]
