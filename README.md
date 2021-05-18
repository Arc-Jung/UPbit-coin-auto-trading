# UPbit-coin-auto-trading
### Today / Total
[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FArc-Jung%2FUPbit-coin-auto-trading&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)
### First commit Arc-Jung  in 2021-04-02
## Architect
![Upbit_Coin_Auto_Trading_Architect.png](/images/Upbit_Coin_Auto_Trading_Architect.png)

## Flowchart
![Upbit_Coin_Auto_Trading_Flowchart.png](/images/Upbit_Coin_Auto_Trading_Flowchart.png)

## 요구사항 분석
	1. 1분마다 가격을 조회 하여 15일 이동평균선이 60일 이동평균선을 넘어서는 골든크로스 시점에 매수를 진행합니다.
	2. 매수 후 15일 이동평균선이 하락이 시작될 때 매도를 합니다.
	3. 매수, 매매를 할때마다 기록합니다.

## 설계
	1. AWS EventBridge로 매 1분 마다 조회하여 업비트 거래소에 보유 중인 코인을 업비트 REST API를 통하여 조회하여 수익률이 10% 이상이면 매매한다.
	2. AWS EventBridge로 매 1분 마다 조회하여 이동평균선을 이용하여 15일 단기 이동평균선이 60일 장기 이동평균선을 넘어 섰을 때 매수한다.
	3. 모든 비즈니스 로직은 파이썬으로 구성하며, AWS Lambda를 통하여 서버리스로 구성하여 유지보수 및 페일오버에 대응하기 쉽게 개발한다.