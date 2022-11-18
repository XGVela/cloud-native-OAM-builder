# cloud-native-OAM-builder

For newest installation guide, please go to https://github.com/XGVela/cloud-native-OAM/blob/main/docs/Installation_guide.md

Cloud-native-OAM-builder provide packages of all cloud native OAM functions.

---
**To start deployment, you should check your environment and build images of all cloud native OAM functions.**

1.A running Kubernetes cluster.

2.The Kubernetes cluster API endpoint should be reachable from the machine you are running helm.

3.Authenticate the cluster using kubectl and it should have cluster-admin permissions.

4.Get images of each cloud native OAM functions created and loaded into cluster registry.

---
**Deploy cloud native OAM relied General PaaS functions**

Within [cloud-native-OAM-builder/charts](https://github.com/XGVela/cloud-native-OAM-builder/oam-basic), it lists the helm charts of all relied General PaaS functions, which are required by other cloud native OAM Telco PaaS functions. To deploy those Telco PaaS functions, these General PaaS functions should be deployed first using the following command.

```bash
cd /root
git clone git@github.com:XGVela/cloud-native-OAM-builder.git
helm install oam /root/cloud-native-OAM-builder/oam-basic -n oam-system
helm uninstall oam -n oam-system
helm upgrade oam /root/cloud-native-OAM-builder/oam-basic -n oam-system
```

---
**Deploy cloud native OAM Telco PaaS functions**

Within [cloud-native-OAM-builder/oam-charts](https://github.com/XGVela/cloud-native-OAM-builder/oam-network), it contains helm charts of all cloud native OAM Telco PaaS functions.

```bash
cd /root
git clone git@github.com:XGVela/cloud-native-OAM-builder.git
helm install oam-network /root/cloud-native-OAM-builder/oam-network -n oam-system
helm uninstall oam-network -n oam-system
helm upgrade oam-network /root/cloud-native-OAM-builder/oam-network -n oam-system
```
