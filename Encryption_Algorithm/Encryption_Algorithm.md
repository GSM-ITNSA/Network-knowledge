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