### Q1: 已经p完盘，为什么矿池的仪表盘不显示挖矿数据？
A：主网上线后留了一段时间让矿工p盘，后续才会开启出块，请等待通知。

### Q2: 是否有 Windows 和 HiveOS 版本？
A：目前不支持 Windows 和 HiveOS。

### Q3: 是否支持 CPU P 盘？
A：CPU 和 GPU 都可以进行 P 盘，但从效率角度来看，建议使用 GPU。

### Q4: 如何查看 P 盘进度？
A：可以在 farmer 或 plotter 的日志中查看。开始 P 盘后，日志中会显示类似以下信息：
```
Plotting sector（XX% complete）
```

### Q5: 可否同时使用多个GPU进行 P 盘？
A：支持多 GPU，软件会默认用所有 GPU。
