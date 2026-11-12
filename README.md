# 카라라 채석장 3D — 내 서버로 100명 멀티플레이 (무료)

이 폴더는 게임 페이지와 멀티플레이 서버를 함께 담고 있어요. 서버 하나가 게임 화면을 보여주고, 플레이어끼리의 접속도 처리해요.

```
server.js      멀티플레이 서버 + 게임 전체가 들어 있어요 (약 1.1MB)
package.json   서버 설정
README.md      이 안내 (올리지 않아도 돼요)
```
**GitHub에는 `server.js`와 `package.json` 두 개만 올리면 돼요.**

## 무료로 인터넷에 올리기 (GitHub + Render)

### 1. GitHub에 올리기
1. https://github.com 에서 무료 가입해요.
2. 오른쪽 위 **+ → New repository**를 눌러요.
   - 이름: 예) `carrara3d`
   - **Public** 선택
   - **Create repository** 클릭
3. 만든 저장소 화면에서 **uploading an existing file**을 눌러요.
4. `server.js`와 `package.json` 두 파일을 끌어다 놓아요(이미 올렸다면 새 `server.js`로 덮어써요).
5. **Commit changes**를 눌러요.
6. 저장소 첫 화면에 두 파일이 보이면 끝이에요.

### 2. Render에서 서버 켜기
1. https://render.com 에서 **GitHub 계정으로** 무료 가입해요.
2. **New + → Web Service**를 누르고 방금 만든 저장소를 고르세요.
3. 설정:
   - Runtime: **Node**
   - Build Command: `npm install`
   - Start Command: `npm start`
   - Instance Type: **Free**
4. **Create Web Service**를 눌러요. 2~3분 뒤 `https://carrara3d-xxxx.onrender.com` 같은 주소가 생겨요.
5. 그 주소를 열면 게임이 시작돼요. 친구들에게 이 주소만 보내면 돼요.

## 접속 확인
- 게임 안 접속자 목록에 초록 점과 **Online · 공개 채석장**이 보이면 성공이에요.
- `주소/health`를 열면 지금 접속 인원이 보여요. 예) `ok 12`
- 🚪 **친구 방**: 같은 코드로 들어온 사람끼리만 만나요. 🔗 **초대 링크**는 이 서버 주소로 만들어져요.
- claude.ai 계정 없이 누구나 접속할 수 있어요. 각 기기에 자동으로 플레이어 ID가 만들어져요.

## 알아둘 점 (무료 요금제)
- 15분 동안 아무도 없으면 서버가 잠들어요. 다음 첫 접속은 30~60초 걸릴 수 있어요. 접속하면 다시 깨어나요.
- 무료 서버가 다시 시작되면 **랭킹 기록(data.json)이 초기화**될 수 있어요. 게임 진행은 각자 브라우저에 저장돼서 그대로예요.
- 무료 요금제에는 월 사용 시간과 데이터 전송량 한도가 있어요. 정확한 숫자는 Render 요금 안내에서 확인하세요.
- 100명이 계속 접속한다면 유료 요금제(월 몇 달러)가 더 안정적이에요.
- 최대 인원은 기본 150명이에요. Render의 **Environment**에서 `MAX_PLAYERS` 값으로 바꿀 수 있어요.
- 가까이 있는 40명까지만 보여서 100명이 접속해도 휴대폰에서 버벅이지 않아요. 500m 안의 사람은 초당 8번, 그보다 먼 사람은 초당 1번 갱신돼요.
- 외계인과의 AI 대화는 claude.ai 기능이라 여기서는 정해진 대사만 나와요.

## 게임을 업데이트할 때
새 버전의 `server.js`를 GitHub 저장소에 다시 올리면(덮어쓰기) Render가 자동으로 다시 배포해요.

## 내 컴퓨터에서 먼저 시험해 보기 (선택)
1. Node.js 18 이상을 설치해요.
2. 이 폴더에서 `npm install`을 실행하고, 이어서 `npm start`를 실행해요.
3. 브라우저로 http://localhost:3000 을 열어요.
