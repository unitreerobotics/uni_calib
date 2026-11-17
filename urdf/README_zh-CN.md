# 手眼标定用 URDF

[English](README.md) | 中文

手眼标定（机器人实时采集）时在页面上选择对应机器人的 URDF 文件。这里只放 URDF 与其引用到的网格，不打包进 AppImage。

| 目录 | URDF | 机型 | 说明 |
|---|---|---|---|
| `g1_description/` | `g1_29dof_rev_1_0.urdf` | G1（29 自由度） | 来源见 `SOURCE.txt`（unitree_ros），未修改 |
| `g1_d_description/` | `g1_d.urdf` | G1_D | 未修改 |
| `r1_d_description/` | `r1_d_with_dex1_1.urdf` | R1-A7-D（Dex1 夹爪） | 含腕部相机 link（`*_dex1_camera_link`），用于与标定结果比较 |

* 机型按 URDF 的 `<robot name>` 识别（`g1_29dof*` → G1，`G1_D*` → G1_D，`R1_A7_D*` / `R1_D*` → R1-A7-D，不分大小写），再逐个核对运动链上的关节；名称认不出时只按关节匹配。
* 正运动学只用 URDF 文件本身；`meshes/` 只用于结果的“3D 查看”。
* URDF 中的末端执行器不参与标定，3D 查看中也不显示。
* 网格按 URDF 中的 `meshes/<文件名>` 相对路径查找，移动目录时请保持 URDF 与 `meshes/` 的相对位置不变。
