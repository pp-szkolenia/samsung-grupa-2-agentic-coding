FROM nginx:1.27-alpine

COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY index.html claude-code-commands.json /usr/share/nginx/html/
COPY schemas/ /usr/share/nginx/html/schemas/
COPY examples/ /usr/share/nginx/html/examples/
