FROM nginx:1.31

# 必要なツールをインストール
RUN apt-get update && apt-get install -y wget tar

# alpのインストール (例: v1.0.21 の amd64 版)
RUN wget https://github.com/tkuchiki/alp/releases/download/v1.0.21/alp_linux_arm64.tar.gz && \
    tar -xvzf alp_linux_arm64.tar.gz && \
    mv alp /usr/local/bin/ && \
    rm alp_linux_arm64.tar.gz

# デフォルトのシンボリックリンクを削除し、通常のファイルとして初期化する
RUN rm -f /var/log/nginx/access.log && \
    touch /var/log/nginx/access.log && \
    chown nginx:nginx /var/log/nginx/access.log
