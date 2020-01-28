FROM python:3.7
WORKDIR /usr/src/server
ADD packagelist.txt .
# コンテナ内にProxyを設定
ENV http_proxy http://sg-sd27b-1.isid.co.jp:8080
ENV https_proxy http://sg-sd27b-1.isid.co.jp:8080
# packagelist.txtにリストされたパッケージをインストールする
RUN pip install --trusted-host pypi.python.org -r packagelist.txt
# コンテナ起動後、FastAPIを実行し8000ポートで待機
CMD ["uvicorn", "main:app", "--reload", "--host", "0.0.0.0", "--port", "3000"]