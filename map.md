# map

map也被称为键值对，也分为map和multimap，与set类似

#### 定义/初始化

```map<type,type>v;```

第一个type通常称为**键(key)值**，第二个为**值(value)**，两者成对出现

插入值也可以用pair

```v.insert(pair<int,int>(1,2))```

#### 输出

输出需要迭代器

使用方法：

```c++
map<int,int>m;
//插入
for(map<int,int>i=m.begin();i!=m.end();i++)
{
    cout<<i->first<<(*i).second;//链表输出形式
}
```



#### 基本操作

| 形式               | 说明                              |
| ------------------ | --------------------------------- |
| m.empty()          | 检查m是否为空                     |
| m.swap(m2)         | 交换m,m2                          |
| m.erase(值)        | 删除key为3的值,只按key删val不会删 |
| m.erase(begin,end) | 删除区间内的值[)                  |
|m.clear()|清空整个容器|

#### 插入

插入时可用**对组pair**插入

方法1```v.insert(pair<int,int>(1,2))```

方法2```v.insert(make_pair(1,2))```

方法3```v[键值]=值```

```c++
map<int,int>m;
//插入
m[99]=98;
cout<<m[99];//输出结果为98
//若m[90]不存在，使用cout输出时结果为0，但再次使用迭代器进行遍历输出时，会将90,0添加到m中
```

当key值存在时，使用insert进行插入时不会生效

当key值存在时，执行m[存在的值]=值时会直接替换

#### map的统计和查找

| 形式           | 作用                                               |
| -------------- | -------------------------------------------------- |
| m.find(key值)  | 查找键值为key的是否存在，不存在则为end()           |
| m.count(key值) | 若为map,值为0或1，multimap可存在多个，返回值为整形 |

map的默认排序规则是按照key从小到大的顺序排列

##### map与pair搭配时

```c++
map<pair<int,int>,int>a;
for(int i=0;i<n;i++)
{
    for(int j=0;j<n;j++)
    {
        a.insert(make_pair((make_pair(i,j)),j));
        //或者
        a[make_pair(i,j)]=j;
    }
}
```

