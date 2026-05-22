---
title: "양자역학 입문 — 파동함수와 슈뢰딩거 방정식"
date: 2026-05-22
draft: false
tags: ["양자역학", "파동함수", "슈뢰딩거 방정식", "입문"]
categories: ["physics"]
description: "양자역학의 핵심 개념인 파동함수와 시간에 따른 슈뢰딩거 방정식을 소개합니다."
ShowToc: true
TocOpen: true
---

## 들어가며

고전역학이 입자의 위치와 운동량을 **동시에 정확히** 기술할 수 있다고 믿었던 시대가 있었습니다. 하지만 20세기 초, 전자의 이중 슬릿 실험이나 흑체 복사 문제는 고전역학으로는 도저히 설명이 안 됐습니다. 이 위기에서 탄생한 것이 바로 **양자역학**입니다.

---

## 1. 파동함수 $\psi(x, t)$

양자역학에서 입자의 상태는 **파동함수(wave function)** $\psi(x, t)$로 기술됩니다. 파동함수 자체는 직접 관측할 수 없는 복소수 함수이지만, 그 절댓값의 제곱이 중요한 의미를 가집니다.

$$
|\psi(x, t)|^2 \, dx = \text{(시각 } t \text{에 입자를 } x \sim x+dx \text{ 사이에서 발견할 확률)}
$$

이를 **확률 밀도(probability density)** 라 하고, 전체 공간에서의 적분은 반드시 1이어야 합니다:

$$
\int_{-\infty}^{\infty} |\psi(x, t)|^2 \, dx = 1
$$

이 조건을 **규격화(normalization)** 조건이라 부릅니다.

---

## 2. 시간-의존 슈뢰딩거 방정식

파동함수의 시간 발전은 **시간-의존 슈뢰딩거 방정식(TDSE)**으로 결정됩니다:

$$
i\hbar \frac{\partial \psi}{\partial t} = \hat{H} \psi = \left[ -\frac{\hbar^2}{2m} \frac{\partial^2}{\partial x^2} + V(x, t) \right] \psi
$$

여기서
- $\hbar = h / 2\pi$: 환산 플랑크 상수
- $m$: 입자의 질량
- $V(x,t)$: 포텐셜 에너지
- $\hat{H}$: **해밀토니안 연산자**

> 이 방정식은 **선형 편미분방정식**입니다. 따라서 두 해의 선형결합도 해가 됩니다 — 이것이 양자 중첩의 수학적 근거입니다.

---

## 3. 시간-독립 슈뢰딩거 방정식

포텐셜이 시간에 무관한 경우 $V = V(x)$, 변수분리법으로

$$
\psi(x, t) = \phi(x) \cdot e^{-iEt/\hbar}
$$

를 가정하면 공간 부분 $\phi(x)$에 대한 **시간-독립 슈뢰딩거 방정식(TISE)**을 얻습니다:

$$
\hat{H} \phi(x) = E \phi(x)
$$

$$
-\frac{\hbar^2}{2m} \frac{d^2 \phi}{dx^2} + V(x) \phi = E \phi
$$

이것은 해밀토니안 연산자 $\hat{H}$의 **고유값 방정식**입니다. $E$는 에너지 고유값, $\phi$는 대응하는 **에너지 고유상태**입니다.

---

## 4. 무한 퍼텐셜 우물 예시

$0 < x < L$ 영역에서 $V = 0$이고, 그 밖에서 $V = \infty$인 **무한 퍼텐셜 우물**을 생각해봅시다.

경계조건 $\phi(0) = \phi(L) = 0$으로부터 해는

$$
\phi_n(x) = \sqrt{\frac{2}{L}} \sin\!\left(\frac{n\pi x}{L}\right), \quad n = 1, 2, 3, \ldots
$$

이고, 에너지 고유값은

$$
E_n = \frac{n^2 \pi^2 \hbar^2}{2mL^2} = \frac{n^2 h^2}{8mL^2}
$$

**에너지가 양자화(quantized)** 됩니다! 이것이 양자역학의 가장 특징적인 현상 중 하나입니다.

---

## 5. 연산자와 기댓값

물리량 $A$에 해당하는 연산자 $\hat{A}$의 **기댓값**은

$$
\langle A \rangle = \int_{-\infty}^{\infty} \psi^* \hat{A} \psi \, dx
$$

로 주어집니다. 예를 들어 위치와 운동량의 기댓값은

$$
\langle x \rangle = \int \psi^* \, x \, \psi \, dx, \qquad
\langle p \rangle = \int \psi^* \left(-i\hbar \frac{\partial}{\partial x}\right) \psi \, dx
$$

---

## 마치며

슈뢰딩거 방정식은 양자역학의 심장부입니다. 다음 글에서는 **하이젠베르크 불확정성 원리**와 연산자의 교환자(commutator)를 다룰 예정입니다.

$$
\Delta x \cdot \Delta p \geq \frac{\hbar}{2}
$$

이 부등식이 단순한 측정 한계가 아니라 자연의 근본적인 특성임을 살펴보겠습니다.
