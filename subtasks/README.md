### 1. data_ps
```
python subtasks/data_ps/exec.py
```
* 데이터셋 read & processing example
* .h5는 처음이라 핸들링 예시 필요
### 2. data_save
```
python subtasks/data_save/exec.py
```
* .h5는 데이터 로더 상에서 배치 단위로 한꺼번에 가져오려니 오랜 시간이 소요됨
* 이에 따라 .h5 파일 내 모든 이미지와 label들을 한 번에 가져오는 것이 필요함.
* 그래서, NumPy로 샘플 하나씩 저장하여 데이터셋을 재구성하는 방식을 택했고, 위 command를 실행시키면 된다.
* 또한, 순서는 해당 script에서 랜덤으로 작성하였기 때문에 데이터셋 코드에서 이를 고려할 필요는 없다.
### 3. intervention
```
python subtasks/intervention/exec.py
```
* GT, Reconstruction, intervention을 모두 이미지로 저장할 수 있는 코드
### 4. smooth_result
```
python subtasks/intervention/exec.py
```
* VAE의 Reconstruction term을 Binary Cross Entropy를 사용한 것으로 결과가 굉장히 sharp하며, 픽셀 값들이 상당히 극단적이다.
* 그래서, Blur 처리를 하여 결과를 다듬는 처리를 수행했다.