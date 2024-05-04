## プログラミング全般のTipsについて
## 対象項目
- 使用頻度がプロジェクト毎かつ毎回ググって調べてるもの
- 毎回忘れてしまうコマンド
- インストールに手間取ったパッケージのやり方
- 上記はChatGPT先輩に聞けば良いかもしれないが、自身の振り返り用として記録する
- 今後リポジトリの構成や章立て構成は変更する可能性は高い
## 内容
- タイトルは”やりたい事”を簡潔に表現したフレーズ
### Condaの操作全般
#### パッケージのインストール
- wget<br>
```conda install -c conda-forge python-wget```
#### 仮想環境の構築
- Pythonのバージョン指定あり
```conda create -n <vir_env> python=3.X```

#### 新規カーネルの追加
- 新たに作成した仮想環境<vir_env>に入り以下のコマンドを実行する<br>
```conda install -c conda-forge ipykernel```<br>
```ipython kernel install --user --name <vir_env>```

- カーネルリストの確認<br>
```jupyter kernelspec list```

- カーネルの削除
```jupyter kernelspec uninstall <KERNEL_NAME>```

#### 仮想環境の保存、再構築 
- 参考にした記事 : [Qiita](https://qiita.com/ozaki_physics/items/13466d6d1954a0afeb3b)
- 仮想環境のファイルへの保存
    - `conda env export > ファイル名.yml`
- 仮想環境の再構築
    - ymlファイルを保存したディレクトリで次のコマンドを実行する<br>
     `conda env create -n 新たな環境名 -f ファイル名.yml`
    - 再構築には時間がかかる。

- その他
  - ymlファイルへ出力後に確認すること
    - name:<"create new env name">として、ファイル名をこれに合わせる。
  - ymlファイルに記述するパッケージ名は必要最低限にする。なぜならパッケージ間の依存関係はconda側で解決してくれるから。
  - バージョンの後ろのハッシュ値を削除する。
  - prefixを削除する。