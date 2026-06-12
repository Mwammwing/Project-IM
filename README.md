# Project IM

> **Citizens NPC 기반 차세대 인게임-웹 통합 커머스 플랫폼**
> 
> 마인크래프트 서버 운영의 고질적인 불편함인 "복잡한 인게임 명령어 기반의 NPC 및 상점 관리"를 모던 웹 기술(Flask)과 자바 플러그인 연동을 통해 중앙 집권식으로 혁신하는 프로젝트입니다.

---

## 핵심 기능 (Features)

* **중앙 관리 웹 대시보드:** 매번 인게임에서 명령어를 치는 대신, 깔끔한 웹 UI(Tailwind CSS)를 통해 NPC의 대사 트리와 상점 아이템 가격, 재고를 실시간으로 제어합니다.
* **비동기 데이터 동기화:** 마인크래프트 서버의 메인 스레드가 멈추지 않도록 `HttpClient`를 활용한 비동기(Async) HTTP 통신으로 Flask API 서버와 데이터를 주고받습니다.
* **동적 인게임 GUI 상점:** 웹 대시보드에서 수정된 아이템 ID, 이름, 가격 정보가 유저가 게임 내에서 NPC를 우클릭하는 순간 실시간 가상 인벤토리 상점 창(GUI)으로 반영됩니다.

---

## 기술 스택 (Tech Stack)

### Web & Backend
| 구분 | 기술 스택 |
| :--- | :--- |
| **Backend** | Python (Flask), APScheduler |
| **Database** | SQLite |
| **Frontend** | HTML5, Vanilla JavaScript, Tailwind CSS |
| **Infra** | Oracle Cloud Infrastructure (Ubuntu Environment), Nginx |

### Minecraft Plugin
| 구분 | 기술 스택 |
| :--- | :--- |
| **Language** | Java (JDK 17+) |
| **API** | Paper-API, Spigot-API |
| **Dependency** | Citizens API (NPC Management), Gson |
| **Build Tool** | Maven |

---

## 시스템 아키텍처 (Architecture)

```text
[인게임 유저] ➔ NPC 우클릭 ➔ [마크 서버 (비동기 API 요청)] ➔ [Flask 중앙 서버] ➔ [SQLite DB]
                                                                     ▲
                                                      [운영자 웹 대시보드 (JS 제어)]
