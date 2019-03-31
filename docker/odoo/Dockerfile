FROM ubuntu:18.04

RUN apt-get update

RUN apt-get -qq install postgresql-client
RUN apt-get -qq install python3 python3-pip wget python3-pip gdebi-core libpq-dev libjpeg-dev libxml2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev libssl-dev

# FIXME Crash on node-gyp. Needed for Odoo/Enterprise ?
# nodejs npm node-clean-css node-less
# RUN npm install -g less
# RUN npm install -g less-plugin-clean-css

RUN pip3 install num2words ofxparse

# Maybe usermapping required?
# RUN useradd odoo