# idea注释模板

## 类模板

```java
/**
 * @Description: 
 * @ClassName: ${NAME}
 * @Author: yyl
 * @Date: ${DATE} ${TIME}
 */
```

## 方法模板

1. java代码中/**+enter快捷键设置

   ```java
   *
    * @Description:
    * @Author: yyl
    * @Date: $DATE$ $TIME$
   $PARAMS$
    * @Return: $RETURN$
    */
   ```

   ![](https://github.com/15802253673/note/blob/master/images/%E6%96%B9%E6%B3%95%E6%B3%A8%E9%87%8A.png?raw=true)

   

2. 设置对应参数值（对应方法）

   ```java
   DATE
       date()
       
   TIME
       time()
       
   PARAMS
       groovyScript("def result=''; def params=\"${_1}\".replaceAll('[\\\\[|\\\\]|\\\\s]', '').split(',').toList(); for(i = 0; i < params.size(); i++) {result+=' * @param ' + params[i] + ((i < params.size() - 1) ? '\\r\\n' : '')}; return result", methodParameters()) returns：methodReturnType() exception：expressionType(Expression) 
       
   RETURN
       methodReturnType()
   ```





