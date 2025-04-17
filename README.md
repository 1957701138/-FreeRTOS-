# -FreeRTOS-
基于FreeRTOS的实时多模态健康监护系统
项目介绍：利用STM32并结合FreeRTOS设计实时多模态健康监护系统，利用FerrRTOS同时运行心率监测与姿态监测两个任务。实时监测心率和身体姿态信息。
硬件平台：STM32F103C8T6、MAX30100心率血氧传感器、MPU6050六轴传感器、0.96寸OLED。
通讯系统：通过I2C协议实现OLED、MAX30100、MPU6050与STM32的通讯。
信息采集系统：第一个任务利用MAX30100配合STM32定时器多次采集血氧间分信号经过处理后得到脉搏信息 ，心率过快或过低就会刷新OLED进行更新；第二个任务利用MPU6050实时计算人体姿态和加速度，和加速度过快或过低会判断人体是否出现跌倒会刷新OLED进行更新。心率或者和加速度平稳代表人体姿态正常则会取消异常提示。
