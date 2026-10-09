# 알림가계부 개인정보처리방침

시행일: 2026년 10월 9일

알림가계부(이하 "앱")는 개인 개발자가 만들고 운영하는 가계부 앱입니다. 이 문서는 앱이 어떤 정보를 다루고, 어떻게 보호하는지 설명합니다.

핵심을 먼저 말씀드리면 **앱에는 서버가 없고, 회원가입이 없으며, 사용자의 결제·거래 정보는 사용자 기기 밖으로 나가지 않습니다.**

---

## 1. 수집·이용하는 정보

### 1-1. 알림 내용 (알림 접근 권한)

앱은 사용자가 Android 설정에서 **알림 접근 권한**을 직접 허용한 경우에만 다른 앱의 알림을 읽습니다.

- **읽는 대상**: 카드사·은행·간편결제 앱과 문자 앱이 보내는 결제·입출금 알림에 한정합니다. 앱 안에 미리 정해둔 금융 앱 목록(패키지명)에 해당하는 알림만 처리하고, 그 외 앱의 알림은 즉시 버리며 저장하지 않습니다.
- **처리 방식**: 알림 본문에서 금액·가맹점명·결제 수단·일시를 추출해 기기 안의 데이터베이스에 거래 기록으로 저장합니다. 알림 원문은 사용자가 "왜 이렇게 기록됐는지" 확인하고 오류를 바로잡을 수 있도록 해당 거래 기록과 함께 기기에만 보관됩니다.
- **전송 여부**: 알림 내용과 거래 기록은 **어떤 서버에도 전송되지 않습니다.** 개발자를 포함해 누구도 원격으로 접근할 수 없습니다.
- **권한 철회**: Android 설정 > 알림 접근에서 언제든 끌 수 있습니다. 끄면 자동 기록이 즉시 중단됩니다.

### 1-2. 사용자가 직접 입력한 정보

수동으로 입력한 거래, 카테고리, 월 예산, 저축 목표 등은 기기 안에만 저장됩니다.

### 1-3. 광고 식별자 (Google AdMob)

무료 사용자에게는 홈 화면 하단에 배너 광고 1개가 표시됩니다. 광고는 Google AdMob이 제공하며, 광고 표시를 위해 Google이 **광고 ID(Advertising ID), 기기 정보, 대략적인 위치(IP 기반)** 등을 수집할 수 있습니다. 이 정보는 앱 개발자가 아니라 Google이 자체 개인정보처리방침에 따라 처리합니다.

- Google 개인정보처리방침: https://policies.google.com/privacy
- 광고 맞춤설정 해제: Android 설정 > Google > 광고 > 광고 맞춤설정 선택 해제
- 프리미엄을 구매하면 광고가 표시되지 않으며 AdMob SDK가 광고를 요청하지 않습니다.

앱의 거래 기록·알림 내용은 AdMob을 포함한 어떤 광고 사업자에게도 제공되지 않습니다.

### 1-4. 인앱 결제 (Google Play 결제)

프리미엄 구매와 개발자 응원(팁)은 Google Play 결제 시스템을 통해 처리됩니다. 결제 수단, 카드 정보 등은 Google이 처리하며 앱은 이를 받지 않습니다. 앱은 구매 완료 여부(프리미엄 보유 여부)만 기기에 저장합니다.

### 1-5. 외부 데이터 조회 (한국은행 ECOS)

물가상승률·환율·예금금리·주가지수를 표시하기 위해 앱은 한국은행 경제통계시스템(ECOS) 공개 API에서 통계 수치를 내려받습니다. 이 요청에는 **사용자 정보가 포함되지 않습니다.** 단순히 공개 통계를 읽어오는 것이며, 일반적인 인터넷 통신 과정에서 IP 주소가 해당 서버에 전달될 수 있습니다.

### 1-6. 수집하지 않는 정보

앱은 다음을 수집하지 않습니다: 이름, 이메일, 전화번호, 계좌번호, 카드번호, 로그인 정보, 연락처, 정확한 위치, 사진. 앱에는 분석(애널리틱스) SDK나 오류 수집 SDK가 들어 있지 않습니다.

---

## 2. 정보의 보관과 삭제

- 모든 거래 기록은 사용자 기기의 앱 전용 저장공간(다른 앱이 접근할 수 없는 영역)에 저장됩니다.
- **앱을 삭제하면 모든 데이터가 함께 삭제됩니다.** 서버에 사본이 없으므로 복구할 수 없습니다.
- 앱 안에서 개별 거래를 삭제하거나, 설정에서 전체 기록을 삭제할 수 있습니다.
- 알림 원문 로그는 최근 60건만 보관되며 오래된 것부터 자동으로 지워집니다.

## 3. 정보의 제3자 제공

앱 개발자는 사용자 정보를 누구에게도 판매·제공하지 않습니다. 위 1-3(AdMob), 1-4(Google Play 결제)에서 설명한 Google의 처리만이 유일한 제3자 관여입니다.

## 4. CSV 내보내기

프리미엄 사용자는 거래 기록을 CSV 파일로 내보낼 수 있습니다. 이 기능은 사용자가 직접 실행할 때만 동작하며, 생성된 파일을 어디로 보낼지는 사용자가 Android 공유 메뉴에서 선택합니다. 앱이 임의로 파일을 전송하지 않습니다.

## 5. 아동의 개인정보

앱은 만 14세 미만 아동을 대상으로 하지 않으며, 아동의 개인정보를 의도적으로 수집하지 않습니다.

## 6. 보안

데이터가 기기 밖으로 나가지 않는 것이 가장 큰 보안 조치입니다. 외부 통신(광고, 결제, 한국은행 통계)은 모두 HTTPS로 암호화됩니다.

## 7. 사용자의 권리

사용자는 언제든지 앱 안에서 자신의 기록을 열람·수정·삭제할 수 있고, 알림 접근 권한을 철회할 수 있으며, 앱을 삭제해 모든 데이터를 없앨 수 있습니다. 서버에 보관된 정보가 없으므로 별도의 열람·삭제 요청 절차는 필요하지 않습니다.

## 8. 방침의 변경

이 방침이 바뀌면 이 페이지에 시행일과 함께 갱신합니다. 수집 항목이 늘어나는 등 중요한 변경이 있으면 앱 안에서도 알립니다.

## 9. 문의

개인정보 관련 문의는 아래로 보내주세요.

- 이메일: limlimlimlim2026@gmail.com

---

# Alrim Ledger Privacy Policy (English summary)

Effective: October 9, 2026

Alrim Ledger is a personal expense tracker developed by an individual developer. **It has no server, no account system, and your transaction data never leaves your device.**

- **Notification access**: Only if you grant it in Android settings, the app reads payment notifications from a fixed list of Korean card, bank and payment apps, extracts amount/merchant/date, and stores the record locally. Notifications from any other app are discarded immediately. Nothing is uploaded anywhere.
- **Ads (Google AdMob)**: Free users see one banner. Google may collect the Advertising ID and device information under Google's own privacy policy (https://policies.google.com/privacy). Your transaction data is never shared with AdMob. Premium removes ads entirely.
- **In-app purchases**: Handled by Google Play Billing. The app never sees payment details.
- **Bank of Korea statistics**: The app downloads public inflation/FX/rate figures from the ECOS open API. No user data is sent.
- **Not collected**: name, email, phone, account or card numbers, contacts, precise location, analytics.
- **Deletion**: Uninstalling the app deletes all data. There is no server copy.
- **Contact**: limlimlimlim2026@gmail.com
