# 心得
我在上一個禮拜的程式碼的基礎上，我讓她在過於靠近物體時會倒退。

```ino
    if (distance > 10) {
      // 將距離線性映射到速度範圍
      int speed = map(distance+20, 10, 100, 0, 255);

      // 限制速度在0到255之間
      speed = constrain(speed, 0, 255);

      move(1, speed); // 前進，速度根據距離動態調整
    } else if(distance > 5){
      motor_9.run(0); // 停止左馬達
      motor_10.run(0); // 停止右馬達
    } else {
        move(2, 50 / 100.0 * 255);
    }
```
