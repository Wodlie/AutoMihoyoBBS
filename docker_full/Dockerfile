FROM python:3-alpine
LABEL maintainer="x.yangtze.river@gmail.com"

ENV CRON_SIGNIN='30 9 * * *'
ENV MULTI=TRUE
ENV TZ=Asia/Shanghai
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories \
	&& apk add --no-cache tzdata git

RUN git clone https://github.com/Womsxd/AutoMihoyoBBS app
WORKDIR /app
RUN pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt 

CMD ["python3", "./docker.py" ]


#挂载本地 config文件夹 到 /app/config 下
