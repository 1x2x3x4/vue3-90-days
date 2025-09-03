reactive

定义：可以接收一个对象类型数据的参数并返回一个响应式的对象

使用

```javascript
import {reactive} from 'vue'

const state = reactive({	//里面是对象类型数据
    count:0	
})

```

ref

定义：可以接收一个简单数据类型或者复杂数据类型的参数，并返回一个响应式的对象

使用

```
import {ref} from 'vue'

const state = ref(0)	//里面可以是对象类型数据也可以是其他的数据类型

//访问参数
state.value
```



总结：

相同点：都返回一个响应式的对象

ref里面的值必须通过.value访问修改，ref的内部实现依赖于reactive函数
注：ref当初始值是对象时，会对内部值做 `reactive`