- vim heketi-secret.yaml
    ``` yaml
    apiVersion: v1
    kind: Secret
    metadata:
      name: heketi-secret
      namespace: default
    data:
      # base64 encoded password. E.g.: echo -n "mypassword" | base64
      key: YWRtaW5AMTIz
    type: kubernetes.io/glusterfs
    ```
