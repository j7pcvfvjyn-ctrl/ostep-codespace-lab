# Chapter7 CPU‑Scheduling 实验分析报告

> 实验环境：GitHub Codespaces
> 模拟器路径：`./ext/ostep-homework/cpu-sched/scheduler.py`
> 评价指标：**平均周转时间(Turnaround Time)**、**平均响应时间(Response Time)**
> 调度算法：FIFO、SJF、RR(Round‑Robin)

---

## 名词回顾
- **周转时间 Turnaround Time**：作业从到达至完成的时间  `T_turnaround = T_completion − T_arrival`
- **响应时间 Response Time**：作业从到达至第一次获得CPU运行的时间 `T_response = T_firstrun − T_arrival`
- **FIFO**：先来先服务，非抢占，作业运行完毕才切换
- **SJF**：短作业优先，非抢占，选当前剩余运行时间最短作业执行完毕
- **RR**：时间片轮转，抢占式；每个作业运行`quantum(时间片)`之后切换下一个就绪作业

---

## Q1 【示例，仿照这个格式写你的题目】
> 实验参数：
> 作业长度：`‑l 100,200,300`
> 调度策略：FIFO
> 命令：
> ```bash
> python3 ./ext/ostep-homework/cpu-sched/scheduler.py -l 100,200,300 -p FIFO -c > hw/chapter7/data/q1_fifo.txt
> ```

### ① 手动预测（不带‑c推演）
甘特图：

