# try-kube!
## 備忘
### emptyDir
Pod用の一時的なディスク領域。PodがTerminateされると削除される。ホスト上の領域をマウントするわけではない。
### hostPath
Kubernetes Node上の領域をコンテナにマッピングする。
- type
    - Directory
    - DirectoryOrCreate
    - File
    - Socket
    - BlockDevice
### downwardAPI
Podの情報などをファイルとして配置するためのプラグイン。
### projected
Secret / ConfigMap / downwardAPI / serviceAccountToken のマウントボリュームを1か所のディレクトリに集約する。