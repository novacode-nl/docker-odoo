FROM ubuntu:18.04

RUN apt-get update

RUN apt-get -qq install python3 python3-pip python3-pip postgresql-client wget gdebi-core libpq-dev libjpeg-dev libxml2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev libssl-dev iptables

# FIXME Crash on node-gyp. Needed for Odoo/Enterprise ?
# nodejs npm node-clean-css node-less
# RUN npm install -g less
# RUN npm install -g less-plugin-clean-css

RUN pip3 install num2words ofxparse

# Wkhtmltopdf
RUN wget -q https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.bionic_amd64.deb
RUN gdebi --n wkhtmltox_0.12.5-1.bionic_amd64.deb
RUN ln -s /usr/local/bin/wkhtmltopdf /usr/bin
RUN ln -s /usr/local/bin/wkhtmltoimage /usr/bin

# Maybe usermapping required?
# RUN useradd odoo