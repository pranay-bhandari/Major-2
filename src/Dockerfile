FROM python:3.9-alpine
WORKDIR /usr/src/app
COPY requirements.txt ./
# COPY entry_point.sh /usr/local/bin/
RUN pip install -r requirements.txt
COPY . .
RUN chmod +x entry_point.sh
ENTRYPOINT [ "./entry_point.sh" ]
