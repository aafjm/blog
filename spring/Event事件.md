### Event事件
- 实现了异步处理
- @Async，另起一个线程去实现
- 观察者模式

### 代码实现 
- applicationContext.publishEvent(xxEvent); 
- xxEvent extends ApplicationEvent
- xxListener implements ApplicationListener<xxEvent>

### 源码:观察者模式
- publishEvent -> multicastEvent -> invokeListener -> listener.onApplicationEvent(event);
