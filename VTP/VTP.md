## VTP란 ❓

- Cisco 전용 프로토콜로써 연결된 스위치끼리 VLAN 정보를 자동으로 주고 받아 동기화하는 프로토콜이다.

## VTP의 특징 👊

- VLAN의 설정 정보는 받아오지만 스위치 Port 정보는 받아오지 않는다.
    - 여기서 말하는 스위치 Port 정보는 속도, 전이중/반이중 모드, VLAN 구성, MAC 주소이다.
- 스위치의 기본 VTP Mode는 Server이고 Domain은 정해져 있지 않다.
- 확장 VLAN (1006~4094)는 TransParent Mode에서만 사용할 수 있다.
- VTP 설정은 (패스워드 → 도메인 설정 → 모드설정)순으로 해야 안전하다.

## VTP 설정 조건

- 스위치에서 VTP는 기본적으로 동작하는 프로토콜이며, 끌 수 없는 프로콜이다.
- VTP를 사용하려면 VTP Domain과 Password가 일치해야한다.
- VTP 동기화 메시지를 주고받으려면 연결되어있는 포트가 Trunk 포트여야지 가능하다.

## VTP Message

1. Summary Advertisement
- VTP Server가 자신과 연결된 스위치에게 5분 주기로 보내는 메시지이다.
- 관리하는 VTP domain에 Revision Number를 전송한다. 다른 스위치들은 Rivision Number를 받아서 자신의 VLAN 정보가 최신인지 아닌지 판단하고 최신이 아니라면 동기화한다.
1. Subset Advertisement 
- VLAN 정보를 담고있는 메시지
1. Advertisement Request 
- VTP client가 VTP Server에게 메시지를 요청하거나 자신이 가지고 있는 Revision Number보다 높은 Number를 가지고 있거나 VTP domain 변경 등 여러가지 VLAN에 변화가 생겼을 경우 Client가 Server에게 보내는 메시지

## VTP Mode

1. Server Mode
- VLAN 정보를 직접 생성, 관리 할 수 있는 Mode이다. (vlan 0 ~ 1005번)
1. Client Mode
- 같은 domain에 password가 설정된 VTP server로부터 VLAN 정보를 받아 저장한다.
- 직접 VLAN 정보를 설정할 수 없다.
1. Transparent Mode
- 자신만의 VLAN 정보를 설정할 수 있다.
- 다른 스위치에게 자신의 VLAN 정보를 전송하지 않으며, VTP server로부터 받은 정보로 동기화하지 않지만 받은 정보는 다른 스위치에게 전송한다.
- Revision Number는 항상 0이다.

## VTP Pruning (가지치기)

![Untitled](data:image/png;base64,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)

- SW는 vlan 10 access 포트를 가지고 있고 SW2, SW3는 vlan 20 access 포트를 가지고 있다.
- 이떄 SW에서는 오른쪽으로 플러딩 될 필요가 없고 SW2,SW3는 왼쪽으로 플러딩 될 필요가 없다.
- Trunk 포트로 불필요한 전송을 막으므로 효율적인 관리를 할 수 있는 설정이다.

```markdown
SW1(config)#vtp pruning 
Pruning switched on
```

- 이렇게 설정하게 되면 VTP로 연결되어있는 스위치들도 Pruning이 활성화된다.