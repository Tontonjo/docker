# Tonton Jo - 2020
# Join me on Youtube: https://www.youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw

Please put your certificate here if using https in .pem format and controle they are correctly setted up in nginx.conf

you can generate a self-signed certificate - edit -days, -keyout and -out to fit your needs:
"openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certificate.pem"
