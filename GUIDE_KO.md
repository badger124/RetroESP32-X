# RetroESP32-X 파일 설명서

이 문서는 RetroESP32-X 저장소에 포함된 모든 파일과 폴더에 대한 한글 설명입니다.

---

## 프로젝트 개요

**RetroESP32-X**는 게임보이 포켓(Gameboy Pocket) 본체에 그대로 끼워 넣을 수 있는 교체용 PCB(인쇄 회로 기판)입니다. ESP32 모듈을 기반으로 하며, [Ducalex의 Retro-Go 펌웨어](https://github.com/ducalex/retro-go)를 사용합니다. OSHWA(오픈소스 하드웨어 협회) 인증(UID: CA000030)을 받은 오픈소스 하드웨어 프로젝트이며, CC-BY-SA-4.0 라이선스로 배포됩니다.

---

## 루트(최상위) 파일

| 파일명 | 설명 |
|---|---|
| `README.md` | 프로젝트 전체 소개 문서입니다. RetroESP32-X의 특징, 업데이트된 기능(2.6인치 LCD, USB-C 충전, 시리얼 핀 헤더 등), 이미지, 작성자 정보, 지원 방법 등을 영문으로 설명합니다. |
| `LICENSE.md` | 이 프로젝트에 적용되는 **Creative Commons Attribution-ShareAlike 4.0 International (CC-BY-SA-4.0)** 라이선스 전문입니다. 출처를 표시하고 동일한 조건으로 공유할 경우 자유롭게 사용·수정·배포할 수 있습니다. |
| `CODE_OF_CONDUCT.md` | 프로젝트 참여자들이 지켜야 할 **행동 강령**입니다. 서로 존중하고 포용적인 환경을 만들기 위한 기준과 위반 시 처리 절차를 담고 있습니다. |
| `SPONSORS.md` | 프로젝트 후원자 목록 파일입니다. (현재 내용은 비어 있습니다.) |
| `.gitignore` | Git 버전 관리에서 **추적하지 않을 파일·폴더 목록**을 지정합니다. 빌드 산출물, 임시 파일 등이 실수로 커밋되지 않도록 방지합니다. |
| `GUIDE_KO.md` | 이 파일입니다. 저장소 내 모든 파일과 폴더에 대한 **한글 설명서**입니다. |

---

## `assets/` 폴더 — 이미지 자산

프로젝트에서 사용하는 이미지 파일들이 담긴 폴더입니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32-X.png` | RetroESP32-X 완성 보드의 **메인 이미지**입니다. README에서 프로젝트 대표 사진으로 사용됩니다. |
| `RetroESP32-X.top.png` | RetroESP32-X 보드의 **상단(앞면) 이미지**입니다. |
| `RetroESP32-X.bottom.png` | RetroESP32-X 보드의 **하단(뒷면) 이미지**입니다. |
| `RetroESP32.png` | 이전 세대 모델인 **구형 RetroESP32** 보드 이미지입니다. |
| `RetroESP32.serial.top.png` | **시리얼 확장 보드** 상단 이미지입니다. |
| `RetroESP32.serial.bottom.png` | **시리얼 확장 보드** 하단 이미지입니다. |
| `certification-mark-CA000030-wide.png` | OSHWA(오픈소스 하드웨어 협회) 인증 마크 이미지입니다. 인증 번호는 **CA000030**입니다. |
| `github.bmp` | GitHub 로고 이미지(BMP 포맷)입니다. |
| `logo.bmp` | 프로젝트 로고 이미지(BMP 포맷)입니다. |

---

## `bom/` 폴더 — 부품 목록 (Bill of Materials)

PCB 제작에 필요한 **부품 목록(BOM)** 파일들이 담긴 폴더입니다. 각 CSV 파일에는 부품의 수량, 회로도 지정 번호(Designator), 부품 번호(MPN), 구매 링크 등이 포함되어 있습니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32-X.csv` | **RetroESP32-X 메인 보드**의 전체 부품 목록입니다. 콘덴서, 저항, ESP32 모듈, LCD, USB-C 커넥터, 오디오 잭, 충전 IC 등 모든 부품과 Digi-Key 구매 링크가 포함되어 있습니다. |
| `RetroESP32-X.clean.csv` | `RetroESP32-X.csv`와 동일한 부품 목록이지만, Eagle PCB 소프트웨어에서 내보낸 **정제된 형식**으로 패키지(Package) 및 장치(Device) 정보도 함께 포함되어 있습니다. |
| `RetroESP32.serial.csv` | **시리얼 확장 보드**의 전체 부품 목록입니다. 구매 링크가 포함된 CSV 형식입니다. |
| `RetroESP32.serial.screen.csv` | 시리얼 확장 보드에서 **화면(스크린) 커넥터** 관련 부품만 별도로 정리한 목록입니다. |
| `RetroESP32.serial.top.csv` | 시리얼 확장 보드에서 **SD 카드 슬롯 및 화면 커넥터** 관련 부품을 정리한 목록입니다. |

---

## `eagle/` 폴더 — Eagle PCB 설계 파일

Autodesk Eagle PCB 소프트웨어로 작성된 **회로 설계 파일**들이 담긴 폴더입니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32-X.brd` | RetroESP32-X 메인 보드의 **PCB 레이아웃(기판 배치) 파일**입니다. 부품 위치, 배선(라우팅), 레이어 정보 등이 담겨 있습니다. Eagle에서 열어 편집하거나 거버 파일 생성에 사용합니다. |
| `RetroESP32-X.sch` | RetroESP32-X 메인 보드의 **회로도(Schematic) 파일**입니다. 각 부품 간의 전기적 연결 관계를 나타냅니다. |
| `RetroESP32.serial.brd` | **시리얼 확장 보드**의 PCB 레이아웃 파일입니다. |
| `RetroESP32.serial.sch` | **시리얼 확장 보드**의 회로도 파일입니다. |
| `RetroESP32.shim.brd` | **심(Shim) 보드**의 PCB 레이아웃 파일입니다. 심 보드는 본체 두께 조정이나 핀 브리지 역할을 합니다. |
| `RetroESP32.shim.sch` | **심(Shim) 보드**의 회로도 파일입니다. |

---

## `gerber/` 폴더 — 거버 파일 (PCB 제조용)

PCB 제조 업체에 전달하는 **거버(Gerber) 파일**들이 담긴 폴더입니다. 거버 파일은 PCB 제조 표준 파일 형식으로, 기판의 각 레이어(구리층, 솔더마스크, 실크 스크린 등)를 정의합니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32-X.zip` | **RetroESP32-X 메인 보드** 거버 파일 압축본입니다. PCB 제조 업체(예: JLCPCB, OSHPark 등)에 이 파일을 제출하면 기판을 제작할 수 있습니다. |
| `RetroESP32.serial.zip` | **시리얼 확장 보드** 거버 파일 압축본입니다. |
| `RetroESP32.serial.osh.zip` | OSHPark(오픈소스 PCB 제조 서비스) 규격에 맞춘 **시리얼 확장 보드** 거버 파일 압축본입니다. |
| `RetroESP32.shim.zip` | **심(Shim) 보드** 거버 파일 압축본입니다. |
| `RetroESP32.shim.osh.zip` | OSHPark 규격에 맞춘 **심(Shim) 보드** 거버 파일 압축본입니다. |

---

## `dxf/` 폴더 — DXF 도면 파일

**DXF(Drawing Exchange Format)** 형식의 기구 설계 도면 파일들이 담긴 폴더입니다. DXF는 CAD(컴퓨터 지원 설계) 소프트웨어에서 주로 사용하는 2D 도면 형식으로, 케이스 절삭, 레이저 커팅, 3D 모델링 기준선 제작 등에 활용됩니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32.serial.dxf` | **시리얼 확장 보드**의 DXF 기구 도면 파일입니다. |
| `RetroESP32.serial 2.dxf` | 시리얼 확장 보드의 DXF 기구 도면 파일로, `RetroESP32.serial.dxf`와 함께 제공되는 **추가 도면 파일**입니다. 두 파일의 정확한 차이는 CAD 소프트웨어로 열어 확인하시기 바랍니다. |

---

## `lbr/` 폴더 — Eagle 라이브러리 파일

Eagle PCB 소프트웨어에서 사용하는 **커스텀 부품 라이브러리** 파일이 담긴 폴더입니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32.lbr` | RetroESP32 프로젝트 전용 **Eagle 부품 라이브러리**입니다. 회로도 심볼(Symbol), PCB 풋프린트(Footprint), 3D 패키지 정보 등 프로젝트에 사용된 커스텀 부품 정의가 담겨 있습니다. Eagle에서 회로도 및 PCB를 편집할 때 이 라이브러리를 불러와야 합니다. |

---

## `pdf/` 폴더 — PDF 문서 파일

PDF 형식으로 내보낸 **회로도 문서** 파일이 담긴 폴더입니다.

| 파일명 | 설명 |
|---|---|
| `RetroESP32.serial.pdf` | **시리얼 확장 보드**의 회로도를 PDF로 내보낸 파일입니다. Eagle 없이도 누구나 열람할 수 있도록 범용 형식으로 제공됩니다. |

---

## `.github/` 폴더 — GitHub 설정 파일

GitHub 플랫폼 관련 자동화 및 설정 파일들이 담긴 폴더입니다.

### `.github/FUNDING.yml`
GitHub **후원(Sponsorship)** 버튼 설정 파일입니다. 저장소 페이지에 후원 버튼이 표시되도록 후원 플랫폼 및 계정 정보를 지정합니다.

### `.github/ISSUE_TEMPLATE/` 폴더 — 이슈 템플릿

| 파일명 | 설명 |
|---|---|
| `bug_report.md` | **버그 신고** 이슈 템플릿입니다. 사용자가 버그를 보고할 때 재현 방법, 기대 동작, 스크린샷, 환경 정보 등을 체계적으로 작성할 수 있도록 안내합니다. |
| `feature_request.md` | **기능 요청** 이슈 템플릿입니다. 새로운 기능이나 개선 사항을 제안할 때 문제 설명, 원하는 해결책, 대안 등을 작성할 수 있도록 안내합니다. |
| `FUNDING.yml` | 이 파일은 일반적인 GitHub 규칙에서는 `.github/` 루트에만 두어야 하지만, 이 저장소에서는 `ISSUE_TEMPLATE/` 하위에도 동일한 이름의 파일이 존재합니다. 이는 저장소 내 **잘못 배치된 중복 파일**로 보이며, 실제 후원 버튼 기능은 `.github/FUNDING.yml`에 의해 제어됩니다. |

### `.github/workflows/` 폴더 — GitHub Actions 워크플로우

| 파일명 | 설명 |
|---|---|
| `static.yml` | **GitHub Pages 자동 배포** 워크플로우 파일입니다. `main` 브랜치에 코드가 푸시될 때마다 저장소 전체 내용을 GitHub Pages에 자동으로 배포합니다. |

---

## 보드 종류 요약

이 저장소에는 세 가지 보드의 설계 파일이 포함되어 있습니다.

| 보드명 | 설명 |
|---|---|
| **RetroESP32-X** | 메인 보드. 게임보이 포켓에 장착되는 핵심 PCB로, ESP32 모듈, 2.6인치 ILI9342C LCD, USB-C 충전 포트, 오디오 출력 등이 포함됩니다. |
| **RetroESP32.serial** | 시리얼 핀 브레이크아웃 확장 보드. 디버깅 및 시리얼 통신용 핀 헤더를 제공합니다. |
| **RetroESP32.shim** | 심(Shim) 보드. 본체와 메인 보드 사이의 간격 조정 또는 핀 연결을 위한 얇은 보조 기판입니다. |
