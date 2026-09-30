---
title: LaTeX 수식 & 논문 작성 치트시트
date: 2026-09-28
categories: [Tools, LaTeX]
tags: [latex, math, paper, cheatsheet]
math: true
description: 블로그와 논문에서 자주 쓰는 LaTeX 수식 문법과 강화학습 표기법, 논문 작성용 명령어 정리
---

블로그(Chirpy)와 논문에서 자주 쓰는 LaTeX 문법을 한곳에 모았다. 표의 왼쪽은 입력, 오른쪽은 실제로 표시되는 모습이다.

## 0. Chirpy 블로그에서 쓸 때 주의할 점

> - front matter에 `math: true`가 있어야 수식이 표시된다.
> - 문장 안 수식도 `$` 하나가 아니라 `$$ ... $$`로 감싼다.
> - 앞뒤에 **빈 줄**이 있는 `$$ ... $$`는 가운데 정렬된 블록 수식이 된다.
> - 목록 맨 앞에 수식이 오면 `\$$ ... $$`처럼 앞의 `$`를 이스케이프한다.
> - 문장 안 수식에서는 `|` 대신 `\mid`, `\vert`, `\lVert` 등을 쓴다. `|`는 표 구분선으로 인식될 수 있다.
> - 여는 중괄호 두 개를 붙여 쓰면 Jekyll(Liquid) 문법과 충돌해 빌드가 깨진다. 두 중괄호 사이에 공백을 한 칸 넣는다.
{: .prompt-warning }

```markdown
문장 안: 할인율 $$ \gamma $$ 는 0과 1 사이 값이다.

$$
V(s) = \max_a Q(s, a)
$$
```

## 1. 그리스 문자

| 입력 | 결과 | 입력 | 결과 | 입력 | 결과 |
|---|---|---|---|---|---|
| `\alpha` | $$\alpha$$ | `\beta` | $$\beta$$ | `\gamma` | $$\gamma$$ |
| `\delta` | $$\delta$$ | `\epsilon` | $$\epsilon$$ | `\varepsilon` | $$\varepsilon$$ |
| `\zeta` | $$\zeta$$ | `\eta` | $$\eta$$ | `\theta` | $$\theta$$ |
| `\lambda` | $$\lambda$$ | `\mu` | $$\mu$$ | `\nu` | $$\nu$$ |
| `\xi` | $$\xi$$ | `\pi` | $$\pi$$ | `\rho` | $$\rho$$ |
| `\sigma` | $$\sigma$$ | `\tau` | $$\tau$$ | `\phi` | $$\phi$$ |
| `\varphi` | $$\varphi$$ | `\chi` | $$\chi$$ | `\psi` | $$\psi$$ |
| `\omega` | $$\omega$$ | `\kappa` | $$\kappa$$ | `\iota` | $$\iota$$ |

대문자는 첫 글자만 대문자로 쓴다: `\Gamma` $$\Gamma$$, `\Delta` $$\Delta$$, `\Theta` $$\Theta$$, `\Lambda` $$\Lambda$$, `\Pi` $$\Pi$$, `\Sigma` $$\Sigma$$, `\Phi` $$\Phi$$, `\Psi` $$\Psi$$, `\Omega` $$\Omega$$

## 2. 첨자, 분수, 루트

| 입력 | 결과 | 설명 |
|---|---|---|
| `x_t` | $$x_t$$ | 아래 첨자 |
| `x^2` | $$x^2$$ | 위 첨자 |
| `R_{t+1}` | $$R_{t+1}$$ | 두 글자 이상은 중괄호로 묶기 |
| `\gamma^{k}` | $$\gamma^{k}$$ | 거듭제곱 |
| `x_{i}^{(j)}` | $$x_{i}^{(j)}$$ | 첨자 동시 사용 |
| `\frac{a}{b}` | $$\frac{a}{b}$$ | 분수 |
| `\tfrac{1}{2}` | $$\tfrac{1}{2}$$ | 작은 분수 (문장 안) |
| `\dfrac{1}{2}` | $$\dfrac{1}{2}$$ | 큰 분수 |
| `\sqrt{x}` | $$\sqrt{x}$$ | 제곱근 |
| `\sqrt[n]{x}` | $$\sqrt[n]{x}$$ | n제곱근 |

## 3. 연산자 (합, 곱, 적분, 극한)

| 입력 | 결과 |
|---|---|
| `\sum_{t=0}^{T} r_t` | $$\sum_{t=0}^{T} r_t$$ |
| `\prod_{i=1}^{n} p_i` | $$\prod_{i=1}^{n} p_i$$ |
| `\int_{a}^{b} f(x)\,dx` | $$\int_{a}^{b} f(x)\,dx$$ |
| `\lim_{n \to \infty} a_n` | $$\lim_{n \to \infty} a_n$$ |
| `\max_{a} Q(s,a)` | $$\max_{a} Q(s,a)$$ |
| `\min_{\theta} L(\theta)` | $$\min_{\theta} L(\theta)$$ |
| `\arg\max_{a} Q(s,a)` | $$\arg\max_{a} Q(s,a)$$ |
| `\operatorname*{argmin}_{\theta} L` | $$\operatorname*{argmin}_{\theta} L$$ |
| `\sup_{x}`, `\inf_{x}` | $$\sup_{x}, \inf_{x}$$ |
| `\log`, `\exp`, `\ln` | $$\log, \exp, \ln$$ |

> 블록 수식에서는 첨자가 기호 위아래로 가고, 문장 안에서는 옆으로 붙는다. 문장 안에서도 위아래로 보내려면 `\sum\limits_{t=0}^{T}`를 쓴다.
{: .prompt-tip }

## 4. 관계 기호와 화살표

| 입력 | 결과 | 입력 | 결과 |
|---|---|---|---|
| `\leq` | $$\leq$$ | `\geq` | $$\geq$$ |
| `\neq` | $$\neq$$ | `\approx` | $$\approx$$ |
| `\sim` | $$\sim$$ | `\propto` | $$\propto$$ |
| `\equiv` | $$\equiv$$ | `\doteq` | $$\doteq$$ |
| `\ll` | $$\ll$$ | `\gg` | $$\gg$$ |
| `\coloneqq` | $$:=$$ | `\triangleq` | $$\triangleq$$ |
| `\leftarrow` | $$\leftarrow$$ | `\rightarrow` | $$\rightarrow$$ |
| `\Rightarrow` | $$\Rightarrow$$ | `\Leftrightarrow` | $$\Leftrightarrow$$ |
| `\mapsto` | $$\mapsto$$ | `\to` | $$\to$$ |
| `\uparrow` | $$\uparrow$$ | `\downarrow` | $$\downarrow$$ |

`\coloneqq`(:=)와 `\triangleq`는 "정의한다"는 뜻으로 논문에서 자주 쓴다. `\coloneqq`는 논문에서는 `mathtools` 패키지가 필요하고, 블로그에서는 표시되지 않을 수 있으니 그냥 `:=`로 쓰면 된다.

## 5. 집합과 논리

| 입력 | 결과 | 입력 | 결과 |
|---|---|---|---|
| `\in` | $$\in$$ | `\notin` | $$\notin$$ |
| `\subset` | $$\subset$$ | `\subseteq` | $$\subseteq$$ |
| `\cup` | $$\cup$$ | `\cap` | $$\cap$$ |
| `\emptyset` | $$\emptyset$$ | `\setminus` | $$\setminus$$ |
| `\forall` | $$\forall$$ | `\exists` | $$\exists$$ |
| `\land` | $$\land$$ | `\lor` | $$\lor$$ |
| `\neg` | $$\neg$$ | `\times` | $$\times$$ |
| `\mathbb{R}^n` | $$\mathbb{R}^n$$ | `\mathbb{N}` | $$\mathbb{N}$$ |
| `\{ x \mid x > 0 \}` | $$\{ x \mid x > 0 \}$$ | `\infty` | $$\infty$$ |

## 6. 글꼴 (논문 표기 관례)

| 입력 | 결과 | 주로 쓰는 곳 |
|---|---|---|
| `\mathbb{E}` | $$\mathbb{E}$$ | 기댓값, 실수 집합 $$\mathbb{R}$$ |
| `\mathcal{S}` | $$\mathcal{S}$$ | 집합, 공간 (상태 공간, 행동 공간, 데이터셋) |
| `\mathbf{x}` | $$\mathbf{x}$$ | 벡터 (라틴 문자) |
| `\boldsymbol{\theta}` | $$\boldsymbol{\theta}$$ | 벡터 (그리스 문자) |
| `\mathrm{KL}` | $$\mathrm{KL}$$ | 약어, 함수 이름 |
| `\text{if } x > 0` | $$\text{if } x > 0$$ | 수식 안의 일반 글자 |
| `\mathit{loss}` | $$\mathit{loss}$$ | 여러 글자 변수 이름 |

## 7. 괄호

| 입력 | 결과 | 설명 |
|---|---|---|
| `\left( \frac{a}{b} \right)` | $$\left( \frac{a}{b} \right)$$ | 내용에 맞게 크기 자동 조절 |
| `\left[ x \right]` | $$\left[ x \right]$$ | 대괄호 |
| `\left\{ x \right\}` | $$\left\{ x \right\}$$ | 중괄호 |
| `\lvert x \rvert` | $$\lvert x \rvert$$ | 절댓값 |
| `\lVert x \rVert_2` | $$\lVert x \rVert_2$$ | 노름 |
| `\langle x, y \rangle` | $$\langle x, y \rangle$$ | 내적 |
| `\lfloor x \rfloor` | $$\lfloor x \rfloor$$ | 내림 |
| `\lceil x \rceil` | $$\lceil x \rceil$$ | 올림 |
| `\bigl( \bigr)`, `\Bigl( \Bigr)` | $$\bigl( \Bigl( \Bigr) \bigr)$$ | 크기 직접 지정 |

조건부 기댓값처럼 괄호 가운데에 세로선이 필요하면 `\left[ X \,\middle|\, Y \right]`를 쓴다.

$$
\mathbb{E}\left[ X \,\middle|\, Y \right]
$$

## 8. 위에 붙는 기호 (악센트)

| 입력 | 결과 | 주로 쓰는 뜻 |
|---|---|---|
| `\hat{x}` | $$\hat{x}$$ | 추정값 |
| `\widehat{AB}` | $$\widehat{AB}$$ | 긴 추정값 |
| `\bar{x}` | $$\bar{x}$$ | 평균 |
| `\overline{xy}` | $$\overline{xy}$$ | 긴 윗줄 |
| `\tilde{x}` | $$\tilde{x}$$ | 근사, 변형된 값 |
| `\dot{x}`, `\ddot{x}` | $$\dot{x}, \ddot{x}$$ | 시간 미분 |
| `\vec{v}` | $$\vec{v}$$ | 벡터 |
| `x^{*}`, `x'` | $$x^{*}, x'$$ | 최적값, 다음 값 |
| `\underbrace{a+b}_{\text{합}}` | $$\underbrace{a+b}_{\text{합}}$$ | 부분 설명 |
| `\overbrace{a+b}^{n}` | $$\overbrace{a+b}^{n}$$ | 부분 설명 |

## 9. 미분과 선형대수

| 입력 | 결과 |
|---|---|
| `\frac{d y}{d x}` | $$\frac{d y}{d x}$$ |
| `\frac{\partial L}{\partial \theta}` | $$\frac{\partial L}{\partial \theta}$$ |
| `\nabla_\theta J(\theta)` | $$\nabla_\theta J(\theta)$$ |
| `\nabla^2 f` | $$\nabla^2 f$$ |
| `A^\top`, `A^{-1}` | $$A^\top, A^{-1}$$ |
| `\operatorname{tr}(A)`, `\det(A)` | $$\operatorname{tr}(A), \det(A)$$ |
| `\operatorname{diag}(x)` | $$\operatorname{diag}(x)$$ |
| `x \cdot y`, `x \odot y`, `x \otimes y` | $$x \cdot y, x \odot y, x \otimes y$$ |
| `\cdots`, `\ldots`, `\vdots`, `\ddots` | $$\cdots, \ldots, \vdots, \ddots$$ |

## 10. 행렬, 경우 나누기, 여러 줄 정렬

**행렬**

```latex
\begin{bmatrix}
  a & b \\
  c & d
\end{bmatrix}
```

$$
\begin{bmatrix}
  a & b \\
  c & d
\end{bmatrix}
\quad
\begin{pmatrix}
  1 & 0 \\
  0 & 1
\end{pmatrix}
$$

`bmatrix`는 대괄호, `pmatrix`는 소괄호, `vmatrix`는 행렬식 기호를 붙인다.

**경우 나누기 (cases)**

```latex
\pi(a \mid s) =
\begin{cases}
  1 - \epsilon + \frac{\epsilon}{|\mathcal{A}|} & \text{if } a = \arg\max_{a'} Q(s, a') \\
  \frac{\epsilon}{|\mathcal{A}|} & \text{otherwise}
\end{cases}
```

$$
\pi(a \mid s) =
\begin{cases}
  1 - \epsilon + \frac{\epsilon}{\lvert\mathcal{A}\rvert} & \text{if } a = \arg\max_{a'} Q(s, a') \\
  \frac{\epsilon}{\lvert\mathcal{A}\rvert} & \text{otherwise}
\end{cases}
$$

**여러 줄 정렬 (aligned)**

`&`가 정렬 기준점이고, `\\`로 줄을 바꾼다.

```latex
\begin{aligned}
  V^\pi(s) &= \mathbb{E}_\pi \left[ G_t \mid S_t = s \right] \\
           &= \mathbb{E}_\pi \left[ R_{t+1} + \gamma G_{t+1} \mid S_t = s \right] \\
           &= \sum_a \pi(a \mid s) \sum_{s', r} p(s', r \mid s, a) \left[ r + \gamma V^\pi(s') \right]
\end{aligned}
```

$$
\begin{aligned}
  V^\pi(s) &= \mathbb{E}_\pi \left[ G_t \mid S_t = s \right] \\
           &= \mathbb{E}_\pi \left[ R_{t+1} + \gamma G_{t+1} \mid S_t = s \right] \\
           &= \sum_a \pi(a \mid s) \sum_{s', r} p(s', r \mid s, a) \left[ r + \gamma V^\pi(s') \right]
\end{aligned}
$$

**번호 붙이기와 참조**

```latex
\begin{equation}
  \delta_t = r_{t+1} + \gamma V(s_{t+1}) - V(s_t)
  \label{eq:td}
\end{equation}

식 \eqref{eq:td}는 TD error이다.
```

$$
\begin{equation}
  \delta_t = r_{t+1} + \gamma V(s_{t+1}) - V(s_t)
  \label{eq:td}
\end{equation}
$$

식 $$\eqref{eq:td}$$는 TD error이다.

## 11. 간격

| 입력 | 결과 | 크기 |
|---|---|---|
| `a\,b` | $$a\,b$$ | 아주 좁게 (적분의 dx 앞에 자주 씀) |
| `a\;b` | $$a\;b$$ | 조금 넓게 |
| `a\quad b` | $$a\quad b$$ | 1em |
| `a\qquad b` | $$a\qquad b$$ | 2em |
| `a\!b` | $$a\!b$$ | 좁히기 |

## 12. 확률과 통계

| 입력 | 결과 |
|---|---|
| `P(A \mid B)` | $$P(A \mid B)$$ |
| `x \sim \mathcal{N}(\mu, \sigma^2)` | $$x \sim \mathcal{N}(\mu, \sigma^2)$$ |
| `\mathbb{E}_{x \sim p}[f(x)]` | $$\mathbb{E}_{x \sim p}[f(x)]$$ |
| `\operatorname{Var}[X]`, `\operatorname{Cov}(X,Y)` | $$\operatorname{Var}[X], \operatorname{Cov}(X,Y)$$ |
| `D_{\mathrm{KL}}(p \,\Vert\, q)` | $$D_{\mathrm{KL}}(p \,\Vert\, q)$$ |
| `\mathcal{H}(\pi)` | $$\mathcal{H}(\pi)$$ |
| `\mathbb{1}[x > 0]` | $$\mathbb{1}[x > 0]$$ |
| `\operatorname{Uniform}(0, 1)` | $$\operatorname{Uniform}(0, 1)$$ |

## 13. 강화학습 표기법

| 의미 | 입력 | 결과 |
|---|---|---|
| MDP | `(\mathcal{S}, \mathcal{A}, P, R, \gamma)` | $$(\mathcal{S}, \mathcal{A}, P, R, \gamma)$$ |
| 정책 | `\pi_\theta(a \mid s)` | $$\pi_\theta(a \mid s)$$ |
| 최적 정책 | `\pi^*` | $$\pi^*$$ |
| 전이 확률 | `P(s' \mid s, a)` | $$P(s' \mid s, a)$$ |
| 리턴 | `G_t = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}` | $$G_t = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}$$ |
| 가치 함수 | `V^\pi(s)`, `Q^\pi(s, a)` | $$V^\pi(s), Q^\pi(s, a)$$ |
| 어드밴티지 | `A^\pi(s,a) = Q^\pi(s,a) - V^\pi(s)` | $$A^\pi(s,a) = Q^\pi(s,a) - V^\pi(s)$$ |
| 궤적 | `\tau = (s_0, a_0, r_0, s_1, \ldots)` | $$\tau = (s_0, a_0, r_0, s_1, \ldots)$$ |
| 리플레이 버퍼 | `\mathcal{D}` | $$\mathcal{D}$$ |
| 타깃 네트워크 | `Q_{\bar{\theta}}`, `\theta^{-}` | $$Q_{\bar{\theta}}, \theta^{-}$$ |

### 자주 나오는 식

**벨만 최적 방정식**

```latex
Q^*(s, a) = \mathbb{E}_{s' \sim P} \left[ r(s, a) + \gamma \max_{a'} Q^*(s', a') \right]
```

$$
Q^*(s, a) = \mathbb{E}_{s' \sim P} \left[ r(s, a) + \gamma \max_{a'} Q^*(s', a') \right]
$$

**Q-learning 업데이트**

```latex
Q(s, a) \leftarrow Q(s, a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]
```

$$
Q(s, a) \leftarrow Q(s, a) + \alpha \left[ r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right]
$$

**DQN 손실 함수**

```latex
\mathcal{L}(\theta) = \mathbb{E}_{(s,a,r,s') \sim \mathcal{D}} \left[ \left( r + \gamma \max_{a'} Q_{\theta^-}(s', a') - Q_\theta(s, a) \right)^2 \right]
```

$$
\mathcal{L}(\theta) = \mathbb{E}_{(s,a,r,s') \sim \mathcal{D}} \left[ \left( r + \gamma \max_{a'} Q_{\theta^-}(s', a') - Q_\theta(s, a) \right)^2 \right]
$$

**Policy Gradient (REINFORCE)**

```latex
\nabla_\theta J(\theta) = \mathbb{E}_{\tau \sim \pi_\theta} \left[ \sum_{t=0}^{T} \nabla_\theta \log \pi_\theta(a_t \mid s_t) \, G_t \right]
```

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\tau \sim \pi_\theta} \left[ \sum_{t=0}^{T} \nabla_\theta \log \pi_\theta(a_t \mid s_t) \, G_t \right]
$$

**PPO Clipped Objective**

```latex
L^{\text{CLIP}}(\theta) = \mathbb{E}_t \left[ \min \left( r_t(\theta) \hat{A}_t, \; \operatorname{clip}\left(r_t(\theta), 1 - \epsilon, 1 + \epsilon\right) \hat{A}_t \right) \right],
\quad r_t(\theta) = \frac{\pi_\theta(a_t \mid s_t)}{\pi_{\theta_{\text{old}}}(a_t \mid s_t)}
```

$$
L^{\text{CLIP}}(\theta) = \mathbb{E}_t \left[ \min \left( r_t(\theta) \hat{A}_t, \; \operatorname{clip}\left(r_t(\theta), 1 - \epsilon, 1 + \epsilon\right) \hat{A}_t \right) \right],
\quad r_t(\theta) = \frac{\pi_\theta(a_t \mid s_t)}{\pi_{\theta_{\text{old}}}(a_t \mid s_t)}
$$

**GAE (Generalized Advantage Estimation)**

```latex
\hat{A}_t^{\text{GAE}(\gamma, \lambda)} = \sum_{l=0}^{\infty} (\gamma \lambda)^l \delta_{t+l},
\quad \delta_t = r_t + \gamma V(s_{t+1}) - V(s_t)
```

$$
\hat{A}_t^{\text{GAE}(\gamma, \lambda)} = \sum_{l=0}^{\infty} (\gamma \lambda)^l \delta_{t+l},
\quad \delta_t = r_t + \gamma V(s_{t+1}) - V(s_t)
$$

**최대 엔트로피 목표 (SAC)**

```latex
J(\pi) = \sum_{t=0}^{T} \mathbb{E}_{(s_t, a_t) \sim \rho_\pi} \left[ r(s_t, a_t) + \alpha \mathcal{H}\left(\pi(\cdot \mid s_t)\right) \right]
```

$$
J(\pi) = \sum_{t=0}^{T} \mathbb{E}_{(s_t, a_t) \sim \rho_\pi} \left[ r(s_t, a_t) + \alpha \mathcal{H}\left(\pi(\cdot \mid s_t)\right) \right]
$$

## 14. 논문 작성용 LaTeX 명령어

> 아래 명령어는 Overleaf 같은 LaTeX 문서에서 쓰는 것이다. 블로그에서는 표시되지 않는다.
{: .prompt-info }

### 기본 문서 구조

```latex
\documentclass{article}
\usepackage{amsmath, amssymb, amsthm}  % 수식, 기호, 정리 환경
\usepackage{graphicx}                  % 그림
\usepackage{booktabs}                  % 깔끔한 표
\usepackage{hyperref}                  % 링크
\usepackage{algorithm, algorithmic}    % 알고리즘 박스
\usepackage[capitalise]{cleveref}      % \cref로 "Figure 1" 자동 표기

\title{Paper Title}
\author{Name \\ Affiliation \\ \texttt{email@example.com}}

\begin{document}
\maketitle

\begin{abstract}
  초록 내용
\end{abstract}

\section{Introduction}
\subsection{Background}
\paragraph{Notation.} 문단 제목이 붙은 짧은 단락

\bibliographystyle{plainnat}
\bibliography{references}  % references.bib 파일
\end{document}
```

### 글자 서식

| 입력 | 뜻 |
|---|---|
| `\textbf{굵게}` | 굵게 |
| `\textit{기울임}`, `\emph{강조}` | 기울임 (논문에서는 `\emph`를 주로 씀) |
| `\texttt{code}` | 고정폭 글꼴 (코드, 환경 이름) |
| `\textsc{Ppo}` | 작은 대문자 (알고리즘 이름에 자주 씀) |
| `\footnote{각주}` | 각주 |
| `~` | 줄바꿈되지 않는 공백 (`Figure~\ref{fig:a}`) |
| `` ``따옴표'' `` | 올바른 큰따옴표 |
| `e.g.,\ `, `i.e.,\ ` | 약어 뒤 간격 보정 |

### 인용과 참조

```latex
\cite{schulman2017ppo}         % [1] 또는 (Schulman et al., 2017)
\citet{mnih2015dqn}            % Mnih et al. (2015) — 문장 주어로 쓸 때
\citep{haarnoja2018sac}        % (Haarnoja et al., 2018) — 괄호 인용
\label{sec:method}             % 라벨 달기
\ref{sec:method}               % 번호 참조
\eqref{eq:loss}                % 식 번호 참조 (괄호 포함)
\cref{fig:result}              % "Figure 3"처럼 종류까지 자동 표기
```

라벨 이름은 `sec:`, `fig:`, `tab:`, `eq:`, `alg:`처럼 접두어를 붙이면 관리하기 편하다.

`references.bib`의 항목 예시:

```bibtex
@article{schulman2017ppo,
  title   = {Proximal Policy Optimization Algorithms},
  author  = {Schulman, John and Wolski, Filip and Dhariwal, Prafulla and Radford, Alec and Klimov, Oleg},
  journal = {arXiv preprint arXiv:1707.06347},
  year    = {2017}
}
```

> Google Scholar에서 논문 아래 **인용** → **BibTeX**를 누르면 이 형식을 그대로 복사할 수 있다.
{: .prompt-tip }

### 그림

```latex
\begin{figure}[t]
  \centering
  \includegraphics[width=0.8\linewidth]{figures/learning_curve.pdf}
  \caption{Learning curves on MuJoCo tasks. Shaded area denotes standard error over 5 seeds.}
  \label{fig:curve}
\end{figure}
```

그림 두 개를 나란히 놓을 때는 `subcaption` 패키지를 쓴다.

```latex
\begin{figure}[t]
  \centering
  \begin{subfigure}{0.48\linewidth}
    \includegraphics[width=\linewidth]{figures/a.pdf}
    \caption{HalfCheetah}
  \end{subfigure}
  \hfill
  \begin{subfigure}{0.48\linewidth}
    \includegraphics[width=\linewidth]{figures/b.pdf}
    \caption{Hopper}
  \end{subfigure}
  \caption{Results on two environments.}
  \label{fig:results}
\end{figure}
```

위치 옵션: `[t]` 페이지 위, `[b]` 아래, `[h]` 현재 위치, `[!t]` 강제로 위

### 표 (booktabs)

```latex
\begin{table}[t]
  \centering
  \caption{Average return over 5 seeds.}
  \label{tab:main}
  \begin{tabular}{lccc}
    \toprule
    Method & HalfCheetah & Hopper & Walker2d \\
    \midrule
    PPO  & 2345 $\pm$ 120 & 1987 $\pm$ 85 & 3012 $\pm$ 140 \\
    SAC  & \textbf{10214 $\pm$ 310} & \textbf{3301 $\pm$ 95} & \textbf{4567 $\pm$ 201} \\
    \bottomrule
  \end{tabular}
\end{table}
```

`l`, `c`, `r`은 열의 왼쪽, 가운데, 오른쪽 정렬이다. 논문 표에는 세로줄을 넣지 않고 `\toprule`, `\midrule`, `\bottomrule`만 쓰는 것이 관례다.

### 알고리즘 박스

```latex
\begin{algorithm}[t]
  \caption{Q-learning}
  \label{alg:qlearning}
  \begin{algorithmic}[1]
    \STATE Initialize $Q(s, a)$ arbitrarily
    \FOR{each episode}
      \STATE Initialize $s$
      \REPEAT
        \STATE Choose $a$ from $s$ using $\epsilon$-greedy policy
        \STATE Take action $a$, observe $r, s'$
        \STATE $Q(s,a) \leftarrow Q(s,a) + \alpha [r + \gamma \max_{a'} Q(s',a') - Q(s,a)]$
        \STATE $s \leftarrow s'$
      \UNTIL{$s$ is terminal}
    \ENDFOR
  \end{algorithmic}
\end{algorithm}
```

### 정리, 정의, 증명

```latex
\newtheorem{theorem}{Theorem}
\newtheorem{lemma}{Lemma}
\newtheorem{definition}{Definition}

\begin{definition}[Markov Decision Process]
  An MDP is a tuple $(\mathcal{S}, \mathcal{A}, P, R, \gamma)$ ...
\end{definition}

\begin{theorem}\label{thm:convergence}
  Q-learning converges to $Q^*$ with probability 1 if ...
\end{theorem}

\begin{proof}
  증명 내용
\end{proof}
```

### 자주 쓰는 매크로 정의

문서 앞부분에 정의해 두면 긴 기호를 짧게 쓸 수 있다.

```latex
\newcommand{\E}{\mathbb{E}}
\newcommand{\R}{\mathbb{R}}
\newcommand{\cS}{\mathcal{S}}
\newcommand{\cA}{\mathcal{A}}
\DeclareMathOperator*{\argmax}{arg\,max}
\DeclareMathOperator*{\argmin}{arg\,min}
```

## 15. 참고 사이트

- **Detexify** (detexify.kirelabs.org): 기호를 손으로 그리면 LaTeX 명령어를 찾아준다.
- **Overleaf 문서** (overleaf.com/learn): LaTeX 사용법이 주제별로 정리되어 있다.
- **MathJax 지원 목록** (docs.mathjax.org): 블로그에서 쓸 수 있는 명령어 확인용.
