# 암호화 ?

# 1. 암호화란 무엇인가요 ❓

- 평문(Plain Text)을 암호문(Crypto Text)으로 변환하는 과정.
    - 평문 → 암호문
- 사용자가 입력한 데이터를 알아볼 수 없는 데이터로 변환하는 과정이다.
    - blue0494 → RHSJEN18275JS83NSUEB
- 암호문의 형태로 정보를 CPU에 저장시켜 정보를 “보호” 할 수 있다.

# 2. 복호화란 무엇인가요 ❓

- 암호문(Crypto Text)를 평문(Plain Text)로 변환하는 과정.
    - 암호문 → 평문
- 암호화된 데이터를 정상적인(사람이 알아볼 수 있는) 데이터로 변환하는 과정.
    - RHSJEN18275JS83NSUEB → blue0494

---

# 3. 암호화 과정의 분류와 암호화 알고리즘

## 단방향 암호화 vs 양방향 암호

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcZmAyQ%2FbtrbljCRVjK%2FHI65qKdGtZTfijKlW9zYok%2Fimg.jpg)

## 3-1.  단방향 암호화가 무엇인가요 ❓

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F5DeQc%2FbtrbqvPO9pB%2FjL2UeCtysP514J93xemm01%2Fimg.png)

- 평문(Plain Text) → 암호화 엔진 → 암호문(Encrypt Text)
- 암호화를 거친 데이터를 다시 원래 상태인 평문으로 되돌리지 못하는 암호화 방식.
- 복호화가 불가능한 데이터 암호화 방식이다.
- 1bit만 바뀌어도 Hash값이 바뀌기 때문에 데이터의 무결성을 검증하기 위한 암호화 방식이다.
- 대표적인 알고리즘 : 해시(Hash)알고리즘

## 3-2. Hash 함수 / 알고리즘

- 임의의 크기를 가진 데이터를 고정된 데이터의 크기로 변환시키는 함수이다.
- 입력값이 길이가 달라도 출력 값은 언제나 고정된 길이로 반환한다.
- 동일한 값이 입력되면 항상 동일한 출력 값을 보장한다.
- Hash 함수에 의해 얻어지는 값은 Hash 값, Hash 코드, Hash CheckSum 등이 있다.
- 대표적인 해시 알고리즘 : SHA 시리즈 / MD5

### 3-2.1 MD5 알고리즘

- Message-Digest Algorithm
- 임의의 메시지를 입력받으면 128bit(32개의 숫자 하나당 4Bit임)짜리 고정 길이의 값을 출력한다.
- 입력 메시지의 제한이 없다.
- 주로 원본 그대로인지 확인하는 무결성 검사 등에 사용된다.
- 하지만 MD5알고리즘은 보안 관련 용도로 활용하지 않는다.

### 3-2.2. SHA 알고리즘

- Secure Hash Algorithm
- MD5의 취약성을 개선하기 위해 만들어진 알고리즘이다.
- 해시 값의 크기는 SHA 알고리즘에 따라오는 Bit 수만큼 달라지게 된다.
- 해시 함수의 버전은 0~3까지 있으며 현재는 SHA2,3이 권장되고 있고 0,1은 사용하지 않게한다

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc3V1Uw%2FbtrbuIU6fja%2FEera8Xp0CHgQaiVMeua5M1%2Fimg.png)

---

## 4. 양방향 암호화

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FT4IZA%2Fbtrbvwz8REw%2FTWRrTyC1wBDf6DypaE9f4k%2Fimg.png)

## 4-1 .양방향 암호화란 ?

- 암호문을 복호화 할 수 있도록 구현된 암호 알고리즘이다.
- 데이터를 인가된 사용자만 볼 수 있도록 하기 위한 장치이다.
- 양방향 암호 알고리즘은 주로 3DES, AES와 RSA가 잘 알려져 있다.
- 알고리즘은 키의 성질에 따라 구분이된다.
    - 대칭키 암호 알고리즘 vs 비대칭키 암호 알고리즘.

## 4-2. 대칭키 암호 알고리즘

- 하나의 키로 암호화와 복호화를 둘 다 수행하는 것을 뜻함.
- 암호를 할 때 사용하는 암호키와 복호화를 할 때 사용하는 키가 같으므로 이 키는 절대로 외부에 유출되지 않도록 관리해야하며 이 키를 비밀키(Secret Key)라고 부른다.
- 암호화와 복호화에 쓰이는 키 크기가 상대적으로 작다.
- 암호 알고리즘 내부 구조가 단순하여 시스템 개발 환경에 용이하다.
- 비대칭키에 비해 암호화와 복호화 속도가 빠릅니다.
- 하지만 교환 당사자간에 동일한 키를 공유해야하기 때문에 키 관리의 어려움이 있다.
- 또한 잦은 키 변경이 있는 경우에 불편함을 초래한다.

### 4-2.1 DES 알고리즘

- Data Encryption Standard.
- 평문을 64비트로 나눠 56비트의 키를 이용해 다시 64비트의 암호문을 만들어 내는 알고리즘

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FddmrN1%2FbtrbtoJCiDF%2FeuecUhWqO80gmE12WMqLZ1%2Fimg.png)

### 4-2.2 3DES 알고리즘

- DES 알고리즘을 **3중**으로 만들어 DES 암호를 보완한 암호 알고리즘입니다.
- 암호화-암호화-암호화 방법이 아닌, 암호화-복호화-암호화 방법으로 암호화를 합니다.

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbKuhMO%2Fbtrbor8jqnY%2FXLRYuP8fhCaGpSSOmrSfY0%2Fimg.png)

### 4-2.3 AES 알고리즘

- DES에 대해 공격방법이 알려지면서 더욱 보완된 AES 알고리즘이다.
- 128 비트 암호화 블록, 다양한 키의 길이(128,192,256)를 갖춘 대칭형 알고리즘.
- AES는 대입 치환 **SPN**(**S**ubstitution-**P**ermutation **N**etwork)을 사용하여 암호화하는 방법이고 전체 bit를 암호화 하는 방식을 사용한다.공

![Untitled](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fx60Ea%2FbtrbkXl5YAq%2FjVNVJBMmIfOC1BQde9x05k%2Fimg.png)

## 5. 비대칭키 암호화 알고리즘

- **공개키** 암호화 알고리즘
- 비대칭키는 암호화할 때의 키와 복호화할 떄의 키가 다른것을 의미한다.
- **공개키(Public Key)와 개인키(Private Key)**
- 한 쌍의 키가 존재하며, 하나는 특정 사람만이 가지는 개인키(또는 비밀키)이고 다른 하나는 누구나 가질 수 있는 공개키이다.
- 공개키와 개인키는 기능히 완전 같다.
- 공개키로 암호화 하는 방식 vs 개인키로 암호화 하는 방식
    - 공개키 암호화는 데이터 보안에 중점을 둔것.
    - 개인키 암호화는 인증 과정에 중점을 둔것.

![Untitled](https://blog.kakaocdn.net/dn/bi9uLq/btrbllnjBl8/QzYfVM7KmH6EYVOVSiQs0k/img.png
)

### 5-1. RSA 알고리즘

- RSA는 창시자들의 이름 앞글자를 따서 지었다 (Ron **R**ivest, Adi **S**hamir, Leonard **A**dleman)
- 최초로 암호화 + 전자서명이 가능한 알고리즘.
- RSA는 큰 정수의 **소인수 분해의 난해함**에 기반하여, 공개키만을 가지고는 개인키를 쉽게 짐작할 수 없도록 디자인되어 있다.