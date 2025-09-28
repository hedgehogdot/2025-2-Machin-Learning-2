# 2025-2-Machin-Learning-2

## Assignment1 : KNN 구현하기
**(a)** 반복문(for loop)을 이용한 iterative 방식으로 k-NN 알고리즘(k=5)을 구현 -> 단일샘플 테스트

**(b)** broadcasting 개념을 이용한 방식으로 k-NN 알고리즘(k=5)을 구현 -> 단일샘플테스트
      테스트 결과 forloop보다 broadcasting의 소요시간이 훨씬 더 적었음 (그러나 단일샘플 테스트이므로 차이 미미)
  
**(c)** k-NN 알고리즘을 확장하여, 단일 이미지뿐만 아니라 **모든 새로운 이미지(테스트 데이터 전체)**에 대해 테스트

  문제1) broadcasting사용시 메모리 터짐
  
  1차 해결책) 거리계산시 벡터를 한번에 flatten이 아닌 for loop을 사용
  2차 해결책) k개의 이웃을 찾을때 heapq를 사용
  문제) 두 해결책 다 for loop을 결국 써야하므로 너무 오래걸림
**(d)** 문제를 해결할 수 있는 방법
  해결책1) for loop과 broadcasting이 아닌 pytorch 내장함수인 **torch.cdist()**를 활용해 거리를 쉽게 계산
  해결책2) for loop와 heapq가 아닌 pytorch 내장함수인 **torch.topk()**를 사용해서 한 번에 k개의 최근접 이웃 필터

**(f)** 각 하이퍼파라미터에 대해 최소 두 가지 이상의 다른 값을 시도해보고, 그 결과에 대한 관찰을 작성하시오.

**(g)** 원한다면 더 많은 옵션을 시도해도 된다. 최종적으로 테스트 데이터에서 얻은 최종 정확도를 작성하시오.
