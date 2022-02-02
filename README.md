# MPU9250_data_in_a_stationary_state_csv

## 개요

- MPU9250 센서가 정지되어 있을 경우 측정되는 오차 범위를 산출하기 위해 10ms마다 9축 데이터를 측정한다.
- 측정된 14,500,000개의 9축 데이터는 100,000줄씩 파일로 저장한다.
- 각 파일에서 최대 충격량과 최소 충격량을 산출한다.
- 정지된 상태에서 측정되는 MPU9250 센서 값을 분석한다.

### 충격량 산출식

```python
math.sqrt((data.acc_x * data.acc_x) + (data.acc_y * data.acc_y) + (data.acc_z * data.acc_z))
```

- 이상적인 상황에서 3축 가속도 데이터는 x축으로 0, y축으로 0, 그리고 z축으로 중력가속도(9.80665)를 받아 충격량은 9.80665를 갖는다.
- 또한, 측정되는 3축 가속도 데이터의 충격량이 9.80665에 가까울수록 정확도가 높은 센서이다.

## 분석 자료

- https://kihyeon-hong.github.io/MPU9250_data_in_a_stationary_state_txt/9-axis_data_analysis.html

## 분석 결과

- 145개의 9축 데이터 파일에서 MPU9250의 충격량은 최대 10.5m/s, 최소 9.23m/s를 보임을 확인하였다.
