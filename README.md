## 大数据渲染

### 常用加载、渲染方式

1. 分页加载

    优：易实现，兼容性好，DOM 节点数量少，性能稳定；

    缺：无法全量展示数据，频繁翻页致使用户体验下降；

    场景​​：表格、列表等需要明确分页导航的场景
2. Element [懒加载 / 按需加载 / 无限滚动](https://element-plus-docs.bklab.cn/zh-CN/component/infinite-scroll.html)

    优：减少初始负载，按需加载；

    缺：无法全量展示数据，实现复杂；

    场景：社交媒体等无限滚动的场景；
3. 虚拟滚动列表，优化大数据渲染；
   - Element [Virtual Table](https://element-plus-docs.bklab.cn/zh-CN/component/table-v2.html)
   - [Vue Virtual Scroll List](https://www.npmjs.com/package/vue-virtual-scroll-list)

    优：保持 DOM 节点数量恒定，性能极佳，支持全量数据展示；

    缺：快速滚动可能出现空白；

    场景：长列表、聊天记录、日志等；
4. 对于图标等，可以使用 Echarts 渲染；
   - 属性：large
   - 属性：largeThreshold

#### 性能优化

- WebWorker

  在渲染之前进行数据处理，可以使用 WebWorker 进行数据处理，避免阻塞主线程。

- requestAnimationFrame

  时间分片进行分批渲染

## 实际场景

运营平台：下拉列表数据量大，导致关闭弹窗、切换列表时，页面卡顿；

### 自定义虚拟列表

### canvas 渲染