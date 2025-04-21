# みんなのチートシート
### これはLaTeXを使っていく上で、皆が気づいたことをまとめていきます。

### コメントアウト
- `%`：行先頭に置いて1行コメント化
- `\usepackage{comment}` ＋ `\begin{comment} … \end{comment}`：複数行のコメント化

### 空白の調整
- **縦方向**
  ```latex
  \vspace{〈長さ〉}    % 例: \vspace{10pt}
  \smallskip / \medskip / \bigskip
  ```
- **横方向**
  ```latex
  \hspace{〈長さ〉}    % 例: \hspace{5mm}
  \\              % 空白1文字分
  ~               % 空白1文字分（改行抑制）
  ```

### 改行・改ページ
- `\\`：改行（インデントなし）
- `\par`：改行（インデントあり）
- `\newpage`：強制改ページ

### セクション見出し
```latex
\chapter{章タイトル}
\section{節タイトル}
\subsection{小節タイトル}
\subsubsection{細分節タイトル}
```
自動で番号付与・目次登録がされます。

### 図の挿入
```latex
\usepackage[dvipdfmx]{graphicx}
\begin{figure}[htbp]
  \centering
  \includegraphics[width=100mm]{hoge.png}
  \caption{説明文}
\end{figure}
```
配置オプション `h,t,b,p` で優先順を指定。

### 箇条書き・番号付きリスト
- **箇条書き**
  ```latex
  \begin{itemize}
    \item アイテム1
    \item アイテム2
  \end{itemize}
  ```
- **番号付き**
  ```latex
  \begin{enumerate}
    \item 項目1
    \item 項目2
  \end{enumerate}
  ```

### 表の作成
```latex
\begin{tabular}{|r||c|l|} \hline
  1 & a   & あ \\ \hline
  2 & bb  & いい \\ \hline
  3 & ccc & ううう \\ \hline
\end{tabular}
```
列指定 `{r|c|l}` で右・中央・左揃え。

### 中央・左右揃え
```latex
\begin{center} … \end{center}
\begin{flushleft} … \end{flushleft}
\begin{flushright} … \end{flushright}
```

### ファイルの分割管理
```latex
\input{hoge.tex}
```
大規模文書の分割読み込みに便利。

### 文字装飾・サイズ変更
- **装飾**：`\textbf{太字}` / `\textit{斜体}`
- **サイズ**：`\tiny` ～ `\Huge`
- **部分拡大**：`\scalebox{2}{テキスト}`（`graphicx`パッケージ）

### 数式モード
- **インライン**：`$ … $`
- **ディスプレイ**：`$$ … $$` または `\begin{eqnarray} … \end{eqnarray}`
- `&` で揃え、`\nonumber` で式番号抑制、`\label`/`\ref` で相互参照。

### ギリシャ文字・記号・演算子・行列
## ギリシャ文字

| 出力 | TeX               | 出力 | TeX                 | 出力 | TeX                   |
|:----:|:-----------------:|:----:|:-------------------:|:----:|:---------------------:|
| α    | `\alpha`          | β    | `\beta`             | γ    | `\gamma`              |
| ζ    | `\zeta`           | η    | `\eta`              | κ    | `\kappa`              |
| μ    | `\mu`             | ν    | `\nu`               | Ξ    | `\Xi`                 |
| ρ    | `\rho`            | τ    | `\tau`              | χ    | `\chi`                |
| Δ    | `\Delta`          | δ    | `\delta`            | ε    | `\epsilon`<br>`\varepsilon` |
| Θ    | `\Theta`          | θ    | `\theta`            | ϑ    | `\vartheta`           |
| Λ    | `\Lambda`         | λ    | `\lambda`           |      |                       |
| Π    | `\Pi`             | π    | `\pi`               |      |                       |
| Σ    | `\Sigma`          | σ    | `\sigma`            |      |                       |
| Φ    | `\Phi`            | ϕ    | `\phi`<br>`\varphi` |      |                       |
| Ψ    | `\Psi`            | ψ    | `\psi`              |      |                       |
| Ω    | `\Omega`          | ω    | `\omega`            |      |                       |

_ϕ や ϑ など、`\var…` の形で書くものもある_

---

## 記号

| 出力 | TeX               |
|:----:|:-----------------:|
| ×    | `\times`          |
| ÷    | `\div`            |
| ±    | `\pm`             |
| ∓    | `\mp`             |
| ≠    | `\neq`            |
| ≒    | `\simeq`          |
| ≔    | `\fallingdotseq`  |
| ≡    | `\equiv`          |
| ≥    | `\geqq`           |
| ≤    | `\leqq`           |
| ∞    | `\infty`          |
| ∵    | `\because`        |
| ∴    | `\therefore`      |

---

## 演算子

| 出力  | TeX            |
|:-----:|:--------------:|
| ∇     | `\nabla`       |
| ∂     | `\partial`     |
| x̄     | `\bar{x}`      |
| ẋ     | `\dot{x}`      |
| x⃗     | `\vec{x}`      |
| Sₓᵧ   | `S_{xy}`       |
| S²    | `S^{2}`        |

---

## 括弧

| 出力      | TeX                           |
|:---------:|:-----------------------------:|
| (hoge)    | `\left( hoge \right)`         |
| {hoge}    | `\left\{ hoge \right\}`       |
| [hoge]    | `\left[ hoge \right\]`        |
| ∣         | `\middle|`                    |

`\left`／`\right` により中身の高さに合わせて自動調整。  
単独で使う縦棒などには `\middle` を使う。

---

## 数式

| 出力           | TeX                       |
|:--------------:|:-------------------------:|
| $e^x$          | `e^x`                     |
| $\log x$       | `\log x`                  |
| $\log_a x$     | `\log_a x`                |
| $\ln x$        | `\ln x`                   |
| $\lim_{n\to\infty}$ | `\lim_{n\to\infty}` |
| $\sin x$       | `\sin x`                  |
| $\cos x$       | `\cos x`                  |
| $\tan x$       | `\tan x`                  |
| $\sum_{i=1}^N$ | `\sum_{i=1}^{N}`          |
| $\prod_{i=1}^N$| `\prod_{i=1}^{N}`         |
| $\int_{a}^{b}$ | `\int_{a}^{b}`            |
| $\iint_{a}^{b}$| `\iint_{a}^{b}`           |

`\frac{}{}` ではなく `\cfrac{}{}` を使うと、分数内の文字も見やすい大きさになる。

- 行列：
  ```latex
  \begin{pmatrix}
    a & b \\
    c & d
  \end{pmatrix}
  ```
- 場合分け：
  ```latex
  \begin{cases}
    A & (条件1) \\
    B & (条件2)
  \end{cases}
  ```

### 式回りの処理
```latex
\begin{eqnarray}
  y & = & x^2 + 2x + 1 \nonumber \\
    & = & (x+1)^2 \label{eq:factors}
\end{eqnarray}
式番号の付与・抑制や参照が可能。
