## **인공지능 전체 구조 및 학습 과정**

### **Model**
- LeNey, AlexNet, VGG나 ResNet 등 다양하게 설계된 모델
- Convolution Layer, Pooling 등 다양한 Layer 충돌로 구성
- 이 모델 안에 학습 파라미터가 있고, 이 모델이 학습하는 대상

### **Prediction/ Logit**
# [0.15, 0.3, 0.2, 0.25, 0.1]
- 각 Class 별로 예측한 값.
- 여기서 가장 높은 값이 모델이 예상하는 class 또는 정답
# [0.0, 0.0, 0.0, 1.0, 0.0]
- 위의 숫자가 정답이라고 할 때 얼마나 틀렸는지 얼마나 맞았는지 확인 가능

### **Loss / Cost**
- 예측한 값과 정답과 비교해서 얼마나 틀렸는지를 확인.
- Cross Entropy 등 다양한 Loss Function들이 있음
- 이 때 계산을 통해 나오는 값이 Loss(Cost, Cost Value 등)이라서 불림
- 이 Loss는 "얼마나 틀렸는지"를 말하며 이 값을 최대한 줄이는 것이 학습의 과정

### **Optimization**
- 앞에서 얻은 Loss 값을 최소화하기 위해 기울기를 받아 최적화된 Variable 값들로 반환
- 이 반환된 값이 적용된 모델은 바로 전에 돌렸을 때의 결과보다 더 나아지게 됨
- 이 때 바로 최적화된 값만큼 바로 움직이는 것이 아닌 Learning Rate만큼 움직인 값이 적용

### **Result**
- 평가 할 때 또는 예측된 결과를 확인 할 때는 예측된 값에서 argmax를 통해 가장 높은 값을 예측한 class라고 둠
# [0.15, 0.3, 0.2, 0.25, 0.1]
- 위의 예측값에서는 0.3이 제일 높은 값이므로 클래스 2가 가장 높다고 봄(파이썬에서 0으로 시작)
