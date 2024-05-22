helm repo add rook-release https://charts.rook.io/release
helm install --create-namespace --namespace rook-ceph rook-ceph rook-release/rook-ceph -f values.yaml

kubectl-namespace rook-ceph roget pods -l "app=rook-ceph-operator" 

 helm upgrade --install --namespace rook-ceph rook-ceph rook-release/rook-ceph --version 1.14.4 --wait



helm install --create-namespace --namespace rook-ceph rook-ceph-cluster \
   --set operatorNamespace=rook-ceph rook-release/rook-ceph-cluster -f values.yaml

kubectl --namespace rook-ceph get cephcluster





umount /dev/sdb
sudo wipefs -a /dev/sdb
