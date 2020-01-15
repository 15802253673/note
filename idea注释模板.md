# idea注释模板

## 类模板

> idea设置中 Editor -> File and Code Templates -> File Header

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

   > idea设置中 Editor -> Live Templates
   >
   > 点击右边 +号点击 Template Group 创建新租
   >
   > 点中新组后再点击右边 +号点击 Live Template 
   >
   > Abbreviation 设置为  *
   >
   > 复制下面代码到Template text

   ```java
   *
    * @Description:
    * @Author: yyl
    * @Date: $DATE$ $TIME$
   $PARAMS$
    * @Return: $RETURN$
    */
   ```

   ![](https://github.com/15802253673/note/blob/master/images/1.png?raw=true)

2. 设置对应参数值（对应方法）

   > 选中模板自定义模板点击右边 Edit variables
   >
   > 在Expression列设置对应参数值

   ```java
   参数 DATE
       date()
       
   参数 TIME
       time()
       
   参数 PARAMS
       groovyScript("def result=''; def params=\"${_1}\".replaceAll('[\\\\[|\\\\]|\\\\s]', '').split(',').toList(); for(i = 0; i < params.size(); i++) {result+=' * @Param ' + params[i] + ((i < params.size() - 1) ? '\\r\\n' : '')}; return result", methodParameters()) returns：methodReturnType() exception：expressionType(Expression) 
       
   参数 RETURN
       methodReturnType()
   ```

## 最终示例

```java
/**
 * @Description: 类注释
 * @ClassName: Templates
 * @Author: yyl
 * @Date: 2020/1/3 17:22
 */
public class Templates {

    /**
     * @Description:
     * @Author: yyl
     * @Date: 2020/1/3 17:27
     * @param str
     * @param list
     * @param user
     * @Return: java.util.List
     */
    public List getList(String str,List list,User user){
        return  null;
    }
}
```

