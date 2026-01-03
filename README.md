# Programming Practice for Problem Solving

- 이 저장소는 **문제해결프로그래밍실습** 과목에서 진행한 과제 및 보고서를 정리한 것입니다.  
- 각 항목은 **문제 요약 → 접근 방법(알고리즘) → 핵심 아이디어/복잡도 → 구현** 흐름으로 정리되어 있습니다.

---

## ✅ 목차

- [1. Finding Celebrities](#1-finding-celebrities)
- [2. Minimum Calculation](#2-minimum-calculation)
- [3. Largest N Numbers](#3-largest-n-numbers)
- [4. Position of k](#4-position-of-k)
- [5. Matrix Addition](#5-matrix-addition)
- [6. Half-Circle Property](#6-half-circle-property)
- [7. Train Rearrangement](#7-train-rearrangement)
- [8. Agony of Engineer](#8-agony-of-engineer)
- [10. Matrix Power Fibonacci / Two Pointers / Sliding Window / DP Problems](#10-matrix-power-fibonacci--two-pointers--sliding-window--dp-problems)
- [11. Knapsack / Climbing Stairs](#11-knapsack--climbing-stairs)

---

## 1. Finding Celebrities

**문제 요약**  
N명 중 유명인(celebrity)이 존재한다면 **단 1명만 존재**하며,  
그 유명인은 **아무도 모르고(out-degree=0)**, **다른 모든 사람은 그를 안다(in-degree=N-1)**는 조건을 만족한다.

**접근 방법 (Two Pointers / Candidate Elimination)**  
두 사람 A, B를 비교한다.

- A가 B를 알면 → A 탈락  
- A가 B를 모르면 → B 탈락  

이 과정을 반복하면 후보가 1명으로 줄어들며, 이후 검증 단계에서 유명인 여부를 판별한다.

**복잡도**  
- Time: `O(N)`  
- Space: `O(1)`

---

## 2. Minimum Calculation

**문제 요약**  
곱셈 연산의 횟수를 최소화하며 `a^n`을 계산한다.

**접근 방법**  
- 기본 방식: **Exponentiation by Squaring**
  - 짝수/홀수 분기
  - 반복 구조 사용 → stack overflow 방지
- 확장 관점: BFS 기반 덧셈 사슬(addition chain)을 통해 최소 곱셈 경로 탐색

**복잡도(대표)**  
- Time: `O(log n)`  
- Space: `O(1)`

---

## 3. Largest N Numbers

**문제 요약**  
정렬 여부를 알 수 없는 `N×N` 행렬에서 상위 N개의 값을 찾는다.

**접근 방법 (Min-Heap)**  
- 크기 N의 최소 힙 유지  
- 새로운 값이 힙의 최솟값보다 크면 교체

**복잡도**  
- Time: `O(N² log N)`  
- Space: `O(N)`

---

## 4. Position of k

**문제 요약**  
행과 열이 모두 정렬된 행렬에서 값 `k`의 위치를 찾는다.

**접근 방법 (Staircase Search)**  
- 오른쪽 위에서 시작  
- `>`이면 왼쪽, `<`이면 아래로 이동

**복잡도**  
- Time: `O(N)`  
- Space: `O(1)`

---

## 5. Matrix Addition

**문제 요약**  
여러 구간 업데이트를 효율적으로 처리한다.

**접근 방법 (2D Difference Array)**  
- 변화 지점만 기록  
- 마지막에 누적합으로 전체 반영

**복잡도**  
- Time: `O(N²)`  
- Space: `O(N²)`

---

## 6. Half-Circle Property

**문제 요약**  
모든 점이 하나의 반원 내에 존재하는지 판별한다.

**접근 방법**  
- 각 점을 `atan2`로 극각 변환  
- 각도 정렬 후 최대 간격 계산

**복잡도**  
- Time: `O(N log N)`  
- Space: `O(N)`

---

## 7. Train Rearrangement

**문제 요약**  
T자 철도에서 스택(LIFO)을 이용해 기차를 `1..N` 순서로 재배열 가능한지 판단한다.

**접근 방법**  
- 스택 시뮬레이션  
- 현재 원하는 번호와 비교하며 push/pop

**복잡도**  
- Time: `O(N)`  
- Space: `O(N)`

---

## 8. Agony of Engineer

**문제 요약**  
두 건물 간 단자 연결 관계를 최소 이동으로 복원한다.

**핵심 아이디어**  
- 단자를 하나씩 확인하지 않음  
- 연결/검사/정리(clean)/이동을 묶어 정보 극대화  
- 주어진 API 기반으로 최종 매핑 구성

---

## 10. Matrix Power Fibonacci / Two Pointers / Sliding Window

### Matrix Power Fibonacci
- 행렬 거듭제곱 + 분할 정복
- Time `O(log n)`

### Two Pointers
- 부분합 ≥ S 인 최소 길이 구간 탐색
- Time `O(N)`, Space `O(1)`

### Sliding Window
- 문자열 패턴 빈도 비교
- Time `O(N)`

---

## 11. Knapsack / Climbing Stairs

### Knapsack (0/1)
- DP 기반 최적 가치 계산
- Time `O(NW)`, Space `O(W)` 가능

### Climbing Stairs
- `dp[i]=dp[i-1]+dp[i-2]`
- Time `O(N)`
