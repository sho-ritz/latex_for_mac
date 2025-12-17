# LaTeX環境の設定

## 概要
このプロジェクトは日本語LaTeX文書（`jreport2.cls`使用）で、JY1エンコーディングスキームを必要とします。

## 設定内容

### 使用するLaTeXエンジン
- **platex** (e-pTeX) - JY1エンコーディングを使用
- **uplatex**は使用しない - JY2エンコーディングのため`jreport2.cls`と互換性がありません

### ファイル構成
- `.latexmkrc` - プロジェクト固有のlatexmk設定
- `.vscode/settings.json` - VS Code LaTeX Workshop設定
- `out/` - コンパイル出力ディレクトリ

### コンパイル方法

#### コマンドライン
```bash
# 基本的なコンパイル
latexmk -pdfdvi main_YOURNAME_paper20XX.tex

# クリーンビルド
rm -rf out && latexmk -pdfdvi main_YOURNAME_paper20XX.tex

# 強制コンパイル（エラーがあっても続行）
latexmk -pdfdvi -f main_YOURNAME_paper20XX.tex
```

#### VS Code
1. `.tex`ファイルを保存すると自動コンパイル
2. `Cmd+K V`でPDFプレビューを表示
3. コマンドパレット → "LaTeX Workshop: Build LaTeX project"

## 出力
- DVI: `out/main_YOURNAME_paper20XX.dvi`
- PDF: `out/main_YOURNAME_paper20XX.pdf`
- ログ: `out/main_YOURNAME_paper20XX.log`

## 注意事項
- BibTeXの参照ファイルは相対パス（`./tex_files/`）を使用
- 未定義の参照警告は複数回コンパイルで解決される場合があります
