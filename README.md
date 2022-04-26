# UPbit-coin-auto-trading
### Today / Total
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FArc-Jung%2FUPbit-coin-auto-trading&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)
### First commit Arc-Jung  in 2021-04-02

#### 해당 어플리케이션은 아직 미완성이므로 참조용으로만 사용하시길 바랍니다. 모든 투자는 본인의 선택이며 투자 손실에 대한 책임은 본인에게 있습니다.

#### 해당 레포지토리의 목적은 여러 알고리즘을 직접 생성하고 테스트 하는 일종의 시물레이터로 사용하는 것을 권장하고 있습니다. 이 레포지토리를 기반으로 자신의 생각과 상상을 기반으로 다양한 알고리즘을 생성하여 테스트하였으면 좋겠습니다. 

## 요구사항 분석
	1. 1분마다 가격을 조회 하여 단기 이동평균선이 장기 이동평균선을 넘어서는 골든크로스 시점에 매수를 진행합니다.
	2. 매수 후 단기 이동평균선이 하락이 시작될 때 매도를 합니다.
	3. 매수, 매매를 할때마다 기록합니다.

## 설계
	1. AWS EventBridge로 매 1분 마다 조회하여 업비트 거래소에 보유 중인 코인을 업비트 REST API를 통하여 조회하여 수익률이 일정 비율 이상일시 매매한다.
	2. AWS EventBridge로 매 1분 마다 조회하여 이동평균선을 이용하여 15일 단기 이동평균선이 장기 이동평균선을 넘어 섰을 때 매수한다.
	3. 모든 비즈니스 로직은 파이썬으로 구성하며, AWS Lambda를 통하여 서버리스로 구성하여 가용성 및 확장성에 유의하여 개발한다.
## Architect
![Upbit_Coin_Auto_Trading_Architect.png](/images/Upbit_Coin_Auto_Trading_Architect.png)

## Flowchart
![Upbit_Coin_Auto_Trading_Flowchart.png](/images/Upbit_Coin_Auto_Trading_Flowchart.png)
