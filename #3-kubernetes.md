# IBM CloudとKubernetesでSpring Bootのマイクロサービスを簡単に!

## メモ

### IBMクラウドを用いたKubernetes

以下のイメージを持てばわかりやすい
- コンテナ
  - 船

- オーケストレーション
  - 舵

- Kubernetesを利用することで素早くテスト環境やアプリケーション環境にデプロイ可能
- rollbackやupgradeを止めずに行うことが可能

### コンポーネント
今回の構成の図

![](./images/IMG_0412.jpg)


- IBM Cloud Kubernetes ...

#### 事前準備
- Kubernetesでクラスタを作成しておく(Minikube, ICP, IKD)

#### 手順
- リポジトリClone
  - (https://github.com/IBM/spring-boot-microservices-on-kubernetes)
- IBM Cloud Kubernetesでクラスタ作成（15分程度）
- データベースサービス作成
- Spring Bootアプリビルド
- Dockerイメージを作成&push
- Kubernetes
  - アプリケーション用のyamlを編集
    - container要素
      - image
- デプロイ
- アプリ動作確認
  - public IP
    - ibmcloud cs workers <クラスタ名>
  - port
    - kubectl get service <account-summary>



### その他
- IBM Cloudの初期アカウントはクレジットカードは不要(無料で利用可能)
- クラスタ1つであれば、フリークラスタを利用すれば無料で利用可能
- 東京リージョンあり
