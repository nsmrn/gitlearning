# ブランチをマージする(git merge)
想定するブランチ構成。以下では ```develop``` ブランチの変更を ```main``` ブランチに取り込む例。  

```sh
# *がついているのが現在のブランチ
#  origin/main -o
#  main        -o
# *develop      └-o <- このコミットを取り込む
```

1. mainブランチに切り替える（取り込みのベース側
```sh
# git checkout <切り替え先ブランチ名>
git checkout main

# *がついているのが現在のブランチ
#  origin/main -o
#  *main       -o
#  develop      └-o
```
2. リモートリポジトリの最新状態を取得する
```sh
# git pull <リモート名> <ブランチ名>
git pull origin main
#  origin/main -o <- mainと一致しているため変化なし
#  *main       -o
#  develop      └-o
```
3. developブランチをmainブランチにマージ
```sh
# git merge <取り込み対象ブランチ名>
git merge develop

# *がついているのが現在のブランチ
# origin/main -o
# *main       -o---o
# develop      └-o-┘
```
4. リモートリポジトリにマージ結果をpush
```sh
# git push <リモート名> <ブランチ名>
git push origin main

# *がついているのが現在のブランチ
# origin/main -o---o
# *main       -o---o
# develop      └-o-┘
```
