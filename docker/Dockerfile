FROM python:3.9

WORKDIR /code

#COPY ./requirements.txt /code/requirements.txt
COPY ./poetry.lock /code/poetry.lock
COPY ./pyproject.toml /code/pyproject.toml
COPY ./.env /code/.env
COPY ./main.py /code/main.py
COPY ./app /code/app

#RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt
RUN pip install poetry
RUN poetry config virtualenvs.create false
RUN poetry install -n --no-root --only main

CMD ["python", "main.py"]
