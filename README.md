---
type: workshop
title: Azure Basic Workshop
description: Azure Portal에서 가상 네트워크, VM, Load Balancer와 SQL Database를 구성하고 웹 애플리케이션을 배포하는 한국어 워크샵
level: beginner
authors: [Anna Jeong]
contacts: ["@Anna-Jeong-MS"]
duration_minutes:
tags: [azure, virtual-network, virtual-machine, load-balancer, azure-sql]
language: ko
execution: [portal]
status: draft
source: original
last_updated: 2026-10-07
validated_on:
original_content_date: 2025-04-17
---

# Azure Basic Workshop

Azure Basic Workshop은 애저 인프라 코어 서비스들을 직접 Hands on Lab 할 수 있는 컨텐츠입니다.

> **참고**: 현재 문서 상태는 `draft`입니다. 최신 Azure Portal에서 처음부터 끝까지 실행한 검증일은 아직 기록되지 않았습니다.

## 사전 요구사항

- Azure Portal에 로그인할 계정과 실습 리소스를 만들 수 있는 Azure 구독이 필요합니다.
- Azure Pass를 사용하는 행사라면 운영자가 제공한 프로모 코드를 준비합니다. 계정과 사용자 생성 절차는 [사전 준비](00-prerequisites/README.md)를 참고합니다.
- 실습에서 Azure 리소스를 생성하므로 비용이 발생할 수 있습니다. 사용할 구독과 리소스 구성을 확인하고, 실습을 마치면 각 랩의 정리 절차를 따릅니다.

<!-- TODO: 저자 확인 — 행사별 구독·권한 조건, 허용 리전, 리소스 비용과 한도 -->

## 학습 경로

[사전 준비](00-prerequisites/README.md)

  Azure Pass 활성화와 Microsoft Entra ID 사용자 생성을 준비합니다.

[Basic](01-basic/README.md)

  애저의 가장 기본적인 서비스인 가상 네트워크와 가상 머신을 활용하여 웹 애플리케이션을 배포합니다. 가상 네트워크를 구성하고, 가상머신을 배포한 후 웹서버를 배포합니다.

[Advanced](02-advanced/README.md)

  가상 머신에 웹 애플리케이션을 배포하고, 웹 애플리케이션의 데이터를 관리하기 위한 SQL 데이터베이스를 구성합니다. Load Balancer의 frontend IP를 웹 애플리케이션을 진입점으로 사용하고, 가상 머신을 백 엔드 풀로 사용합니다. 이렇게 구성하면 웹 애플리케이션을 논리적으로 격리할 수 있으며, 추후 애플리케이션의 확장을 고려한 아키텍처를 설계할 수 있습니다.

## 소요 시간

전체 및 랩별 소요 시간은 확인 전입니다.

<!-- TODO: 저자 작성 — 실제 완주 시간을 확인한 뒤 루트·랩 duration_minutes와 본문을 함께 갱신 -->

## 실행 환경과 외부 의존성

이 워크샵은 포털형입니다. Azure Portal에서 리소스를 구성하고, Azure Bastion으로 VM에 접속해 본문의 명령을 실행합니다. Codespaces나 로컬 개발 환경을 별도로 구성하지 않습니다.

| 의존성 | 사용 위치 | 확인 사항 |
|---|---|---|
| [BasicApp](https://github.com/Anna-Jeong-MS/BasicApp) | Basic의 웹 애플리케이션 배포 | 접근 가능성·라이선스·크기·대체 경로 확인 필요 |
| [TodoApp](https://github.com/Anna-Jeong-MS/TodoApp) | Advanced의 웹 애플리케이션과 SQL 연결 | 접근 가능성·라이선스·크기·대체 경로 확인 필요 |
| Ubuntu·Python 패키지 저장소 | VM에서 패키지 설치 | 본문의 이미지·설치 명령과 현재 패키지 조합 재검증 필요 |
| [Microsoft 패키지 저장소](https://packages.microsoft.com/) | Advanced의 ODBC 드라이버 설치 | VM 운영체제와 드라이버 호환성 재검증 필요 |

외부 앱과 패키지는 이 저장소에 포함하지 않습니다. 각 랩에서 안내하는 외부 저장소와 서비스를 사용합니다.

## 검증과 정리

Basic은 VM의 공용 IP로 웹 애플리케이션에 접속합니다. Advanced는 Load Balancer의 공용 IP로 접속한 뒤 SQL 연결과 목록 기능을 확인합니다. 자세한 절차는 [Basic 검증](01-basic/README.md#검증)과 [Advanced 검증](02-advanced/README.md#검증)을 따릅니다.

실습 후에는 [Basic 정리](01-basic/README.md#정리-clean-up)와 [Advanced 정리](02-advanced/README.md#정리-clean-up)에 따라 실습 리소스 그룹을 정리합니다. 삭제 전에는 해당 리소스 그룹에 다른 용도의 리소스가 없는지 확인합니다.

문서의 `last_updated`는 수정일입니다. `validated_on`은 사람이 포털에서 전체 실습을 완료한 날짜만 기록하며, 현재는 공란입니다. 원본 콘텐츠 수정일은 `2025-04-17`입니다.

<!-- TODO: 저자 검증 — 포털 UI와 스크린샷, Advanced의 NAT Gateway 누락·VM 이름 불일치, 외부 앱 및 패키지 설치, 리소스 삭제 완료 확인 -->
<!-- TODO: 저자 확인 — authors·contacts가 현재 저자 표기와 유지보수 연락처에 맞는지 확인 -->

## 출처와 기여

기존 [Azure Basic Workshop](https://github.com/Anna-Jeong-MS/AzureBasicWorkshop)의 실습 내용을 유지하며 문서 구조와 경로를 정리했습니다.

기여 방법은 [CONTRIBUTING](CONTRIBUTING.md), 보안 문제 제보는 [SECURITY](SECURITY.md), 행동 강령은 [Microsoft Open Source Code of Conduct](.github/CODE_OF_CONDUCT.md)를 참고합니다.

## 라이선스

기존 Microsoft 저작권 고지와 [MIT 라이선스](LICENSE.md)를 유지합니다. 문서·이미지의 CC BY-SA 4.0 전환은 필요한 동의가 확인되기 전까지 적용하지 않습니다.
