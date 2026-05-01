# kiz库开发指南
**kiz**当前库比较缺乏，邀请您一起为kiz开发库

- [使用C++为kiz开发库](#使用C++为kiz开发库)
- [使用kiz为kiz开发库](#使用kiz为kiz开发库)

## 使用C++为kiz开发库
## 创建命名空间
以库名+lib命名
```
namespace xx_lib
```
## 创建库函数
```cpp
#include "models.hpp" // 必备, 定义了对象模型
#include "kiz.hpp"  // 可选，用于库内抛出异常
#include "vm.hpp" // 可选, 包含call_method, call_function, is_true, obj_to_str, obj_to_debug_str等实用函数
namespace xx_lib {
model::Object* foo(model::Object* self, model::List* args) {
    /// 请在库函数中使用这样的函数签名
    /// 您不需要在函数中管理引用计数, kiz会帮你解决

    /// 抛出异常
    throw NativeFuncError("ErrName", "ErrMag");
}

}
```

实战演练


model中功能拆解


## 使用kiz为kiz开发库
1. 创建库文件夹 `modules/YourLibName`
2. 主逻辑放在 `modules/YourLibName/__main__.kiz`中
3. 在其他kiz文件中使用:
```
import YourLibName
YourLibName.foo()
```

---
author : *azhz1107cat*