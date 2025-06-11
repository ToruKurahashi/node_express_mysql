FROM mcr.microsoft.com/devcontainers/base:ubuntu

# MySQLインストール
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y mysql-server && \
    rm -rf /var/lib/apt/lists/*

# MySQL設定
RUN echo "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';" > /tmp/init.sql && \
    chmod +x /tmp/init.sql

# MySQLが起動する状態でコンテナに入るための設定
RUN mkdir -p /var/run/mysqld && \
    chown -R mysql:mysql /var/run/mysqld && \
    chmod 755 /var/run/mysqld
