# Javaを活用したマイクロサービスのためのKubernetes活用

## メモ

### Java
- Java9以降:カスタムJREの作成
  - 小さいコンテナを作成するのに重要となる
- JDK10以降におけるコンテナ対応の改善
- JDK11で削除されたパッケージ一覧
  - web Services系の設定がデフォルトから抜けた
    - Maven Centralからライブラリを取ってきて依存関係解決
  - 早めに試す
- 今のトレンド(機能)を利用することができる(リリースの期間の短縮)

### Docker
- latest tagは絶対使用しない
  - どのバージョンのものをビルドか分からなくなる
- タグにはBuildidを付ける
- 小さなサイズのイメージを作る
  - 小さなイメージを使う
- LIGHT4j
  - 内部
  - httpのサーバを独自に実装
  - 軽量でパフォーマンスが良い
- DockerHubのイメージは安全かを確認する

### Kubernetes
- Azureでのコンテナ化
- 類似
  - Web App for container
  - Function(serverless)
  - OPENSHIFT
  - Pivotal Cloud Foundary
- Serverless
  - code + (Event + data)
- k8sの進化は速い
- 本番環境は考えることが多い
- 全てのk8sの機能を利用する必要はない
  - J2EEと近いところがある
- 複雑な構成を作らない
  - 運用構成を変えればできること無理してk8sでしない
- 大規模クラスタを作らない
  - ノード数を多く作らない
  - Kubernetesもメンテナンスが必要
  - クラスタが死んだらその上に乗っているコンテナは全て死ぬことも考える
- 本番環境の設定ファイルには多くの設定が必要
  - 公式ドキュメントから環境にあった設定が必要
- Label & Selctorの理解は重要
  - LBの振り分けをSelectorで行う
- Persistence Volumeの使い所について
  - SDKを使用したファイル保存・更新機能実装のススメ 
- VNet経由でManaged DBの利用のススメ
  - マネージドのDBを利用する
- バージョンアップ
  - 簡単にローリングアップデート可能だが絶対にやらない
    - 新しいバージョンにした場合、古い設定は動かない可能性あり
    - 3rdPartyの利用も注意が必要
    - 新しいクラスタを構築し、今動いている環境のものを構築クラスタに持っていく。その後振り分け
    - rback
    - 本番環境を触れる人を物理的に絞る
- 問題が発生したとき
  - kubectl describe pod
  - kubectl logs POD_NAME
  - kubectl exec -it POD_NAME /bin/sh
  - kubectl get events -w
  - Deploy Ubuntu POD

  - 英語のIssueを読む
- VSCODEでリモートデバッグが可能
- Virtual Kubelet Serverless
  - 一番下のVMは
  - PODを動かしているノード
- Azule DevOpts
  - 看板ボード
  - CIのパイプライン
  - CDのパイプライン
  - privateのMaven Repository

### その他
- https://github.com/yoshioterada
- 