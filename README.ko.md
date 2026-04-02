# YK 운영 플랫폼

🌍 English version: [README.md](README.md)

---

MMORPG **열혈강호 W(The Ruler of The Land W)**의 라이브 서비스 운영을 지원하기 위해 개발된 웹 기반 운영 관리 시스템입니다.

본 시스템은 **게임 서버가 외부망과 완전히 분리된 환경**에서,
운영자가 안전하게 실시간 운영 작업을 수행할 수 있도록 설계되었습니다.

---

## 📌 프로젝트 배경

게임 서버는 보안상의 이유로 외부 네트워크와 격리된 상태로 운영되었습니다.
이로 인해 다음과 같은 문제가 존재했습니다:

* 운영자가 게임 서버에 직접 접근 불가
* 모든 운영 작업은 간접적인 방식으로 처리 필요
* 실시간 운영 작업(아이템 지급, 공지, 유저 관리 등)의 안정성과 추적성 확보 필요

---

## 🧩 해결 방안

운영 플랫폼과 게임 서버 사이에 **Interface Server를 두는 구조**를 설계하여
모든 요청이 해당 서버를 통해 전달되도록 구현했습니다.

* 운영툴 → Interface Server → 게임 서버 구조
* 게임 서버 직접 접근 차단
* 요청 검증 및 로깅 중앙화

이를 통해 보안을 유지하면서도 안정적인 운영이 가능한 구조를 구축했습니다.

---

## 🏗 시스템 아키텍처

본 시스템은 3-Tier 구조를 기반으로 구성되었습니다:

* Presentation Layer: JSP 기반 관리자 UI
* Application Layer: Spring 기반 백엔드
* Data Layer: MariaDB / MSSQL

- Interface Server를 통한 보안 통신 구조

(상세 내용은 `docs/architecture.md` 참고)

---

## 🛠 주요 기능

* 공지사항 등록 및 관리
* 게임 아이템 지급 기능
* 유저 정보 조회 및 관리
* 운영 이력 로그 관리
* 권한 기반 운영자 관리 시스템

---

## 🧪 기술 스택

Backend

* Java
* Spring Framework (eGovFramework)
* MyBatis

Database

* MariaDB
* MSSQL

Infrastructure

* AWS EC2
* AWS RDS
* AWS S3
* AWS CloudWatch

Frontend

* JSP
* JavaScript
* jQuery

---

## 👨‍💻 담당 역할

* 전체 시스템 아키텍처 설계
* Spring 기반 백엔드 개발
* Interface Server 연동 구조 설계 및 구현
* 데이터베이스 설계 및 쿼리 작성
* AWS 환경 배포 및 운영

---

## 📈 성과

* 게임 서버를 외부에 노출하지 않고도 안정적인 운영 환경 구축
* 운영 업무 자동화를 통해 작업 효율 향상
* 운영 이력 관리 체계 구축으로 추적 가능성 확보

---

## 📄 상세 문서

> 모든 상세 문서는 한글 기준으로 작성되었습니다.

* [프로젝트 개요](docs/project-overview.ko.md)
* [시스템 아키텍처](docs/architecture.md)
* [비즈니스 흐름](docs/business-flow.md)
* [기술 의사결정](docs/technical-decisions.md)
* [기여 내용](docs/my-contributions.md)
* [트러블슈팅](docs/troubleshooting.md)
