FROM python:3.9-alpine
WORKDIR /usr/src/app
COPY requirements.txt ./
# COPY entry_point.sh /usr/local/bin/
RUN pip install -r requirements.txt
#!/bin/sh
RUN python manage.py makemigrations
RUN python manage.py migrate
RUN python manage.py migrate --fake sessions zero
RUN python manage.py migrate --fake-initial
RUN python manage.py shell < init_admin.py
RUN python manage.py makemigrations app
RUN python manage.py migrate app
RUN python manage.py runserver 0.0.0.0:8000
COPY . .
# RUN chmod +x entry_point.sh
# ENTRYPOINT [ "./entry_point.sh" ]
