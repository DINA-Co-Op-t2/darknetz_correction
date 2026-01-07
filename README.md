목적 : DarkneTZ 코드를 이용하여 TEE 영역 모델 학습 및 추론을 구현한다.

주의 사항 :
1. 추론시 -pp_end 에 해당하는 layer는 cost layer가 될 수 없다. 추론 시 cost layer는 사용하지 않으며, 그러므로 TEE에서 구현한다면 단순히 값을 넘겨주는 작업만 TEE에서 해야하는데 굳이 그럴 필요가 없다.
     -> 그래서 명령어 입력시 pp_end가 cost layer이지 않도록 주의해야한다.
