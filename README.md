# SZUT_RM_HW

上海应用技术大学 Robotics Master 课程作业仓库。

## 目录结构

| 路径 | 内容 |
| --- | --- |
| `261114/` | 按日期归档的作业，每天一个目录 |
| `261114/hw/` | 作业 3：mini_vision 多线程视觉处理流水线 |
| `ex1`～`ex4` | 课堂动手实验（C++17 / OpenCV） |
| `demos/` | 演讲中通过 Python Tutor 展示的示例代码 |

## 环境

推荐 Ubuntu 22.04：

```bash
sudo apt update
sudo apt install -y g++ cmake libopencv-dev
```

## 构建课程示例

在仓库根目录执行：

```bash
cmake -S . -B build
cmake --build build -j
```

可执行文件生成在 `build/` 下：

```bash
./build/ex1
./build/ex2
./build/ex3
./build/ex4
```

## 构建并运行作业

```bash
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build -j
ctest --test-dir build --output-on-failure
```

作业的详细说明、任务要求与检查脚本见 [`261114/hw/README.md`](261114/hw/README.md)，
技术报告见 [`261114/hw/report.md`](261114/hw/report.md)。

一键执行完整检查（构建 + ctest + 多 worker 验证 + 报告格式检查）：

```bash
cd 261114/hw && ./scripts/check.sh
```

### 图像素材

`261114/hw/assets/` 中的 20 张 PPM 图像未纳入版本控制（共约 4.6 MB），
可通过脚本按需重新生成：

```bash
python3 261114/hw/scripts/generate_assets.py
```
