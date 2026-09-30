

    ```
    cd <fdo-pri-src>/component-samples/demo/scripts
    bash demo_ca.sh
    bash web_csr_req.sh
    bash user_csr_req.sh
    ./keys_gen.sh
    echo | openssl s_client -proxy ${https_proxy_host}:${https_proxy_port} -showcerts -connect fdorv.com:443 2>/dev/null | sed -n '/-----BEGIN CERTIFICATE-----/, /-----END CERTIFICATE-----/p' >> ./secrets/ca-cert.pem
    cp -r ./secrets/. ../<component>
    cp service.env ../<component>
    ```

