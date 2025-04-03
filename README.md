## Memory Access Latency Analysis on AMD Platforms Based on PMU and IBS

## 项目名称
基于PMU和IBS的AMD平台访存延时探测
## 项目描述
在Intel平台上，CPU与内存控制器通过QPI总线进行高效连接，其可以通过内存控制器上的Uncore PMU（Performance Monitoring Unit）组件统计内存控制器上的访问数据量和拥塞程度来计算内存的访问延时，intel的架构可以参考[5-7]。然而，在 AMD 平台上，由于其采用基于多个CCD（Core Complex Die）封装的独特架构，且在每个 CCD中，AMD 将核心分组为CCX（Core Complex），内存访问延时会明显受到从 CCX 到 Infinity Fabric 之间拥塞程度的影响。如果仅依靠内存控制器上相关的PMU评估访问延时，将无法准确反映实际情况，参考[1-4]。
![image](https://github.com/user-attachments/assets/646ceecc-c7f7-4871-a5f7-6f7e6a61e912)

本项目通过探索 Performance Monitoring Counter [11-12]技术和 AMD 的 Instruction-Based Sampling（IBS）[8-10]技术，来分析AMD访存在各个阶段的延时情况，深入分析内存访问的性能瓶颈，为优化系统性能提供数据支持，从而提升整体计算效率。
![image](https://github.com/user-attachments/assets/7339591e-47d3-454f-a629-f12a66bdaf84)

（注：其中core到DDR总延时可以通过IBS机制获取，Xi到DDR延时可以通过Xi PMU获取，Memory control到DDR延时，可以通过uncore memory PMU获取）
## 所属赛道
2025全国大学生操作系统比赛的“OS功能挑战”赛道
## 参赛要求
● 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2026年春季学期或之后本科毕业的大一~大四的学生）

● 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖

● 请遵循“2025全国大学生操作系统比赛”的章程和技术方案要求
## 支持单位
龙蜥社区(OpenAnolis)
## 项目导师
张菁

● github https://github.com/ZhangJing-hub

● email zj321357@alibaba-inc.com
## 难度
高
## 特征
● Linux 软硬件结合的访存延时分析
## License
● GPL-2.0
## 预期目标
注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标

● 量化分析AMD Genoa架构对NUMA的访存延迟的影响。

● 学习PMU、IBS硬件机制、使用方法及采集数据解析，调研AMD Genoa是否具有uncore memory PMU。

● 实现基于PMU和IBS的AMD平台实时访存延时的实时探测工具，分析是Xi、Infinity Fabric还是内存控制器性能瓶颈问题。

## 参考资料：
[1]https://chipsandcheese.com/p/pushingll-amds-infinity-fabric-to-its

[2]https://qsantos.fr/2024/10/03/amd-cpus-ccds-and-ccxs/

[3]https://www.sohu.com/a/341460511_120116768

[4]https://en.wikichip.org/wiki/amd/microarchitectures/zen_4

[5]https://blog.csdn.net/qq_39815222/article/details/131040870

[6]https://gitee.com/anolis/cloud-kernel/blob/devel-6.6/tools/perf/pmu-events/arch/x86/icelakex/uncore-memory.json

[7]https://blog.csdn.net/essencelite/article/details/142682124

[8]https://www.amd.com/content/dam/amd/en/documents/archived-tech-docs/software-optimization-guides/40546.pdf

[9]https://github.com/jlgreathouse/AMD_IBS_Toolkit/blob/master/README.txt

[10]https://alessandropellegrini.it/theses/IBS.pdf

[11]https://xryan.net/p/168

[12]https://openanolis.cn/sig/ARM_ARCH_SIG/doc/774254734868851019
