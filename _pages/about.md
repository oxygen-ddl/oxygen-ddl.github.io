---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

# 关于我

我是王立，目前是[哈尔滨工业大学（威海）](https://www.hitwh.edu.cn)机器人工程专业的本科生。

我的研究兴趣包括机器人运动控制、具身智能、自主无人系统和实时嵌入式系统。


# 教育背景

- *2023.09-至今* \| 机器人工程工学学士 \| [哈尔滨工业大学（威海）](https://www.hitwh.edu.cn)

# 科创经历

- *2024.09-2026.04* \| ROVER水下机器人实验室 \| 电控组负责人
  - 参加全国海洋航行器设计大赛，设计机器人的电控系统整体方案
  - 参与实验室新成员面试、考核与培训

- *2024.11-2026.01* \| 机器人研究所 \| 本科生成员
  - 参与水下机器人冗余控制系统开发，负责香橙派与STM32异构通信及姿态控制算法实现
  - 完成轮足机器人LQR最优控制系统建模、控制器设计


# 项目经历

- *2025.03 – 2025.08* \| **堤坝智能巡检水下机器人** \| 队长 · 嵌入式软件负责人

  - **RTOS多线程系统**：采用STM32F407VET6主控与STM32F103协处理器，在STM32CubeMX中完成硬件初始化配置，接入FreeRTOS实时操作系统，在Keil MDK环境下设计6个实时任务线程（传感器采集、TCP通信、导航规划、姿态控制、水声定位）。利用队列和信号量实现任务同步，控制频率达到200Hz。

  - **通信系统设计**：通过I²C协议读取深度传感器与温湿度传感器，通过USART读取IMU数据，使用串转网芯片CH9121实现TCP协议与上位机进行稳定数据交互。

  - **运动控制与自主巡检**：设计级联PID控制器实现ROV姿态稳定（俯仰/横滚精度±2°）；基于TDOA水声脉冲时差算法实现水下测距，解决GPS受限环境下的定位问题，测距误差<5%。实现沿xyz轴平移与绕xyz轴旋转运动控制，并完成大坝表面遍历路径规划，配合摄像头识别完成裂缝检测任务。

  - **项目成果**：带领5人团队完成水下坝体三维建模与裂缝风险评估系统，获得**全国海洋航行器设计大赛全国一等奖**及**省级三等奖**。

  **项目链接**：  
  [GitHub仓库](https://github.com/oxygen-ddl/stm32f407_rov_freertos)

  **电器性连接图**：
  ![电器性连接图](collections/ROV/image.png)

**巡检实机演示视频：**

<div style="display: flex; gap: 16px; flex-wrap: wrap; margin-top: 20px;">

  <div style="flex: 1; min-width: 280px;">
    <video src="collections/ROV/Image86.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
    <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
      1. 锁定姿态平移演示
    </p>
  </div>

  <div style="flex: 1; min-width: 280px;">
    <video src="collections/ROV/Image89.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
    <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
      2. 潜航过门演示
    </p>
  </div>

  <div style="flex: 1; min-width: 280px;">
    <video src="collections/ROV/Image92.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
    <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
      3. 标记裂缝演示
    </p>
  </div>

  <div style="flex: 1; min-width: 280px;">
    <video src="collections/ROV/VID_20260409_162318.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
    <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
      4. 子弹前进演示
    </p>
  </div>

</div>

<br><br>
- *2025.09 – 2026.01* \| **水下机器人冗余控制系统** \| 核心成员 · 通信设计

  - **异构通信架构设计**：在香橙派（Ubuntu 20.04）上使用C++开发UDP通信模块，以香橙派作为主控中心，通过自定义二进制数据包结构（帧头+帧尾+CRC校验）与心跳机制，实现与STM32F407的双向实时通信。完成8通道推进器PWM控制指令下发与深度、IMU数据的可靠回传，并在心跳丢失等异常情况下自动触发自我保护机制。

  - **传感器驱动与分层架构**：阅读DVL多普勒水下测速传感器技术手册，在香橙派端使用C++独立编写串口驱动程序，实现水下三维速度的实时采集与解析。在此基础上开发运动控制程序，将上层算法输出的运动参数精准映射到8通道推进器输出，搭建了完整的水下控制算法测试平台。

  - **项目成果**：成功构建水下机器人冗余姿态控制系统，实现机器人按照预定路线自主稳定行驶，获得软件著作权《冗余驱动水下机器人姿态控制系统》。
  
  **舱内硬件排布**：
  ![舱内硬件排布](collections/ROV_Orangepi/IMG_20260409_161704.jpg)

  **项目链接**：  
  [GitHub仓库](https://github.com/oxygen-ddl/OrangePi_STM32_for_ROV)

  **演示视频(2倍速)：**

  <div style="margin-top: 15px;">
    <video src="collections/ROV_Orangepi/VID_20260409_115922.mp4" controls="controls" width="85%" style="border-radius: 8px; max-width: 800px;"></video>
  </div>

  <br><br>

- *2025.04 – 2025.05* \| **有感无刷电机FOC驱动设计** \| 个人项目

  - **硬件电路与PCB设计**：使用嘉立创EDA独立完成三相全桥驱动电路原理图设计与4层PCB Layout。选用STM32G431CUB6作为主控芯片，EG2133作为三相全桥驱动芯片，集成INA240电流采样电路、AS5600 12位磁编码器接口、XL1050 CAN收发器及TPS54331DR 5V电源模块。

  - **FOC控制算法实现**：在STM32G431平台上基于SPWM模型开发FOC矢量控制程序，通过AS5600磁编码器获取电机转子位置，完成Clarke与Park坐标变换；设计电流环（1kHz）、速度环（500Hz）、位置环（200Hz）三闭环系统，并开发CAN总线通信接口，实现对无刷关节电机的高精度控制。

  - **项目成果**：成功实现电机电流、速度、角度高精度闭环控制，开发出一套低成本有感无刷电机FOC驱动方案，单块驱动板硬件成本控制在100元以内，为关节电机控制提供了高性价比解决方案。

  **硬件与实物展示：**

  ![FOC驱动板原理图](collections/FOC_driver/SCH_Schematic3_2026-04-09_01(1).png)
  *图1：FOC驱动板原理图*


  <div style="display: flex; gap: 20px; flex-wrap: wrap; margin: 20px 0 30px 0;">
    
    <div style="flex: 1; min-width: 320px; text-align: center;">
      <img src="/collections/FOC_driver/PCB_PCB3_2026-04-09.png" alt="FOC驱动板PCB Layout" style="width:100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
      <p style="margin-top: 12px; color: #555; font-size: 0.95em;">图2：4层PCB Layout设计</p>
    </div>

    <div style="flex: 1; min-width: 320px; text-align: center;">
      <img src="/collections/FOC_driver/3D_PCB3_2026-04-09.png" alt="FOC驱动板3D视图" style="width:100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
      <p style="margin-top: 12px; color: #555; font-size: 0.95em;">图3：PCB 3D渲染图</p>
    </div>

  </div>

  ![FOC驱动板实物照片](collections/FOC_driver/real_picture.jpg)   
  *图4：FOC驱动板实物展示（上方为第一版，下方为最终优化版）*

  **算法验证视频：**

  <div style="display: flex; gap: 15px; flex-wrap: wrap; margin-top: 15px;">
    <div>
      <p><strong>使用DengFOC开发板验证FOC算法：</strong></p>
      <video src="collections/FOC_driver/VID_20250412_170553.mp4" controls="controls" width="400" height="auto"></video>
    </div>
    <div>
      <p><strong>使用自制PCB + FOC算法实际运行：</strong></p>
      <video src="collections/FOC_driver/VID_20260409_153013.mp4" controls="controls" width="280" height="auto"></video>
    </div>
  </div>

<br><br>

- *2026.01* \| **轮足机器人LQR控制** \| 个人项目

  - **系统建模与分析**：针对并联腿轮足机器人建立完整运动学与动力学模型，推导轮地接触约束下的非线性状态空间方程（状态量：机身俯仰角、机身高度、轮速；控制量：轮毂电机力矩）。在MATLAB/Simulink中完成模型线性化、可控性及可观性分析，为后续控制器设计提供准确数学基础。

  - **LQR最优控制器设计**：通过求解代数Riccati方程设计LQR状态反馈控制器，得到最优增益矩阵K，实现0.15m–0.25m变腿高范围内的自平衡控制。实际测试中调节时间小于2s，显著提升了机器人动态平衡能力。

  - **柔顺力控实现**：基于Virtual Model Control（VMC）实现腿部柔顺力控制，通过虚拟弹簧-阻尼模型模拟腿部柔性特性，有效吸收地面冲击，提升机器人对台阶、斜坡及不平坦地形的适应能力。

  **项目链接**：  
  [GitHub仓库](https://github.com/oxygen-ddl/wheel_leg_esp32)

  **实机演示视频：**

  <div style="display: flex; gap: 12px; flex-wrap: wrap; margin-top: 15px;">
    <video src="collections/wheel_leg/VID_20260409_102838.mp4" controls="controls" width="32%" height="auto" style="border-radius: 8px;"></video>
    <video src="collections/wheel_leg/VID_20260409_102725.mp4" controls="controls" width="32%" height="auto" style="border-radius: 8px;"></video>
    <video src="collections/wheel_leg/VID_20260409_104859.mp4" controls="controls" width="32%" height="auto" style="border-radius: 8px;"></video>
  </div>
<br><br>

- *2025.01-2025.08* \| 混凝土3D打印机器人 \| 创业合作人
  - 完成模型的开发：在MATLAB/Simulink中建立泵系统动态模型；使用Embedded Coder为STM32F407自动生成C代码，实现末端稳定出料
  - 选型与供电设计：基于力矩和惯量计算为六自由度机械臂选择伺服电机、减速器和驱动器；设计24V/48V双电源供电系统及优化功率分配
  - 成果：参与联合调试，完成混凝土墙连续打印（0.4m×0.4m×0.6m），精度±5mm，验证建筑机器人工业可行性
  **机械臂调试展示：**

  <div style="display: flex; gap: 16px; flex-wrap: wrap; margin-top: 20px;">

    <div style="flex: 1; min-width: 200px;">
      <video src="collections/ES/VID_20250402_111330.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
      <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
        1. 机械臂单关节调试演示
      </p>
    </div>

    <div style="flex: 1; min-width: 320px;">
      <video src="collections/ES/VID_20260409_163355.mp4" controls="controls" width="100%" style="border-radius: 10px;"></video>
      <p style="text-align: center; margin-top: 12px; color: #333; font-weight: 500;">
        2. 机械臂多关节协同运动演示
      </p>
    </div>

  </div>

# 获奖与荣誉

### 科创
- *2025* \| 全国一等奖，全国海洋航行器设计大赛（澜巡智卫-水利工程巡检机器人）
- *2025* \| 省级三等奖，全国海洋航行器设计大赛
- *2025* \| S奖，美国大学生数学建模竞赛
- *2026* \| 软件著作权《冗余驱动水下机器人姿态控制系统》

### 荣誉
- *2024, 2025* \| 国家励志奖学金
- *2024* \| 二等人民奖学金
- *2024* \| 实学实干优秀学生奖
- *2024, 2025* \| 优秀团员



# 联系方式

- 邮箱：2023212693@std.hit.edu.cn
- 电话：+86 18423121673
- GitHub：[github.com/oxygen-ddl](https://github.com/oxygen-ddl)