# Machine Learning Notes

機械学習初心者（私）が、機械学習の初歩を学ぶためのリポジトリです。記載内容の誤り（認識違い）の指摘は大歓迎です。

## ディレクトリ構成

```shell
machine-learning-notes
├── LICENSE
├── README.md
├── datasets  ※ 分析対象データセット（ライセンスは、データ公開元のライセンスに準じる）
├── main.py
├── mlops     ※ ML Opsに関する知見の格納場所
├── notebooks ※ datasets を分析するための Jupyter Notebooks
├── notes     ※ 機械学習を学ぶ上で必要な基礎知識の格納場所
│   ├── math
│   └── ml
├── pyproject.toml
├── scripts
│   ├── datasets
│   └── download_datasets.py ※ 全データセットを一括で取得するエントリポイント
└── uv.lock
```

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

Kaggle のデータセット取得には、個人の API トークンが必要です。このリポジトリにはトークンは含まれていません。

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
