# NyanKatX3 Tab 개인정보처리방침 / Privacy Policy

적용 대상: NyanKatX3 Tab(냥캣탭) Chrome 확장 프로그램 1.6.0
최종 수정 및 시행일: 2026년 11월 2일

## 개인정보처리방침

### 1. 기본 원칙
냥캣탭은 새 탭 이동, 링크 미리보기, 선택한 텍스트 번역, 자막 추출·표시·번역, 일본어 음성인식, Base64·QR 해석과 자동 스크롤 기능을 제공합니다. 개발자는 확장 프로그램을 통해 음성, 인식 결과, 번역 내용, 자막 파일 또는 방문 기록을 수집하는 서버를 운영하지 않습니다. 광고·분석·추적 SDK를 사용하지 않으며 사용자 데이터를 판매하거나 광고 목적으로 제공하지 않습니다.

기능에 필요한 페이지 내용은 브라우저에서 처리합니다. 모델·글꼴 다운로드, 사이트 미리보기 및 파일 다운로드에는 아래와 같은 외부 통신이 발생합니다.

### 2. 처리하는 데이터와 목적
- **음성인식:** 사용자가 시작한 탭의 재생 오디오를 캡처합니다. 해당 탭 전체의 소리가 포함될 수 있으며 마이크나 다른 탭의 소리를 직접 수집하지 않습니다. 일본어 음성은 기기 내 Parakeet CTC 모델로 인식합니다. 오디오와 인식 결과를 개발자 또는 Hugging Face의 음성 처리 서버에 업로드하지 않습니다. 팝업을 닫아도 캡처가 유지되며 중지·대상 탭 닫기·페이지 이동 시 종료됩니다.
- **번역과 자막:** 선택한 텍스트, 사용자가 불러온 자막, 감지된 자막 및 음성인식 결과를 표시·번역에 사용합니다. 번역은 브라우저의 온디바이스 Language Detector/Translator API로 수행합니다. 확장 프로그램은 번역 내용을 자체 서버나 별도 클라우드 번역 API로 전송하지 않습니다.
- **자막 탐지·다운로드:** 현재 페이지·프레임과 자막·미디어 요청 URL 및 관련 응답에서 자막 후보를 찾습니다. 사용자가 다운로드 또는 번역을 요청하면 원본 사이트나 CDN에서 자막을 가져옵니다. 사이트 접근에 필요한 브라우저 쿠키 등 인증 정보가 원본 요청에 포함될 수 있습니다. 쿠키를 개발자에게 전송하는 기능은 없습니다.
- **페이지 보조 기능:** 링크 URL, 선택한 Base64 텍스트, QR 해석을 요청한 이미지, 스크롤 위치, 영상 상태 및 kio.ac 다운로드 상태를 해당 기능에 필요한 범위에서 처리합니다. QR·Base64 해석은 기기 내에서 수행하며 웹 이미지는 원본 주소에서 가져올 수 있습니다.
- **설정:** 자막 스타일·프리셋·후처리 사전, 자동 스크롤 제외 사이트, 링크 미리보기·번역 옵션 등을 저장합니다. PC 글꼴 목록은 글꼴 선택에 사용하며 개발자에게 전송하지 않습니다.

### 3. 모델 다운로드와 외부 서비스
- ‘음성 모델 준비’를 누르면 Hugging Face(`huggingface.co`) 및 파일 제공 CDN에서 음성인식 모델·전처리 모델·토큰 파일을 내려받습니다. 최초 다운로드는 약 656 MB이며 확장 프로그램의 Cache Storage에 보관하여 재사용합니다. 제공자는 IP 주소, 요청 파일 경로, 접속 시간 및 일반적인 HTTP/브라우저 정보를 받을 수 있습니다. 오디오나 인식 문장을 다운로드 요청에 첨부하지 않습니다.
- 브라우저 내장 번역·언어 감지 모델은 필요할 때 브라우저 제공자의 서비스에서 내려받습니다. 다운로드와 보관은 브라우저가 관리하며 해당 제공자의 정책이 적용됩니다.
- 일부 선택형 글꼴은 jsDelivr/Project Noonnu 또는 토스 서버에서 가져오며 해당 제공자가 일반적인 접속 정보를 받을 수 있습니다.
- 새 탭 이동 기능은 `fav.ju.mp`에 접속하며 실패 시 `12tw.pages.dev`, `tchinso.github.io/fav/`를 사용할 수 있습니다. 사용자는 설정에서 새 탭 자동 이동을 끌 수 있습니다.
- 링크 미리보기, 해석한 URL 열기, 온라인 자막 검색(`sub.h2h.workers.dev`), 자막·이미지 다운로드는 목적지 사이트에 실제 네트워크 요청을 보냅니다. 사이트는 IP 주소 및 브라우저 정책에 따른 쿠키·리퍼러 등 일반적인 접속 정보를 받을 수 있고 자체 개인정보처리방침을 적용합니다. 확장 프로그램은 별도의 광고·추적 코드를 추가하지 않습니다.

### 4. 저장과 삭제
오디오 버퍼와 인식·번역 결과는 처리 중 메모리에 일시 보관합니다. 확장 프로그램은 음성 녹음 파일이나 영구적인 대화 기록을 생성하지 않습니다. 중지하면 캡처와 음성 모델 Worker를 해제합니다.

자막 스타일·후처리 사전 등은 확장 프로그램의 로컬 저장소에 저장됩니다. 일부 일반 설정과 사이트 제외 목록은 `chrome.storage.sync`에 저장되어 브라우저 동기화 설정에 따라 브라우저 제공자를 통해 동기화될 수 있습니다. 개발자가 관리하는 동기화 서버는 없습니다. 자막 탐지·다운로드 상태 일부는 세션 저장소에 보관되며 탭 상태 변경이나 브라우저 세션 종료에 따라 정리됩니다.

내려받은 음성 모델은 **자막 → 음성인식 → 모델 캐시 삭제**로 삭제할 수 있습니다. 브라우저 내장 번역 모델은 이 버튼의 삭제 대상이 아닙니다. 로컬 설정은 해당 화면에서 수정하거나 확장 프로그램을 제거하여 삭제할 수 있습니다. 동기화 데이터는 브라우저의 동기화 설정도 확인해야 합니다. 다운로드한 자막과 내보낸 설정 JSON은 사용자가 선택한 위치에 남으며 직접 삭제해야 합니다.

### 5. 권한과 데이터 사용 제한
웹사이트 접근, `webRequest`, `webNavigation`은 페이지 기능·자막 탐지·탭 상태 처리에 사용합니다. `tabCapture`와 `offscreen`은 사용자가 시작한 오디오 처리, `storage`는 설정·상태 저장, `downloads`는 요청한 파일 저장, `fontSettings`는 글꼴 선택, `contextMenus`는 우클릭 기능에 사용합니다. `declarativeNetRequest`는 링크 미리보기가 활성화된 탭의 프레임 표시를 위한 응답 헤더 처리에 사용합니다.

데이터는 명시된 사용자 대면 기능을 제공하는 데 필요한 범위에서만 사용합니다. Google API로부터 받은 정보의 사용은 Limited Use 요구사항을 포함한 Chrome 웹스토어 사용자 데이터 정책을 준수합니다. 문의 시 자발적으로 제공한 정보는 문의 대응에 사용합니다.

### 6. 문의와 변경
문의: `team@soleil.channel.io`
기능이나 데이터 처리 방식이 변경되면 이 문서와 시행일을 갱신합니다.

---

## Privacy Policy
Applies to NyanKatX3 Tab (NyanKatTab), Chrome extension version 1.6.0.
Last updated and effective: November 2, 2026.

### 1. Principles
The extension provides new-tab navigation, link previews, text translation, subtitle discovery/display/translation, Japanese speech recognition, Base64/QR decoding, and scrolling tools. The developer does not operate a server collecting extension users’ audio, transcripts, translations, subtitle files, or browsing history. No advertising, analytics, or tracking SDKs are included. User data is not sold or shared for advertising. Content processing is local, but model/font downloads, previews, and file downloads involve external requests.

### 2. Data processed
Starting speech recognition captures playback audio from the selected tab, potentially including all sound in that tab. It does not directly capture the microphone or other tabs. Japanese speech is transcribed locally using Parakeet CTC. Audio and transcripts are not uploaded to the developer or Hugging Face for processing. Capture continues after the popup closes and stops on explicit stop, target-tab closure, or navigation.

Selected text, loaded/discovered subtitles, and transcripts are processed for display and translation. The browser’s on-device Language Detector/Translator APIs are used; the extension does not send translation input to its own server or a separate cloud translation API.

Subtitle discovery examines the page, frames, subtitle/media request URLs, and relevant responses. Requested subtitles are fetched from their original site or CDN. Original-site requests may include browser credentials such as cookies for access; cookies are not sent to the developer.

Link URLs, selected Base64 text, images selected for QR decoding, scrolling positions, video state, and kio.ac download status are processed as needed. QR and Base64 decoding is local; web images may be fetched from their original URLs. Styles, presets, dictionaries, scrolling exclusions, preview and translation preferences are saved. Installed font names are used for selection and are not sent to the developer.

### 3. External services
Preparing speech recognition downloads approximately 656 MB of model, frontend, and token files from Hugging Face (`huggingface.co`) and its delivery CDNs into extension Cache Storage. Providers may receive IP addresses, requested file paths, request times, and ordinary HTTP/browser information. Audio and transcripts are not attached to these download requests.

The browser may download built-in translation/language detection models from its provider, which manages those downloads and storage under its own policies. Some optional fonts come from jsDelivr/Project Noonnu or Toss; those providers may also receive ordinary connection information.

New-tab navigation opens `fav.ju.mp`, with `12tw.pages.dev` and `tchinso.github.io/fav/` as fallbacks, and can be disabled. Link previews, decoded URL navigation, online subtitle search (`sub.h2h.workers.dev`), and subtitle/image downloads request resources from the relevant sites. Those sites may receive IP addresses and, depending on browser policies, cookies, referrers, and other ordinary request information. Their privacy policies apply. The extension adds no separate advertising or tracking code.

### 4. Storage and deletion
Audio buffers, transcripts, and translations are temporarily held in memory. The extension does not create audio recordings or permanent conversation logs. Stopping releases capture and the speech model Worker.

Styles and dictionaries are stored locally. Some general settings and exclusion lists use `chrome.storage.sync` and may synchronize through the browser provider according to browser settings. The developer operates no synchronization server. Some discovery/download state uses session storage and is cleared according to tab lifecycle or browser session termination.

Use **자막 → 음성인식 → 모델 캐시 삭제** to remove downloaded speech models. This does not delete browser-managed translation models. Edit local settings in the extension or uninstall it to remove them; synchronized settings are also subject to browser sync controls. Saved subtitles and exported settings JSON remain at the user-selected location until deleted by the user.

### 5. Permissions and limited use
Website access, `webRequest`, and `webNavigation` support page tools, subtitle discovery, and tab lifecycle handling. `tabCapture` and `offscreen` support user-started audio processing. `storage`, `downloads`, `fontSettings`, and `contextMenus` support settings/state, requested downloads, font selection, and context-menu tools. `declarativeNetRequest` adjusts frame response headers in tabs with active link previews.

Data is used only as necessary for the described user-facing features. Use of information received from Google APIs adheres to the Chrome Web Store User Data Policy, including the Limited Use requirements. Information voluntarily provided in support inquiries is used to respond to those inquiries.

### 6. Contact and changes
Contact: `team@soleil.channel.io`
This policy and its effective date will be updated when features or data practices change.
