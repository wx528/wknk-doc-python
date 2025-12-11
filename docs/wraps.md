# wraps: Decorator

### A Simple Decorator Example 
```
import time
from functools import wraps

def timing(func):
    """
    一个用于计算函数执行时间的装饰器。
    """
    # 使用 @wraps 来保留原函数的元数据（名称、文档等）
    @wraps(func)
    def wrapper(*args, **kwargs):
        # 1. 前置处理：记录开始时间
        start_time = time.perf_counter()
        
        # 2. 调用原函数
        result = func(*args, **kwargs)
        
        # 3. 后置处理：记录结束时间并计算耗时
        end_time = time.perf_counter()
        run_time = end_time - start_time
        
        print(f"函数 {func.__name__!r} 执行耗时: {run_time:.4f} 秒")
        
        # 4. 返回原函数的执行结果
        return result
    return wrapper



@timing
def calculate_power(n):
    """计算 n 的平方和，故意延迟。"""
    time.sleep(0.5) # 模拟耗时操作
    return sum(i*i for i in range(n))

# 调用被装饰的函数
result = calculate_power(100000)

```