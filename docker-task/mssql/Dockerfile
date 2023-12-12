
FROM mcr.microsoft.com/mssql/server:2017-CU17-ubuntu

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY . /usr/src/app

RUN chmod +x /usr/src/app/run-init.sh

ENV SA_PASSWORD=Un!q@to2023

ENV ACCEPT_EULA=Y

ENV MSSQL_PID=Developer

EXPOSE 1433

CMD /bin/bash ./entrypoint.sh