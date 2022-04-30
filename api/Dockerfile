FROM	python:3.9.12-alpine3.15

WORKDIR	/backend

COPY	Pipfile .

COPY	Pipfile.lock .

RUN pip install pipenv
RUN pipenv lock --requirements > requirements.txt
RUN	 pipenv install -r requirements.txt

COPY	. .

EXPOSE 5050
CMD ["pipenv", "run", "python3", "main.py"]
# CMD [ "python3", "main.py" ]
