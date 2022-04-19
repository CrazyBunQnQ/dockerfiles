# nginx镜像
FROM arm32v7/nginx:1.17.8
# 维护者信息
MAINTAINER CrazyBunQnQ "crazybunqnq@gmail.com"

# 设置镜像时区环境变量
ENV TZ=Asia/Shanghai
# 给app.sh赋予可执行权限, 并设置时区
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone