# Asteria - C Language Interpreter & Execution Visualizer

Asteriaは、C言語ソースコードの構文解析および実行シミュレーションを行い、プログラム実行過程の詳細な可視化を提供するソフトウェアである。

本システムは、メモリ管理、ポインタ操作、関数呼び出し機構等のC言語における低レベル動作を段階的に表示することにより、言語仕様の理解を支援する。

---

## 機能概要

### 実行制御
- ステップ単位での実行制御機能
- 実行位置のリアルタイム表示
- ユーザー入力による実行フロー制御

### 状態監視機能
以下の内部状態を段階的に表示する：

- **シンボルテーブル管理**: 変数および関数の定義情報
- **メモリ空間監視**: アドレス割り当てと値の対応関係
- **実行出力記録**: 標準出力への書き込み内容

### 言語機能対応
- 基本データ型（int, char, float, double）
- 算術・論理・比較演算子
- 制御構文（条件分岐、反復処理）
- 関数定義および呼び出し機構
- ポインタおよびアドレス演算
- 配列操作（一次元配列）
- 標準入出力関数（printf, scanf）

## システム要件

### 動作環境
- オペレーティングシステム: Microsoft Windows
- アーキテクチャ: x86-64

### 依存関係
- LLVM/Clang ツールチェーン
  - libclang.dll の可用性が必須
  - 推奨バージョン: LLVM 15.0 以上
  - インストール時にシステムPATHへの追加を要する

### LLVM導入手順
1. [LLVM公式配布サイト](https://releases.llvm.org/download.html)より適切なバイナリを取得
2. インストーラー実行時に「Add LLVM to the system PATH」オプションを有効化
3. システム再起動により設定を反映

## 実行手順

### バイナリ実行
```
Asteria.exe [ソースファイルパス]
```

### 実行例
```
Asteria.exe sample_program.c
```

### 操作方法
- Enter: 次ステップへの遷移
- q + Enter: プログラム終了

### 引数省略時の動作
引数未指定時は内蔵されたデフォルトプログラムが実行される。

## 開発者向け情報

### ソースコードからの実行
```bash
git clone https://github.com/[username]/[repository].git
cd [repository]
python -m venv venv
venv\Scripts\activate
pip install clang
python Asteria.py [ソースファイル]
```

### 技術仕様
- 実装言語: Python 3
- 解析エンジン: libclang (LLVM Project)
- 配布形式: PyInstaller生成バイナリ

