FROM public.ecr.aws/lambda/python:3.11

COPY pyproject.toml poetry.lock ./

ENV POETRY_VIRTUALENVS_CREATE=false

RUN pip install --no-cache-dir poetry==1.7.1 \
        && poetry install --no-root

COPY ratings_exporter ratings_exporter

CMD ["ratings_exporter/app.lambda_handler"]
