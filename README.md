<h1 align="center">EMERGENCY <span>4</span> DELUXE</h1>

<p align="center">
  <strong>한국어 번역 패치</strong><br>
  Community Korean Translation
</p>

<p align="center">
  <img alt="Version: 0.1.0 draft" src="https://img.shields.io/badge/version-0.1.0--draft-e74c3c?style=for-the-badge">
  <img alt="Platform: Windows Steam" src="https://img.shields.io/badge/platform-Windows%20%2F%20Steam-2d3138?style=for-the-badge">
  <img alt="Language: Korean" src="https://img.shields.io/badge/language-Korean-2878b5?style=for-the-badge">
</p>

> [!NOTE]
> **em4-korean-translation**은 Steam판 **EMERGENCY 4 Deluxe**의 비공식 한국어 번역 프로젝트입니다. 메뉴, 차량·장비 설명, 행동 안내, 임무와 대사를 한국어로 번역하고, 한국어 글꼴과 UI 수정 파일을 함께 제공합니다.

오류를 발견하면 [Issues](https://github.com/omsiyong/em4-korean-translation/issues)에 화면과 상황을 함께 남겨 주세요.

> [!IMPORTANT]
> **설치된 EMERGENCY 4 Deluxe 원본 게임이 필요합니다.** 이 저장소는 번역 패치이며, 게임 실행 파일과 음성·영상·차량 그래픽을 제공하지 않습니다.

## Download

저장소 상단의 **Code → Download ZIP**으로 다운로드하고 압축을 풉니다. 압축을 푼 폴더 안의 `Data`가 설치할 패치입니다.

설치 프로그램이나 명령어 입력은 필요하지 않습니다.

## Installation

1. **준비 및 백업.** 게임을 종료합니다. Steam 라이브러리에서 **관리 → 로컬 파일 보기**를 선택하여 `Em4.exe`와 `Data`가 있는 설치 폴더를 엽니다. 기존 `Data` 폴더와 `em4.cfg` 파일을 다른 위치에 백업합니다.
2. **한국어 폴더 만들기.** 게임의 `Data/Lang`에서 **`en` 전체를 복사**하고 복사본 이름을 **`kr`**로 바꿉니다. 원래 `en`의 이름은 바꾸지 않습니다. **기존 음성과 영상을 복사하기 위해 필수적으로 진행하여야 합니다**
3. **패치 붙여넣기.** 다운로드한 패치의 **`Data` 폴더를 게임 설치 폴더에 붙여넣고**, 파일 교체를 물으면 **덮어쓰기**를 선택합니다. 한국어 XML의 위치는 `Data/Lang/kr`입니다.
4. **언어 변경.** 게임의 `em4.cfg`를 텍스트 편집기로 열어 `s_language` 값을 **`kr`**로 바꿉니다. 파일의 기존 인코딩을 유지하여 저장합니다.

   ```xml
   <var name="s_language" value="kr" />
   ```

5. **게임 실행.** 평소처럼 Steam에서 게임을 실행합니다.

> [!TIP]
> 패치의 `Data`는 `Em4.exe`와 같은 위치에 넣습니다. `Data/Data`로 중복해서 넣지 마세요. 해상도나 `fs_basepath`는 이 패치를 위해 수정할 필요가 없습니다.

### When something goes wrong

- **한국어가 나오지 않음:** `s_language="kr"`인지, 번역 XML이 `Data/Lang/kr`에 있는지 확인합니다.
- **음성·영상 누락:** 원래 게임의 `en` 폴더 전체를 `kr`로 복사했는지 확인합니다. 패치 ZIP만으로는 음성과 영상이 채워지지 않습니다.
- **기존 테스트 실행 도구 사용:** 그 도구로 원래 설정을 복구한 뒤 패치를 적용합니다.
- **글자 잘림·누락 또는 번역 오류:** [Issues](https://github.com/omsiyong/em4-korean-translation/issues)에 스크린샷, 임무 이름, 직전 행동을 함께 기록합니다.
- **다른 모드와 충돌:** 확인한 Steam 원본 기준으로 제작했습니다. 문제가 생기면 백업본으로 복구합니다.

## Updating & Uninstalling

**업데이트:** 새 버전의 `Data`를 같은 위치에 덮어넣습니다. 이미 이 방식으로 만든 `kr` 폴더가 있으면 `en`을 다시 복사할 필요는 없습니다. 게임 업데이트나 Steam 파일 무결성 검사 후에는 패치 적용 여부를 확인하세요.

**영어로 전환:** `s_language` 값을 `en`으로 바꿉니다. 공용 UI와 글꼴에는 패치가 적용된 상태가 유지됩니다.

**완전히 제거:** 백업한 원래 `Data`와 `em4.cfg`로 복구하고, 새로 추가한 `Data/Lang/kr`, `Data/Fonts/korean_probe.def`, `korean_probe.dds`도 제거합니다. Steam 파일 무결성 검사는 덮어쓴 원본 파일을 복구할 수 있지만 새로 추가한 파일은 직접 정리해야 합니다.

## Documentation

| 문서 | 내용 |
| --- | --- |
| [Notices](NOTICE.md) | 글꼴 및 원본 자산에 관한 고지 |
| [Font license](licenses/OFL.txt) | 한국어 글꼴 추가분의 SIL Open Font License 1.1 |
| [Font metadata](licenses/font-metadata.txt) | 사용한 글꼴의 저작권 및 라이선스 정보 |

## Repository layout

```text
em4-korean-translation/
├── Data/
│   ├── Lang/kr/          한국어 언어 XML
│   ├── Fonts/            한국어를 지원하는 글꼴 파일
│   └── UI/               글꼴 연결 및 표시 영역 수정
├── licenses/             글꼴 라이선스와 메타데이터
├── NOTICE.md             글꼴 및 원본 자산 고지
└── README.md
```

## Contributing

오역, 누락, 글자 잘림 등의 제보와 번역 개선 제안을 환영합니다. [Issues](https://github.com/omsiyong/em4-korean-translation/issues)에 원문 또는 현재 번역, 수정 제안과 해당 상황을 남겨 주세요. 번역 데이터 수정 제안은 Pull Request로도 보낼 수 있습니다.

## License

EMERGENCY 4 Deluxe와 원문·원본 자산에 관한 권리는 각 권리자에게 있습니다. 이 프로젝트는 제작사·배급사와 무관한 비공식 팬 번역입니다.

Noto Sans KR에서 생성한 한국어 글꼴 추가분은 [SIL Open Font License 1.1](licenses/OFL.txt)을 따릅니다. 이 라이선스가 게임 원본 부분이나 번역 전체에 적용되는 것은 아닙니다. 자세한 고지는 [NOTICE.md](NOTICE.md)를 참고하세요.

번역의 별도 오픈소스 라이선스는 아직 지정하지 않았습니다.
