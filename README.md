# Machine Learning Notes

機械学習初心者（私）が、機械学習の初歩を学ぶためのリポジトリです。記載内容の誤り（認識違い）の指摘は大歓迎です。

## ディレクトリ構成

```shell
machine-learning-notes
├── LICENSE
├── README.md
├── datasets  ※ 分析対象データセット（ライセンスは、データ公開元のライセンスに準じる）
├── main.py
├── notebooks ※ datasets を分析するための Jupyter Notebooks
├── notes     ※ 機械学習を学ぶ上で必要な基礎知識の格納場所
│   ├── math
│   ├── ml
│   └── mlops
├── pyproject.toml
├── scripts
│   ├── datasets
│   └── download_datasets.py ※ 全データセットを一括で取得するエントリポイント
└── uv.lock
```

## コンテンツ

| No. | 分類 | 項目名 |
| --- | --- | --- |
| 1 | Notebooks | [クレカ不正検出](./notebooks/credit-card-fraud/credit-card-fraud.ipynb) |
| 2 | Mathematics | [平均（算術平均）](notes/math/mean/mean.md) |
| 3 | Mathematics | [中央値（メジアン）](notes/math/median/median.md) |
| 4 | Mathematics | [四分位点（quartile）](notes/math/quantile/quantile.md) |
| 5 | Mathematics | [分散（バリアンス）](notes/math/variance/variance.md) |
| 6 | Mathematics | [標準偏差](notes/math/stddev/stddev.md) |
| 7 | Mathematics | [歪度（skewness）と log1p 変換](notes/math/skewness/skewness.md) |
| 8 | Mathematics | [カーネル密度推定（KDE）](notes/math/kde/kde.md) |
| 9 | Mathematics | [相関係数](notes/math/correlation/correlation.md) |
| 10 | Machine Learning | [PCA - Principal Component Analysis](notes/ml/pca/pca.md) |
| 11 | Machine Learning | [k-means - K-means／k平均法](notes/ml/k-means/k-means.md) |
| 12 | ML Ops | [作成中](notes/mlops/) |

## 実行環境の構築
### 前提条件

- Python 3.12 以上
- uv（Python パッケージ・環境管理ツール）
- Visual Studio Code　※ Jupyter Notebook で代用も可能
  - Microsoft が提供している [Jupyter Extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) を利用
- Kaggle アカウント
  - Kaggle API トークンを発行し、`~/.kaggle/kaggle.json` に配置済みであること
  - ※ トークンの取得方法は [Kaggle 公式ドキュメント](https://www.kaggle.com/docs/api)を参照してください

### パッケージのインストール

python, uv, VS Code は、別途インストールしてください。以下のコマンドを実行すると、依存パッケージがインストールされます。

```bash
uv sync
```

### 利用する Python の指定

VS Code上で Ctrl + Shift + P → Python: Select Interpreter　を選択し、`.venv/bin/python`を選択してください。

### Kaggle API トークンについて

Kaggle のデータセット取得には、個人の API トークンが必要です。

以下の手順で取得してください：

1. Kaggle にログイン
2. Account Settings → API → Create New Token
3. ダウンロードした `kaggle.json` を `~/.kaggle/` に配置
4. パーミッションを600に制限

### データセットのダウンロード

データセットは、100MBを超えるファイルが多く、GitHub にアップロードできません。正確には、Git LFS を利用すればアップロード可能ですが、無料枠に収まらない見込みです。

以下のコマンドで、データセットをダウンロードしてください。

```shell
uv run python scripts/download_datasets.py
```


## ライセンス

[MIT LICENSE](./LICENSE)

※ 分析に利用するデータセットは、オリジナルデータ公開元のライセンスに従います。

## 参考文献（手元にある書籍リスト）

- [事例で学ぶ特徴量エンジニアリング](https://www.oreilly.co.jp/books/9784814400546/)
- [The Kaggle Book:データ分析競技 実践ガイド&精鋭31人インタビュー](https://tatsu-zine.com/books/the-kaggle-book?srsltid=AfmBOoobOipbs54pBtZ8BKMQmcDf4YqXRjvehImAmftPz2u6s6RUEJpz)
- [見て試してわかる機械学習アルゴリズムの仕組み 機械学習図鑑](https://www.shoeisha.co.jp/book/detail/9784798155654)
- [MLOps実装ガイド 本番運用を見据えた開発戦略](https://www.oreilly.co.jp/books/9784814401208/)
- [仕事ではじめる機械学習 第2版](https://www.oreilly.co.jp//books/9784873119472/)
- [機械学習システムデザイン 実運用レベルのアプリケーションを実現する継続的反復プロセス](https://www.oreilly.co.jp/books/9784814400409/)
- [楽しみながら学ぶベイズ統計](https://www.sbcr.jp/product/4815604745/)
- [データサイエンスのための数学入門 Pythonで学ぶ線形代数、確率、統計の基礎](https://www.oreilly.co.jp/books/9784814401260/)
- [「原因と結果」の経済学 データから真実を見抜く思考法](https://www.diamond.co.jp/book/9784478039472.html)
- [Pythonで学ぶあたらしい統計学の教科書](https://www.shoeisha.co.jp/book/detail/9784798155067)
- [前処理大全](https://gihyo.jp/book/2018/978-4-7741-9647-3)
- [戦略的データサイエンス入門―ビジネスに活かすコンセプトとテクニック](https://www.oreilly.co.jp/books/9784873116853/)
- [ゼロから作るDeep Learning―Pythonで学ぶディープラーニングの理論と実装](https://www.oreilly.co.jp/books/9784873117584/)
