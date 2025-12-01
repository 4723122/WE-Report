# 第9回 Webエンジニアリング演習 レポート
## 学籍番号
4723122

## frontend/calculator.tsのプログラム
```
function add(a: number, b: number): number {
    return a + b;
}

const multiply = (a: number, b: number): number => {
    return a * b;
}

export { add, multiply };
```

##動作確認結果
```
@4723122 ➜ /workspaces/WE-TypeScript/frontend (main) $ node main.js
5 + 3 = 8
5 * 3 = 15
```
