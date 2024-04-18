### JS数组基本方法

1. `push()` 尾部插入
2. `unshift()` 头部插入
3. `pop()` 尾部删除
4. `shift()` 头部删除
5. `splice(5,1,2,3,4)` 从索引5开始 删除1个元素并把 2 3 4 从索引 5 插入
6. `concat(arr1, arr2)` 连接两个或多个数组 也可以连接对象或者元素
7. `every(callback())` 测试数组中的所有元素是否都通过了由提供的函数实现的测试 全满足true 否则false
8. `some(callback())` 数组中只要有一个元素通过测试就返回 true
9. `forEach()` 迭代整个数组 与for循环使用相同
10. `map(callback())` 迭代整个数组 保存每个元素被函数处理的结果 返回新数组
11. `filter(callback())` 迭代整个数组 保存callback()返回true的元素 返回新数组
12. `reduce()`详解：

    >array.reduce(function(accumulator, currentValue, currentIndex, array), initialValue)

    **accumulator（累加器）**：累加器累加回调的返回值；它是上一次调用回调时返回的累积值，或者是提供的初始值（initialValue），不提供初始值默认为数组第一个元素，函数执行将从次二个元素开始。

    **currentValue（当前值）**：数组中正在处理的当前元素。

    **currentIndex（当前索引）（可选）**：数组中正在处理的当前元素的索引。如果提供了initialValue，则起始索引号为0，否则为1。

    **array（数组）（可选）**：调用reduce方法的数组。

    **initialValue（初始值）（可选）**：作为第一次调用callback函数时第一个参数的值。如果没有提供初始值，则将使用数组中的第一个元素。
13. `Symbol.iterator`详解：

    > let iterator = numbers[Symbol.iterator]();  
    > console.log(iterator.next().value);

    @@iterator是一个内置的Symbol值，Symbol.iterator，它指定了一个对象的默认迭代器。当一个对象需要被迭代（比如在一个for...of循环中）时，它的@@iterator方法被调用，无需任何参数，并且返回一个用于获取对象中的值的迭代器。

    虽然@@iterator并不是直接作为数组的方法引入的，数组类型自ES6起默认实现了这个接口，使得数组成为可迭代的对象。这意味着你可以直接在数组上使用for...of循环，或者使用扩展运算符（...）来遍历数组的元素，而这背后都是因为数组类型实现了Symbol.iterator方法。

    > es5通过forEach()等方法进行的迭代是通过利用回调函数访问数组元素的形式进行的迭代，ES6中的数组被认为是“可迭代的”，因为它们实现了Symbol.iterator属性。这意味着数组不仅可以使用.forEach和其他ES5中的迭代方法，还可以使用for...of循环、扩展运算符等ES6中引入的特性，这些特性提供了更为直接和灵活的迭代方式。例如，使用for...of可以直接迭代数组中的元素，而不需要提供回调函数

14. `Array.from()`详解：

    > let evens = Array.from(numbers, x => (x % 2 == 0));

    Array.from()可以将一个数组转换成一个新的数组，并支持接受一个回调函数，在生成新数组的同时进行映射操作，类似于 map() 但是Array.from()比 map() 更强大的地方在于它可以将一个类数组，一个可迭代的其他对象转换为数组，并且在转换的同时执行回调函数对元素进行处理

    处理数组时，使用map()即可，处理类数组时使用 Array.from()更好

15. `fill()` 填充数组 fill(1) 将数组所有元素换成 1，fill(1,3,5) 将数组索引 3-5（不包括 5） 的两个元素换成 1
16. `copyWithin()` 复制一部分数组中的元素 放到数组的指定起始位置  copyArray.copyWithin(1, 3, 5); 将索引 3-5（不包括 5）的两个元素贴到索引1的位置
17. `reverse()` 将数组反转
18. `sort(callback())` 根据回调函数对数组进行排序
19. `indexOf()` 返回与参数匹配的第一个元素的索引
20. `lastIndexOf()` 返回与参数匹配的最后一个元素的索引
21. `find(callback())` 返回第一个满足函数条件的元素
22. `findIndex(callback())` 返回第一个满足函数条件的元素的索引
23. `includes()` 数组中是否存在某个元素 支持接受第二个参数代表从哪个索引开始搜索
24. `toString()` 把数组中所有元素输出为一个字符串
25. `join()` 把数组中所有元素输出为一个字符串 可以指定分隔符

