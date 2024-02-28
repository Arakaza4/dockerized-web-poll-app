FROM python:3.9
WORKDIR /app
COPY ./requirements.txt /app
RUN pip install -r requirements.txt
COPY . .
# Set environment variables
ENV REDIS_HOST=redis
ENV REDIS_PORT=6379

EXPOSE 80
# ENV FLASK_APP=app.py
CMD ["flask", "run", "--host=0.0.0.0", "--port=80"]