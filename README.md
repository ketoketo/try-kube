# try-kube!
## コマンド備忘
### node確認
```
kubectl get nodes
```
### node確認(詳細)
```
kubectl describe node n0
```
### pod確認(全namespace)
```
kubectl get pods --all-namespaces -o wide
```
### pod確認(詳細)
```
kubectl describe pod sample-pod
```
### マニュフェスト適用
```
kubectl apply -f sample-pod.yaml
```
### podのコンテナに入る
```
kubectl exec -it sample-pod -c nginx-container /bin/sh
```
### podのコンテナでコマンド実行
```
kubectl exec -it sample-pod -- /bin/ls -l /tmp/
```
### podのログ確認
```
kubectl logs sample-pod
kubectl logs -f sample-pod
```
### podのコンテナからファイルコピー
```
kubectl cp sample-pod:/etc/hostname .
```
### podのコンテナをポートフォワードで接続
```
kubectl port-forward sample-pod 8888:80
```
### kubectlのデバッグ
```
kubectl -v=6 get pod
kubectl -v=8 apply -f sample-pod.yaml
```
### ReplicaSetの一覧を表示
```
kubectl get replicasets
```
### Deploymentの確認
```
kubectl get deployments
```
### Deploymentのスケーリング
```
kubectl scale deployment sample-deployment --replica=5
```
### serviceの確認
```
kubectl get service
```
### podとIPの確認
```
kubectl get nodes -o custom-columns="NAME:{metadata.name},IP:{status.addresses[].address}"
```
### 一時的にテストPod起動
```
kubectl run --image=centos:6 --restart=Never --rm -it testpod bash
```