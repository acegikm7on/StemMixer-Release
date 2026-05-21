<h1><img src="stemmixer.ico" alt="" width="40" height="40" style="vertical-align: middle; margin-right: 0.35em;"> StemMixer</h1>

![StemMixer screenshot](screenshot.jpg)

곡을 **보컬 · 드럼 · 베이스 · 기타(건반)** 네 가지 악기 스템으로 나눈 뒤, 피치·믹스·내보내기까지 한 번에 할 수 있는 Windows용 음원 편집 프로그램입니다.

## 다운로드 (Windows)

[**StemMixer v1.0.0 Installer (exe)**](https://github.com/acegikm7on/StemMixer-Release/releases/latest/download/StemMixer_v1.0.0_Installer.exe)

> 소스 코드는 비공개 저장소에서 개발됩니다. 설치 파일과 문서는 [StemMixer-Release](https://github.com/acegikm7on/StemMixer-Release)에서 공개합니다.

---

## 주요 기능

### AI 스템 분리

- 한 곡을 **보컬, 드럼, 베이스, 기타/건반** 스템으로 자동 분리합니다.
- 분리가 끝나면 각 스템을 바로 재생·조절할 수 있습니다.

### 클라우드 서버 상태 표시 (하단 상태줄)

상태 텍스트(예: **준비 완료**) 왼쪽의 **작은 원형 표시**는, 실시간 서버 연결 상태가 아니라 **최근 클라우드 요청 결과**를 보여 주는 안내입니다.

| 색 | 의미 |
|----|------|
| **회색** | 최근에 클라우드 서버 응답이 없음 (에러가 아님) |
| **초록** | 최근 요청이 성공함 (일정 시간 후 회색으로 돌아감) |
| **주황** | 지금 스템 분리 중 |
| **빨강** | 최근 스템 분리(또는 관련 요청) 실패 |

- **스템 분리는 표시등이 초록일 때 시작하는 것을 권장합니다.** 초록이면 클라우드 서버가 최근에 준비된 상태라, 분리가 더 빨리 진행될 가능성이 큽니다. 회색이면 잠시 기다리거나, 원을 눌러 서버를 깨운 뒤 초록이 될 때까지 기다려 주세요.
- 앱을 연 뒤 잠시 후 **한 번** 클라우드 서버를 미리 깨우려 시도합니다(분리 작업 없음). 실패해도 알림은 뜨지 않으며 표시는 회색으로 유지됩니다.
- **회색**일 때 원을 클릭하면 서버 깨우기를 다시 시도할 수 있습니다.
- 회색으로 바뀔 때 서버에 상태 확인 요청을 보내지 않습니다.

### 피치 시프트 (키 변경)

- **±2 반음** 범위에서 키를 올리거나 내릴 수 있습니다.
- 보컬·베이스·기타 스템에 피치를 적용합니다. (드럼은 원음 유지)
- **보컬** 피치 변경 시 포먼트(목소리 특성)를 최대한 유지하도록 처리합니다.

### 악기별 비율 조절 (믹서)

- 네 스템 각각의 **볼륨을 0~100%** 슬라이더로 세밀하게 조절합니다.
- 보컬만 크게, 드럼만 줄이기 등 원하는 밸런스로 실시간 미리듣기가 가능합니다.

### 프리셋

- **원본**, **보컬만**, **보컬 제거**, **드럼만**, **드럼 제거**, **베이스만**, **베이스 제거**, **기타/건반만**, **기타/건반 제거** 등 자주 쓰는 조합을 버튼 한 번으로 적용합니다.
- **모노로 듣기** 옵션으로 스테레오·모노 청취를 전환할 수 있습니다.

### 로컬/YouTube 음원 가공

- PC에 있는 **음원 폴더**를 지정하면, 그 안의 곡들을 순서대로 불러와 분리·편집할 수 있습니다.
- 경로 입력란에 **YouTube 주소**(단일 영상·재생목록)를 넣으면, 오디오를 가져와 동일한 분리·편집 파이프라인에 연결합니다.

### 내보내기

- 현재 키·믹서 설정이 반영된 결과를 **WAV**(기본) 또는 **MP3**(128 kbps)로 저장합니다.

---

## 문제 해결

설치·실행 중 나오는 Windows 경고는 **앱이 손상됐다는 뜻이 아닙니다.** 공개 설치 파일이 코드 서명 없이 배포될 때 흔히 보이는 화면입니다.

### 설치할 때

| 증상 | 대처 |
|------|------|
| **「Windows의 PC 보호」 / SmartScreen** | **추가 정보** → **실행**을 선택합니다. 다운로드한 공식 설치 파일인지 주소를 확인하세요. |
| **사용자 계정 컨트롤(UAC)** 「이 앱이 디바이스를 변경할 수 있도록 허용하시겠습니까?」 | 설치에 관리자 권한이 필요합니다. **예**를 눌러 진행합니다. |
| 백신·보안 프로그램이 설치를 차단 | StemMixer 설치 폴더·`StemMixer.exe`를 예외(허용) 목록에 추가한 뒤 다시 시도합니다. |
| 설치가 중간에 멈춤 | 다른 설치 프로그램을 종료하고, 설치 파일을 다시 받아 실행합니다. |

### 실행 직후

| 증상 | 대처 |
|------|------|
| **필수 구성 요소 누락** (FFmpeg 등) | 설치가 불완전할 수 있습니다. 앱을 제거한 뒤 설치 파일로 **다시 설치**하세요. |
| **Cloud configuration** 오류로 앱이 바로 종료 | 배포본 설정 문제일 수 있습니다. [문의](#문의)로 설치 파일 버전과 메시지 전체를 알려 주세요. |
| **저장 공간 연결** 경고 (유휴 사전 분리 일시 중지) | 클라우드 업로드 경로 점검용 안내입니다. **직접 스템 분리**는 인터넷과 클라우드 서버가 정상이면 가능한 경우가 많습니다. 경고가 반복되면 문의해 주세요. |

### 클라우드 서버 표시등 · 스템 분리

| 증상 | 대처 |
|------|------|
| 오래 **회색**만 보임 | 앱을 연 지 3~5초 정도 기다립니다. 그래도 회색이면 표시등을 **클릭**해 서버 깨우기를 시도한 뒤 **초록**이 될 때까지 기다립니다. |
| **초록**인데 분리가 느림 | 곡 길이·네트워크·서버 대기열에 따라 수 분 걸릴 수 있습니다. 하단 진행률과 단계 문구를 확인하세요. |
| **주황**에서 오래 멈춘 것 같음 | 업로드·분리·다운로드 중일 수 있습니다. 가능하면 앱을 끄지 말고 기다립니다. |
| **빨강** | 네트워크 연결을 확인하고, 잠시 후 같은 곡으로 다시 시도합니다. 표시등이 **초록**일 때 시작하는 것을 권장합니다. |
| 분리를 눌렀는데 바로 실패 | 인터넷 연결, 방화벽·VPN, 회사망 차단 여부를 확인합니다. |

### YouTube · 폴더 ·보내기

| 증상 | 대처 |
|------|------|
| YouTube **로그인** 안내 | 브라우저에서 YouTube에 로그인한 뒤 앱에서 **다시 시도**합니다. |
| 브라우저 **로그인 정보를 읽을 수 없음** | 보안 프로그램·브라우저 쿠키 차단 설정을 확인합니다. |
| **유효하지 않은 경로 또는 URL** | 로컬 **폴더 경로** 또는 올바른 YouTube 주소인지 확인합니다. |
| **보내기**가 안 됨 | 스템 분리나 피치 작업이 끝난 뒤 다시 시도합니다. |
| 피치만 바꿀 수 없음 | 먼저 해당 곡의 **스템 분리가 완료**되어야 합니다. |

### 로그·지원 요청 시

- 활동 패널을 **Shift+클릭**하면 상세 로그를 켤 수 있습니다(다시 Shift+클릭으로 끔).
- 문의 시 **StemMixer 버전**, 증상, 표시등 색(회색/초록/주황/빨강), 가능하면 상세 로그 일부를 함께 보내 주시면 도움이 됩니다.

---

## 문의

acegikm7on@gmail.com

---

Split a track into **vocals · drums · bass · other (guitars/keys)** stems, then change pitch, mix levels, and export—all in one Windows app.

## Download (Windows)

[**StemMixer v1.0.0 Installer (exe)**](https://github.com/acegikm7on/StemMixer-Release/releases/latest/download/StemMixer_v1.0.0_Installer.exe)

> Source code is developed in a private repository. Installers and docs are published at [StemMixer-Release](https://github.com/acegikm7on/StemMixer-Release).

## Features

### AI stem separation

- Automatically splits a song into **vocals, drums, bass, and other (guitars/keys)** stems.
- When separation finishes, you can play and adjust each stem right away.
- Separation runs on **cloud GPU (RunPod)**. The first request after idle can take longer while a server is allocated and started.

### Cloud server status (bottom status bar)

The **small dot** to the left of the status text (e.g. **Ready**) is **not** a live server connection indicator—it reflects **recent cloud activity** only.

| Color | Meaning |
|-------|---------|
| **Gray** | No recent cloud server response (not an error state) |
| **Green** | A recent request succeeded (returns to gray after a timeout) |
| **Orange** | Stem separation in progress |
| **Red** | A recent separation or related request failed |

- **Start stem separation when the dot is green.** Green means the cloud server was recently ready, so separation is more likely to start quickly. If it is gray, wait a moment or click the dot to wake the server, then wait until it turns green.
- Shortly after launch, the app **once** tries to wake the cloud server in the background (no separation job). Failure is silent; the dot stays gray.
- When **gray**, click the dot to try waking the server again.
- When the dot turns gray after a timeout, the app does **not** send a health-check request (avoids waking the server just to poll status).

### Pitch shift (key change)

- Raise or lower the key by up to **±2 semitones**.
- Pitch is applied to vocals, bass, and other stems. (Drums stay at the original pitch.)
- **Vocals** use formant preservation to keep voice character when shifting pitch.
- Pitch results are saved on disk so reopening the same song loads quickly.

### Stem pitch CLI (Rubber Band)

| Stem | CLI flags (with `-p±N`) | Rationale |
|------|-------------------------|-----------|
| **Vocals** | `-2 -c5 -F --centre-focus` | Formant preservation; centre-focus stabilizes phase for centered lead vocal. |
| **Bass** | `-2 -c5 -F` | Formant preservation keeps low-end body within ±2 semitones; low artifact risk. |
| **Other** | `-2 -c5` | Mixed stem (piano, guitar, etc.): no formant lock to avoid phase smearing / comb filtering. |
| **Drums** | bypass | Original stem copied at playback; no pitch shift so transients stay intact. |

### Per-instrument level control (mixer)

- Fine-tune each stem from **0–100%** with vertical sliders.
- Preview in real time—e.g. louder vocals, quieter drums—to get the balance you want.

### Presets

- One-click combos such as **Original**, **Vocals only**, **No vocals**, **Drums only**, **No drums**, **Bass only**, **No bass**, **Other only**, and **No other**.
- **Listen in mono** toggles between stereo and mono playback.

### Local / YouTube audio

- Point the app at a **folder of audio files** on your PC, or paste a **YouTube URL** (single video or playlist) in the path field.

### Export

- Save the current key and mixer settings as **WAV** (default, 32-bit float) or **MP3** (128 kbps CBR).
- In the save dialog, pick format from the file type dropdown.

### Optional usage statistics (YouTube)

- When enabled at install or in settings, separation/export activity for YouTube tracks is cached locally and merged to B2 (weekly upload).
- After a successful upload, local JSON is **kept for 7 days** (`b2_synced_at`) for retry/debug, then removed automatically—not deleted immediately on upload.
- New events after upload clear the sync marker and queue another upload.

## Troubleshooting

Warnings during install or first run usually do **not** mean the app is broken. Unsigned public installers often trigger Windows SmartScreen.

### During installation

| Symptom | What to do |
|---------|------------|
| **Windows protected your PC** (SmartScreen) | Choose **More info** → **Run anyway**. Confirm you downloaded the official installer from the release page. |
| **User Account Control** — allow changes to your device | The installer needs administrator permission. Choose **Yes**. |
| Antivirus blocks the installer | Add the StemMixer install folder and `StemMixer.exe` to your allow/exclusion list, then retry. |
| Install hangs or fails | Close other installers, re-download the `.exe`, and run it again. |

### After launch

| Symptom | What to do |
|---------|------------|
| **Critical Dependency Missing** (FFmpeg, etc.) | The install may be incomplete. Uninstall and **reinstall** from the official installer. |
| **Cloud configuration** — app exits immediately | Likely a broken build configuration. [Contact](#contact) with the full message and installer version. |
| **Storage connection** warning (idle pre-separation paused) | Ingest storage check failed for background pre-separation. **Manual stem separation** may still work if the network and cloud server are OK. If the warning keeps appearing, contact support. |

### Cloud status dot · stem separation

| Symptom | What to do |
|---------|------------|
| Dot stays **gray** for a long time | Wait 3–5 seconds after launch. If still gray, **click** the dot to wake the server, then wait until it turns **green**. |
| **Green** but separation is slow | Long tracks, network speed, and server queue can take several minutes. Watch the bottom progress text. |
| **Orange** seems stuck | Upload, separation, or download may still be running. Avoid force-closing the app if possible. |
| **Red** | Check your internet connection and retry. Prefer starting separation when the dot is **green**. |
| Separation fails right away | Check internet, firewall, VPN, or corporate network blocking. |

### YouTube · folders · export

| Symptom | What to do |
|---------|------------|
| YouTube **sign-in** prompt | Sign in to YouTube in your browser, then **Retry** in the app. |
| Cannot read browser **login/cookies** | Review security software and browser cookie/privacy settings. |
| **Invalid path or URL** | Use a valid local **folder path** or YouTube URL. |
| **Export** does nothing | Wait until stem separation or pitch shift finishes, then try again. |
| Pitch controls unavailable | Complete **stem separation** for that track first. |

### Logs · contacting support

- **Shift+click** the activity panel to toggle a detailed log (Shift+click again to turn off).
- When reporting issues, include **StemMixer version**, what happened, dot color (gray/green/orange/red), and a short excerpt from the detailed log if possible.

## Contact

acegikm7on@gmail.com
