# AMMORA // GIWA Sepolia Bonding Curve Graduation DEX

`@ammora-protocol/sdk` (v0.3.9) 및 `viem`을 활용해 **GIWA Sepolia Testnet (Chain ID: `91342`)**에서 동작하는 본딩커브 발행·매수·매도·졸업(`migrate`) 미니 DEX입니다.  
별도 빌드 과정 없이 정적 파일로 바로 실행할 수 있도록 구성되어 있습니다.

---

## 포함된 파일

- `index.html`: 지갑 연결(EIP-6963), V4 커브 생성, 견적·매수·매도, 보유 수량 조회, 졸업(`migrate`) 실행 UI 및 스크립트
- `_redirects`: SPA 라우팅 및 `/api/*` 프록시 리다이렉트 규칙 (Netlify 등 정적 호스팅 호환)
- `.gitignore`: Git 저장소에 불필요한 파일(OS/에디터 설정, 환경변수, 로그 등) 추적 제외 설정
- `README.md`: 저장소 설명 및 로컬/호스팅 실행 가이드

---

## GitHub 업로드 방법

압축을 푼 폴더 내부에 `.gitignore`와 `README.md`가 함께 들어 있습니다.

```bash
git init
git add .
git commit -m "feat: add GIWA Sepolia Ammora bonding curve graduation DEX"
git branch -M main
git remote add origin https://github.com/<내_아이디>/<저장소_이름>.git
git push -u origin main
```

---

## 실행 방법

1. **로컬 웹 서버 실행**:
   ```bash
   python3 -m http.server 8080
   ```
2. **브라우저 접속 및 지갑 연결**:
   - `http://localhost:8080` 접속 후 `[LINK_WALLET]`으로 지갑을 연결합니다.
   - GIWA Sepolia(`91342`) 네트워크와 테스트넷 ETH가 필요합니다. ([GIWA Faucets](https://docs.giwa.io/get-started/faucets))
3. **커브 생성 및 거래**:
   - `[ + NEW_CURVE ]`에서 새 본딩커브를 생성하거나 좌측 목록에서 기존 커브를 선택합니다.
   - `[1. QUOTE]` → `[2. EXECUTE_BUY]` / `[ SELL ]` 순서로 거래하고, 졸업 조건 충족 시 `[ TRIGGER_GRADUATION_MIGRATE() ]`를 실행합니다.
