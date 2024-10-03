---
title: paizaでPythonを使う時の備忘録（適宜更新）
tags:
  - Python
  - 初心者
  - paiza
  - 競技プログラミング
private: false
updated_at: '2024-10-03T13:56:06+09:00'
id: 4ec29f2ecad5f637334c
organization_url_name: null
slide: false
ignorePublish: false
---
# 入力
## 入力値を整数を整数に変換して取得
```python
n = int(input())
```
## 複数の値を取得
```python
a,b=input().split()
```
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
## 入力で複数の値をリスト形式で取得し、int型に変換
```python
price_list = list(map(int, input().split()))
```