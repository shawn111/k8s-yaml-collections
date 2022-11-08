helm template prometheus prometheus-community/prometheus  | tee config.yaml


kbld -f prometheus.yaml --imgpkg-lock-output bundle/.imgpkg/images.yml

rebuild yaml
kbld -f prometheus.yaml -f bundle/.imgpkg/images.yml > bundle/config.yml



imgpkg  push -b 127.0.0.1:43053/shawn111/promethe-bundle:v0.0.1 -f promethe/
