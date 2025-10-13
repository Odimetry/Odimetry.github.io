---
layout: post
title: "Controller / 제어기"
date: 2025-10-08 21:12 +0900
tags: [test]
---
State-space equation
===
In control engineering, a state-space representation is a mathematical model of a physical system that uses state variabels to track how inputs shape system behavior over time through first-order differential equations or difference equations. The most general state-space representation of a linear system with $p$ inputs and $n$ state variables is written in the following form: [wikipedia](https://en.wikipedia.org/wiki/State-space_representation) 

$\dot{x}(t) = \mathbf{A}x(t) + \mathbf{B}u(t)$ \\
$y(t) = \mathbf{C}x(t) + \mathbf{D}u(t)$

where: \\
$x$ is called the "state vector", $x \in \mathbb{R}^{n}$\\
$y$ is called the "output vector", $y \in \mathbb{R}^{q}$\\
$u$ is called the "input(or control) vector", $u \in \mathbb{R}^{p}$\\
$\mathbf{A}$ is the "state matrix", $\mathbf{A} \in \mathbb{R}^{n \times n}$\\
$\mathbf{B}$ is the "input matrix", $\mathbf{B} \in \mathbb{R}^{n \times p}$\\
$\mathbf{C}$ is the "output matrix", $\mathbf{C} \in \mathbb{R}^{q \times n}$\\
$\mathbf{D}$ is the "feedthrough matrix", $\mathbf{D} \in \mathbb{R}^{q \times p}$

In cases where the system model does not have a direct feedthrough, $\mathbf{D}$ is the zero matrix.

Controllability
===
Controllability condition implies that it is possible - by admissible inputs - to steer the states from any initial value to any final value within some finite time window. A continuous time-invariant linear state-space model is controllable if and only if(iff) \\
$$
\operatorname{rank}
\begin{bmatrix}
\mathbf{B} \, \mathbf{AB} \, \cdots \mathbf{A}^{n-1}\mathbf{B}
\end{bmatrix}
= n
$$

Observability
===
Observability is a measure for how well internal states of a system can be inferred by knowledge of its external outputs. A continuous time-invariant linear state-space model is observable if and only if(iff) \\
$$
\operatorname{rank}
\begin{bmatrix}
\mathbf{C} \\ 
\mathbf{CA} \\
\vdots \\
\mathbf{CA}^{n-1}
\end{bmatrix}
 = n
$$

---

상태공간 방정식
===
제어에서 상태공간 표현식이란 물리적 계를 입력, 출력, 상태 변수의 1차 미분 방정식, 차분 방정식으로 표현하는 수학적 모델이다. 일반적인 상태공간 방정식(표현식)에서 $p$개의 입력과 $q$개의 출력, $n$개의 상태변수를 가진다면 다음과 같이 표현할 수 있다.

$\dot{x}(t) = \mathbf{A}x(t) + \mathbf{B}u(t)$ \\
$y(t) = \mathbf{C}x(t) + \mathbf{D}u(t)$

여기서 \\
$x$는 "상태 벡터", $x \in \mathbb{R}^{n}$\\
$y$는 "출력 변수", $y \in \mathbb{R}^{q}$\\
$u$는 "입력(혹은 제어) 벡터", $u \in \mathbb{R}^{p}$\\
$\mathbf{A}$는 "상태 행렬", $\mathbf{A} \in \mathbb{R}^{n \times n}$\\
$\mathbf{B}$는 "입력 행렬", $\mathbf{B} \in \mathbb{R}^{n \times p}$\\
$\mathbf{C}$는 "출력 행렬", $\mathbf{C} \in \mathbb{R}^{q \times n}$\\
$\mathbf{D}$는 "피드스루(feedthrough) 행렬", $\mathbf{D} \in \mathbb{R}^{q \times p}$

가제어성(제어 가능성)
===
가제어성 조건은 - 용인될 수 있는 제어 입력에 의하여 - 상태를 임의의 초기 조건으로부터 또 다른 어떤 최종 조건으로 유한 시간 내에 이끌어갈 수 있다는 것이다. 연속적인 시불변 선형 상태 공간 모델이 제어 가능일 필요 충분 조건은 다음과 같다. \\
$$
\operatorname{rank}
\begin{bmatrix}
\mathbf{B} \, \mathbf{AB} \, \cdots \mathbf{A}^{n-1}\mathbf{B}
\end{bmatrix}
= n
$$

가관측성(관측가능성)
===
가관측성은 일종의 척도로서, 어떤 시스템 내부의 상태가 그 외부 출력을 앎에 따라 얼마나 잘 추정될 수 있는가 하는 것이다. 연속적인 시불변 선형 상태 공간 모델이 관측 가능할 필요 충분 조건은 다음과 같다. \\
$$
\operatorname{rank}
\begin{bmatrix}
\mathbf{C} \\ 
\mathbf{CA} \\
\vdots \\
\mathbf{CA}^{n-1}
\end{bmatrix}
 = n
$$