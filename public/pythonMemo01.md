---
title: paizaでPythonを使う時の備忘録（適宜更新）
tags:
  - Python
  - 初心者
  - paiza
  - 競技プログラミング
private: false
updated_at: '2024-10-05T23:40:50+09:00'
id: 4ec29f2ecad5f637334c
organization_url_name: null
slide: false
ignorePublish: false
---
# 入力
## 入力値を整数（int型）に変換して取得
```python
n = int(input())
```
## 複数の値を取得
```python
a,b=input().split()
```
split関数は**半角スペース、タブ、改行**で文字列を分割することができる。
## 複数の値を取得し、int型に変換
```python
n, l = map(int, input().split())
```
## 1行ずつ配列に入れる
```python
rounds_list = [input() for i in range(n)]
```
## 入力の行数が不明な場合：値を1行ずつ配列に入れる
```python
import sys
a = []
for l in sys.stdin:
    a.append(int(l))
```
### sysモジュール
- Pythonの標準ライブラリ、Pythonのインタプリタと対話するための機能を提供
### sys.stdin
- 入力を読み取るために使う
### append()
- リスト（配列）に新しい要素を追加するためのメソッド
- リストの**最後**に1つの要素を追加する
## 入力で複数の値をリスト形式で取得し、int型に変換
```python
price_list = list(map(int, input().split()))
```
# 配列の処理
## ループ処理
```python
fruits = ['みかん', 'りんご', 'ぶどう']
for fruit in fruits:
    print(fruit) 
```
**出力**
```
みかん
りんご
ぶどう
```
## 要素の合計
### for文を使ったやり方
```python
list_1 = [1,2,4,8]
total = 0

for n in list_1:
    total += n

print(total) 
# 出力：15
```
### sum()関数を使ったやり方
```python
list_1 = [1,2,4,8]
total = sum(list_1)

print(total)

# 出力：15
```
sum()関数を使うと簡単に合計を求めることができる。
## 最大値を取得するmax()関数
引数の値の中から最大値を返す
### リストの最大値を取得
```python
numbers = [10, 20, 30, 40]
max_value = max(numbers)
print(max_value)

# 出力：40
```
### key引数を用いて、特定の条件で最大値を取得
```python
words = ["apple", "banana", "cherry"]
longest_word = max(words, key=len)  # 最も長い単語を取得
print(longest_word)

# 出力：banana
```
# 文字列の処理
## 任意の文字列の置き換え、削除ができるreplace()関数
```python
s = 'aokidai'

s = s.replace('ai', '')
print(s)
# 出力：aokid
```
- 空文字列に置き換えすると削除される
## 辞書形式を用いたreplace関数による文字列の置き換え
```python
s = 'aokidai'

# 文字置換用の辞書
replace_map = {
    'a': '4',
    'o': '0',
    'k': '6',
    'i': '1',
}

# 辞書に基づいて文字を置換
for char, replacement in replace_map.items():
    s = s.replace(char, replacement)

print(s)
# 4061dai
```
- replace_map.items() は辞書のキーとバリューを取り出す
  - charはキー（置き換えされる元の文字）
  - replacementはバリュー（置き換え後の文字）
## 正規表現を使って文字列を置き換え、削除ができるre.sub()関数
```python
import re

s = 'aokidai'

# 正規表現を使って、母音（大文字・小文字）を一度に削除
s = re.sub(r'[aeiouAEIOU]', '', s)

print(s)
# 出力：kd
```
### 正規表現について
参照：https://www.megasoft.co.jp/mifes/seiki/meta.html
## 文字列の長さを取得するlen()関数
```python
s = 'aokidai'
print(len(s))
# 7
```
## 文字列の連結
```python
m = 'aoki'
n = 'dai'

m += n
print(m)
# aokidai
```
## 文字列の部分一致
```python
print('dai' in 'aokidai')
# True
```
## 文字列の中の特定の文字を抽出
```python
s = 'aokidai'

print(s[0])
# a
```
