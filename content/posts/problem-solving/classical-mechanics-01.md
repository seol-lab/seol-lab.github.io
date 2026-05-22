---
title: "고전역학 문제풀이 #1 — 단순조화진동자의 에너지 보존"
date: 2026-05-22
draft: false
tags: ["고전역학", "단순조화진동자", "에너지 보존", "문제풀이"]
categories: ["problem-solving"]
description: "단순조화진동자(SHO)의 에너지 보존을 라그랑주 역학으로 유도합니다."
ShowToc: true
TocOpen: true
---

## 문제

질량 $m$인 입자가 용수철 상수 $k$인 용수철에 연결되어 1차원 운동을 한다. 마찰은 없다.

1. 라그랑주안(Lagrangian) $L$을 구하라.
2. 오일러-라그랑주 방정식으로 운동방정식을 유도하라.
3. 역학적 에너지가 보존됨을 보여라.
4. 일반해를 구하고, 진동 주기 $T$를 구하라.

---

## 풀이

### 1. 라그랑주안 설정

일반화 좌표로 입자의 위치 $q = x$를 선택한다.

**운동에너지:**
$$
T = \frac{1}{2} m \dot{x}^2
$$

**퍼텐셜 에너지:**
$$
V = \frac{1}{2} k x^2
$$

**라그랑주안:**
$$
L = T - V = \frac{1}{2} m \dot{x}^2 - \frac{1}{2} k x^2
$$

---

### 2. 오일러-라그랑주 방정식

$$
\frac{d}{dt}\!\left(\frac{\partial L}{\partial \dot{x}}\right) - \frac{\partial L}{\partial x} = 0
$$

각 항을 계산하면:

$$
\frac{\partial L}{\partial \dot{x}} = m\dot{x}
\quad \Rightarrow \quad
\frac{d}{dt}\!\left(\frac{\partial L}{\partial \dot{x}}\right) = m\ddot{x}
$$

$$
\frac{\partial L}{\partial x} = -kx
$$

따라서 운동방정식은

$$
\boxed{m\ddot{x} + kx = 0}
$$

이것이 **단순조화진동자 방정식**이다.

---

### 3. 에너지 보존 증명

전체 역학적 에너지를 $E = T + V$로 정의한다:

$$
E = \frac{1}{2}m\dot{x}^2 + \frac{1}{2}kx^2
$$

시간에 대해 미분하면:

$$
\frac{dE}{dt} = m\dot{x}\ddot{x} + kx\dot{x} = \dot{x}(m\ddot{x} + kx)
$$

운동방정식 $m\ddot{x} + kx = 0$을 대입하면:

$$
\frac{dE}{dt} = \dot{x} \cdot 0 = 0
$$

$$
\therefore \quad E = \text{const} \qquad \blacksquare
$$

> 마찰이 없는 SHO에서 역학적 에너지는 항상 보존된다.

---

### 4. 일반해와 주기

$\omega_0^2 = k/m$으로 놓으면 운동방정식은

$$
\ddot{x} + \omega_0^2 x = 0
$$

특성방정식의 근이 $\pm i\omega_0$이므로 일반해는

$$
x(t) = A\cos(\omega_0 t) + B\sin(\omega_0 t)
$$

혹은 진폭-위상 형태로

$$
\boxed{x(t) = C\cos(\omega_0 t + \phi)}
$$

여기서 $C = \sqrt{A^2 + B^2}$, $\tan\phi = -B/A$이다.

**진동 주기:**

$$
T = \frac{2\pi}{\omega_0} = 2\pi\sqrt{\frac{m}{k}}
$$

> **핵심 포인트**: 주기 $T$는 진폭 $C$에 **무관**하다. 이것이 SHO의 가장 중요한 성질인 **등시성(isochronism)**이다.

---

### 5. 위상 공간 그림

초기 조건 $x(0) = x_0$, $\dot{x}(0) = 0$으로 풀면

$$
x(t) = x_0 \cos(\omega_0 t), \qquad \dot{x}(t) = -x_0\omega_0 \sin(\omega_0 t)
$$

에너지 보존 $E = \frac{1}{2}m\dot{x}^2 + \frac{1}{2}kx^2 = \frac{1}{2}kx_0^2$으로부터

$$
\frac{x^2}{x_0^2} + \frac{\dot{x}^2}{x_0^2\omega_0^2} = 1
$$

이것은 위상 공간 $(x, \dot{x})$에서 **타원** 궤적이다.

---

## 정리

| 물리량 | 표현 |
|-------|------|
| 라그랑주안 | $L = \frac{1}{2}m\dot{x}^2 - \frac{1}{2}kx^2$ |
| 운동방정식 | $m\ddot{x} + kx = 0$ |
| 각진동수 | $\omega_0 = \sqrt{k/m}$ |
| 주기 | $T = 2\pi/\omega_0 = 2\pi\sqrt{m/k}$ |
| 에너지 | $E = \frac{1}{2}kC^2$ (보존) |

다음 문제풀이에서는 **감쇠 조화진동자(damped harmonic oscillator)**를 다룰 예정입니다.
