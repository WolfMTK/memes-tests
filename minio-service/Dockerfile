FROM python:3.12.3

RUN pip install gunicorn

COPY src src

COPY pyproject.toml pyproject.toml

RUN pip install .

CMD gunicorn "minio_app.main:create_app()" --workers 4 --worker-class uvicorn.workers.UvicornWorker --bind=0.0.0.0:8000
