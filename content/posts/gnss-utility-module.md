---
title: "GNSS Utility Module (common.c)"
date: 2025-06-13T10:00:00+09:00
draft: false
tags: ["GNSS", "GPS", "C언어", "라이브러리"]
categories: ["기술"]
author: "Yongrae Jo"
description: "GNSS 라이브러리의 다양한 유틸리티 함수들을 제공하는 기반 모듈에 대한 설명입니다."
---

# GNSS Utility Module (common.c)

GNSS 라이브러리의 다양한 유틸리티 함수들을 제공하는 기반 모듈입니다.

## ▶ 목차

1. [데이터 타입 구조](#데이터-타입-구조)
2. [함수 구조](#함수-구조)
3. [사용 예시](#사용-예시)
4. [데이터 타입 목록](#데이터-타입-목록)
5. [함수 목록](#함수-목록)

---

## ◆ 데이터 타입 구조

GNSS 모듈에서 사용되는 기본 데이터 타입들을 정의합니다.

### 기본 타입 정의

```c
typedef struct {
    double lat;    // 위도 (degrees)
    double lon;    // 경도 (degrees)
    double alt;    // 고도 (meters)
} gnss_position_t;

typedef struct {
    double x, y, z;    // ECEF 좌표계 (meters)
} gnss_ecef_t;
```

## ◆ 함수 구조

주요 유틸리티 함수들의 구조와 용도에 대해 설명합니다.

### 좌표 변환 함수

- `llh_to_ecef()`: 위경고도를 ECEF 좌표계로 변환
- `ecef_to_llh()`: ECEF 좌표계를 위경고도로 변환
- `deg_to_rad()`: 도 단위를 라디안으로 변환

## ◆ 사용 예시

```c
#include "common.h"

int main() {
    gnss_position_t pos = {37.5665, 126.9780, 50.0}; // 서울시청
    gnss_ecef_t ecef;
    
    llh_to_ecef(&pos, &ecef);
    printf("ECEF: X=%.2f, Y=%.2f, Z=%.2f\n", ecef.x, ecef.y, ecef.z);
    
    return 0;
}
```

## ◆ 데이터 타입 목록

| 타입명 | 설명 | 용도 |
|--------|------|------|
| `gnss_position_t` | 위경고도 구조체 | GPS 위치 정보 저장 |
| `gnss_ecef_t` | ECEF 좌표 구조체 | 지구중심 좌표계 |
| `gnss_time_t` | GPS 시간 구조체 | 시각 정보 관리 |

## ◆ 함수 목록

### 좌표 변환
- `llh_to_ecef()` - 위경고도 → ECEF 변환
- `ecef_to_llh()` - ECEF → 위경고도 변환
- `xyz_to_enu()` - XYZ → ENU 변환

### 수학 유틸리티
- `deg_to_rad()` - 도 → 라디안 변환
- `rad_to_deg()` - 라디안 → 도 변환
- `dot_product()` - 벡터 내적 계산

### 시간 함수
- `gps_to_utc()` - GPS 시간 → UTC 변환
- `utc_to_gps()` - UTC → GPS 시간 변환

---

이 모듈은 GNSS 애플리케이션 개발의 기반이 되는 핵심 유틸리티들을 제공합니다.
