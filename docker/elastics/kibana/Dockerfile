FROM docker.elastic.co/kibana/kibana:7.3.1

# plugins setup
RUN kibana-plugin install https://github.com/bitsensor/elastalert-kibana-plugin/releases/download/1.1.0/elastalert-kibana-plugin-1.1.0-7.3.1.zip \
    && kibana-plugin install https://github.com/fbaligand/kibana-enhanced-table/releases/download/v1.4.3/enhanced-table-1.4.3_7.3.1.zip
