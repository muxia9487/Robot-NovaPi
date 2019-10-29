###### README.md Power by `Markdown`
# 本專案適用mBlock-NovaPi
###### _Power by BaiSheng10081_
###### [Python]
###### TG: https://t.me/c/1453792738/106
## **NovaPi-LMove-Rshoot-Python.mblock**

### ***Move Motor Pin Chanel***
```python
__encoder_motor_M1 = encoder_motor_class("M1", "INDEX1")
    # 右前輪
__encoder_motor_M2 = encoder_motor_class("M2", "INDEX1")
    # 左前輪
__encoder_motor_M3 = encoder_motor_class("M3", "INDEX1")
    # 左後輪
__encoder_motor_M4 = encoder_motor_class("M4", "INDEX1")
    # 右後輪
```
---
### ***Shoot Motor Pin Chanel***
```python
__smartservo_1 = smartservo_class("M6", "INDEX1")
    # 控制射擊仰角的伺服馬達
def _E5_BD_88_E8_97_A5_E9_81_8B_E9_80_81 (): 
    # 這串16進制數字(彈藥運送)為{中文編碼[UTF-8](寫程式盡量不要用中文)}
    global Deg, P, S, RB, RA, C, FL, FR, BL, BR, GO, CP
    # 定義[全域變數(global)]
    if gamepad.is_key_pressed("N2"):
                        # 2號按鍵("N2")
        RA = RA * -1
        while not not gamepad.is_key_pressed("N2"):
            pass

        power_expand_board.set_power("DC2", 100 * RA)
            # 掃球使用[“DC2”]輸出100 * RA 的轉速
    if gamepad.is_key_pressed("N3"):
                        # 3號按鈕("N3")
        power_expand_board.stop("DC2")
            #停止["DC2"]訊號發送
        RA = 1

    if gamepad.is_key_pressed("N4"):
                        # 4號按鈕("N4")
        RB = RB * -1
        while not not gamepad.is_key_pressed("N4"):
            pass

        power_expand_board.set_power("DC1", 100 * RB)
            # 上膛線使用[“DC1”]輸出100 * RB 的轉速
    if gamepad.is_key_pressed("N1"):
        power_expand_board.stop("DC1")
            # 停止["DC1"]訊號發送
        RB = -1
```
## GamePad Instruction manual
* 左側蘑菇頭操作機器人進行X, Y移動
* 右側蘑菇頭控制機器人進行360º旋轉
<br></br>

| **Button** | *N1*| *N2*| *N3*| *N4*| *R1*| *R2*| *<-*| *->*|
|-|:-:|:-:|:-:|:-:|:--:|:-:|:-:|:-:|
| **Click**   | 上膛線| 掃球| 停止膛線電機| 停止掃球電機| 擊球器開始加速| 停止擊球器運作| 四驅轉速調整為2.5單位(s)| 四驅轉速調整為0.5單位(s)|
| **Double Click**| 改變電機方向| 改變電機方向| 
