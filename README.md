# cloud-native-OAM-builder

#### You should have the following before getting started with the operate
1.A running Kubernetes cluster.
2.The Kubernetes cluster API endpoint should be reachable from the machine you are running helm.
3.Authenticate the cluster using kubectl and it should have cluster-admin permissions.

**Infra charts operate**
cd /root
git clone git@github.com:XGVela/cloud-native-OAM-builder.git
helm install oam-infra /root/cloud-native-OAM-builder/charts -n oam-system
helm uninstall oam-infra -n oam-system
helm upgrade oam-infra /root/cloud-native-OAM-builder/charts -n oam-system


**oam charts operate**
cd /root
git clone git@github.com:XGVela/cloud-native-OAM-builder.git
helm install oam-network /root/cloud-native-OAM-builder/oam-charts -n oam-system
helm uninstall oam-network -n oam-system
helm upgrade oam-network /root/cloud-native-OAM-builder/oam-charts -n oam-system
