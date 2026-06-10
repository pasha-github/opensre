FROM nginx:alpine

# Copy the Tier 3 demo as the default page
COPY 1FFC_ComplaintPortal_Tier3.html /usr/share/nginx/html/index.html

# Lightweight nginx config — no caching for demo use
RUN printf 'server {\n\
    listen 80;\n\
    root /usr/share/nginx/html;\n\
    index index.html;\n\
    add_header Cache-Control "no-store";\n\
    add_header X-Frame-Options "SAMEORIGIN";\n\
    location / { try_files $uri $uri/ /index.html; }\n\
}\n' > /etc/nginx/conf.d/default.conf

EXPOSE 80
