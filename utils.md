# Default Tolerations Namespace

    kind: Namespace
    apiVersion: v1
    metadata:
      name: openshift-marketplace
      annotations:
        scheduler.alpha.kubernetes.io/defaultTolerations: >-
          [
            {
              "key": "node-role.kubernetes.io/infra",
              "operator": "Exists",
              "effect": "NoSchedule"
            },
            {
              "key": "node.k8s.bb/servico",
              "operator": "Equal",
              "value": "psc-nodes-infra",
              "effect": "NoSchedule"
            }
          ]
