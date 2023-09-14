# 心得
有一些地方可以做修改，主要是在速度函數那裡。

> 這是線性的實現方法
```ino
    int distance = ultrasonic_3.distanceCm(); // 獲取距離
    if (distance > 10) {
      int speed = map(distance, 10, 100, 0, 255);

      speed = constrain(speed, 0, 255);

      move(1, speed);
```
> 這是非線性的實現方法
```ino
    float speedFactor = pow(distance, 2) / 10000.0;
    int speed = int(speedFactor * 255);

    speed = constrain(speed, 0, 255);
```
