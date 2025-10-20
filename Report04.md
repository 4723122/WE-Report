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
