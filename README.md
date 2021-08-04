# ติดต้อง NGINX Open Source รุ่นล่าสุดใน Ubuntu 20.04

1. sudo apt install curl gnupg2 ca-certificates lsb-release
2. echo "deb http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list
3. echo "deb http://nginx.org/packages/mainline/ubuntu `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list
4. echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
    | sudo tee /etc/apt/preferences.d/99nginx
5. curl -o /tmp/nginx_signing.key https://nginx.org/keys/nginx_signing.key
6. sudo mv /tmp/nginx_signing.key /etc/apt/trusted.gpg.d/nginx_signing.asc
7. sudo apt update
8. sudo apt install nginx
