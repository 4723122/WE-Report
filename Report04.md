# 第4回　Webエンジニアリング演習　レポート
## 4723122

##実装したプログラム
import sys
import json

books = [
    {
        "title": "Java基礎",
        "author": "佐藤花子",
        "year": 2023,
        "isbn": "978-4-987654-32-1",
        "price": 2800
    },
    {
        "title": "Web開発",
        "author": "山田次郎",
        "year": 2023,
        "isbn": "978-4-111111-11-1",
        "price": 3200
    }
]

new_book = sys.argv[1] #引数のうち必要な方を取り出す
new_book_data = json.loads(new_book) #json形式に変換（辞書型として扱えるようにする
books.append(new_book_data) #booksのDBに追加

count = 0
for book in books: #ループ処理で本の一覧を出力
    count += 1
    print(f"{count}. {book['title']} - {book['author']} ({book['year']}) ISBN: {book['isbn']} 価格: {book['price']}円")


## 実行結果
@4723122 ➜ /workspaces/WE-Python (main) $ python book_manager.py "{ \"title\": \"Python\", \"author\": \"田中太郎\", \"year\": 2024, \"isbn\": \"987-4-123456-78-9\", \"price\": 2500 }"
1. Java基礎 - 佐藤花子 (2023) ISBN: 978-4-987654-32-1 価格: 2800円
2. Web開発 - 山田次郎 (2023) ISBN: 978-4-111111-11-1 価格: 3200円
3. Python - 田中太郎 (2024) ISBN: 987-4-123456-78-9 価格: 2500円

@4723122 ➜ /workspaces/WE-Python (main) $ git add .
@4723122 ➜ /workspaces/WE-Python (main) $ git commit -m "add Re4"
[main 882770a] add Re4
 6 files changed, 51 insertions(+)
 rename Dockerfile => .devcontainer/Dockerfile (100%)
 rename devcontainer.json => .devcontainer/devcontainer.json (100%)
 rename {library-scripts => .devcontainer/library-scripts}/common-debian.sh (100%)
 rename {library-scripts => .devcontainer/library-scripts}/docker-in-docker-debian.sh (100%)
 create mode 100644 book_manager.py
 create mode 100644 main.py
@4723122 ➜ /workspaces/WE-Python (main) $ git push -u origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 2 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.01 KiB | 1.01 MiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/4723122/WE-Python
   51a2c48..882770a  main -> main
branch 'main' set up to track 'origin/main'.
