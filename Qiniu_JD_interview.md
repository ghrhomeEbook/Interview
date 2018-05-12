#  七牛云和京东面试总结

## 背景

``` bash
    大三，专业为软件工程，自学前端与后端差不多一年，由于大三很多小伙伴都外出实习，于是 “ 博主 ” 也想投简历试试，如果运气好，没准能得个offer ?  事实证明，运气还是差了点。
```
## 看中 “ 春招 ”

``` bash
    大公司在每年的三四月进行春招，于是我拜托了在七牛云的学姐和在京东的学长内推。在改了不下10来遍的简历之后，终于将简历投了出去，七牛云直接面试，不需笔试，京东则经过了笔试。笔试过了，于是给我发了面试通知~
```
## 出发 “ 上海 ”

``` bash
    4.11号的时候，收到七牛云的电话，说后天下午2.30电话视频面试，本觉得京东笔试挂了。但是在当天晚上收到京东的面试通知，面试地点在上海，由于博主在湖南湘潭，于是给京东回了一封邮件，内容大概是 ：“ 无法及时到达，能否改为线上视频面试 ” ，第二天一大早回了我的邮件，大意就是 ：“ 面试由面试官决定，会帮我申请电话远程面试，但是不一定会有安排 ~ ” 因为七牛云和京东都在上海，所以博主翘了课，坐上高铁去了上海~
```
# 先来谈谈七牛云
> 第一家面试的公司，很紧张，好像当天只有我一个面试者，因为七牛云的笔试好像是在当天晚上。
``` bash
    奔波到了七牛云的公司后，在前台签了个到，然后把我领到一旁，让我骚等，过了一会，来了一个面试官，很和善，然后就开始面试。因为之前学姐给了我的简历给他看，所以问了四五个问题，然后开始写算法....
```

## 问了什么问题 ？
<div style="font-size: 15px">
    <p>面试官 : 你了解BFC吗？能说说是什么，形成BFC有什么条件？我回答 : 块级格式化上下文，一般形成的条件就是float除了none以外的值，还有绝对定位fixed和absolute，以及overflow除了visible之外。比如同一个BFC下，div1的margin-bottom : 30px， 然后div2的margin-top : 50px，然后这时候其实发生了 “ 塌陷 ” div1 和 div2 之间相距并不是30+50，而是取大的50px。</p>
</div> 

<div style="font-size: 15px">
    <p>接着，面试官 : 看你简历上面有写Nginx配置，说一下原理？nginx我很少用，一般跨域我都是在php后台修改header，nginx我才配过一次，如何配置我知道，但是要我说原理，我当场懵逼。（后来看了一下，是通过把本地的url前缀映射到要跨域的web服务器上，而nginx通过检测url前缀，把http请求转发到真实的物理服务器，并通过rewrite命令把前缀再去掉。简单说就是nginx服务器欺骗了浏览器，让它认为这是同源调用，又通过重写url，欺骗真实的服务器）</p>
</div> 

<div style="font-size: 15px">
    <p>然后面试官又问 : 你前端用vue，应该熟悉vue吧，讲一下vue的生命周期，在每一个周期都做了什么事情。我回答 : vue的生命周期： beforeCreate周期，init events，初始化生命周期、data、watch等，然后接着到created周期，在created周期期间，判断是否有el元素，有的话就判断是否有template，没有的话就巴拉巴拉，接着到beforeMount周期，做了什么忘了，接着到mounted周期，里面会有数据的修改，里面还有beforeUpdate和updated周期，紧接着到beforeDestroy周期，做了什么忘了，接着到Destroyed周期。。。。vue是自学，然后直接就做应用，所以对于生命周期的研究就过了一遍就完事了....(后面回去恶补了一下，看下方总结)</p>
</div> 

<div style="font-size: 15px">
    <p>面试官问 : vue在data里面定义了一个a，然后怎么在template里面显示，我暗想：这个简单，然后我答 : {{ a }}，面试官 ：“ 为什么可以直接这样就能显示 ?  vue数据绑定原理是什么 ? ” 我.... 面试官又问，react有了解吗 ? react和vue有什么区别，我答 : 没学过vue，但是好像都有用到虚拟DOM。。面试官 ：“ 讲一下虚拟DOM ”， 只能硬着头皮说 : “ 如果需要改变任何元素的状态，那么是先在虚拟DOM上进行改变，而不是直接改变真实的DOM。” 感觉没答对。（后面也看了一下源码，把这个双向绑定的原理理解了一下）</p>
</div>

<div style="font-size: 15px">
    <p>面试官 : “ 网站优化有什么手段 ? ” 我答 : “ 把css放在头部，js放底部 ”， “为什么要这样 ? ” “ 因为浏览器在渲染页面的时候，是按顺序执行下来，如果js脚本放在头部，由于网速过慢，js加载未完成时，页面会出现一片空白 ” “ 嗯，还有吗 ? ” “ 减少http请求，可以缓存一些重复使用的数据，比如在vue中使用vuex状态管理进行对数据的缓存”， “ 那在DOM节点方面如何进行优化 ?”
     我 : “....”</p>
</div> 

<div style="font-size: 15px">
    <p>面试官 : “ js常写吗 ? 我们来做个题 ”， 于是就直接手写算法...</p>
</div> 

## 算法
<div style="font-size: 15px">
    <p>面试官 : “ 给你一个对象，求有几层。 ” ， 我 : “ ???? ” 。面试官举了个例子</p>
</div>

```javascript
比如这个a中，就有四层。如何算出这四层

const a = {
    b : 1,
    c : function(),
    d : {
        e : 2,
        f : {
            g : 3,
            h : {
                i : 4
            }
        },
        j : {
            k : 5
        }
    }
}
```


<div style="font-size: 15px">
    <p>emmm，看第一眼，懵，再看一眼，就是考遍历，然后递归。再看一眼，不会做。。。</p>
</div> 

<div style="font-size: 15px">
    <p>我的思路是遍历第一层，然后如果第一层向下还有，就继续遍历， 然后传入需要遍历的obj，但是想了想总觉得有点不对劲。总之写啊写啊，差不多过了40多分钟，然后面试官看我没写出来，于是说要不给你出另外一道题吧~ ， 于是出了第二道题</p>
</div> 

---------------------
<div style="font-size: 15px">
    <p>面试官 : “ 学过数据结构吧，用两个栈实现队列。 ” ， 我 : “ ???? ” 。面试官 : “ 没听懂吗 ? ” ， “ 是的，能否举个例 ? ”</p>
</div>

```javascript
现在有个Q队列和栈A，栈B，栈只有两个方法，push()和pop(), 队列也只有两个方法，push()和pull()，队列的进和出都只能通过A和B的push和pop实现。

// 大概举个例子
const Q = {

    a = new A(),
    b = new B(),

    push() {
       
    },

    pull() {
       
    }
}
```

```javascript
队列 “ 先进先出 ” ， 栈 “ 先进后出 ”

// 我的代码是这样，就大概
const Q = {

    a = new A(),
    b = new B(),

    push(obj) {
        let s1 = this.a
        let s2 = this.b
        let len = Object.keys(obj).length  // 获得长度

        // push进A队列 
        for(let i = 0; i < len; i++)
        {
            s1.push(obj[i])                 //   c
                                            //   b
                                            //   a    
        }

        // push进B队列 
        for(let j = len-1; j >= 0 ; j--)
        {
            s2.push(obj[j)                  //   a
                                            //   b
                                            //   c  
        }
    },

    pull() {
       // 把栈B输出来就好了
       // 所以push顺序是a - b - c ，然后pull出来顺序是 a - b - c
    }
}

let q = new Q()
q.push('a, b, c')
q.pull()

```
写了差不多10来分钟，后面发现会错意，于是问了面试官，面试官又解释了一遍，然后接着做，差不多过了二十分钟，给面试官看了一下，面试官摇头，说只考虑每次只push一个，比如我第一次push(a), 第二次push(b)，然后再push(c)，接着我pull()就给我弹出a，再pull一次就给我弹出b。


原来是我会错意， 然后准备改一下代码，过了两分钟，面试官就说这次面试结束，让我骚等，我知道自己挂了，他走了之后，我就坐在那里把这道题做完，一分钟后，内推我的学姐出来，看我在做，就说了句 ：“ 不用写了~” , 我就知道我凉了，但是第二题我是做完了，只是运气不好，没能赶在他结束之前。只能说运气差了点。

和学姐聊了会天，然后出门赶第二场面试 - 京东。那时已经下午5 : 15分，京东面试在6 : 00。

---------------------

## 京东 “ 迟到 ”
``` bash
    只能说第一次面试，没把握住时间，也确实那时候很想进七牛云，所以想把题做出来，七牛云从3点面到5点，出来的时候只剩下45分钟，而我又太过于低估了周五下午下班时期的上海，还傻逼逼的打了个快车，师傅说了句 : 你搭地铁都比坐滴滴快。期间京东面试官打电话过来问我，能否及时到场，我说尽快，因为我确实不知道地铁转乘过去一个大概的时间，给个短时间怕不够然后食言，给个久一点时间又怕面试官觉得我太拖。
    下午6 : 17到面试地点。然后签了个到，马上进行了面试。那时候面试区已经没有人，只有我一个面试者在面试。
```
## 京东面试

<div style="font-size: 16px">
    <p>面试官拿着我的简历，看了一下， “ 你先自我介绍一下吧 ~ ” ，巴拉巴拉讲了一下，“ 你前端是用vue，那你和我说一下vue 的生命周期 ”，我就把在七牛云讲的又讲了一遍， “ 我看你用到了vuex， 你一般什么场景下会用 ? ”， 我回答 ：购物车，或者音乐播放器的时候会用到。　“ 那你了解vuex的原理和过程吗 ? ” “ 不知道 ”</p>
</div>

<div style="font-size: 16px">
    <p>“ Nginx配置说一下 ”， 我就巴拉巴拉说了一下，然后问我，原理是什么，我答 : 改变头，都是直接在php里改header，面试官又说 : “ 既然说到了nginx，跨域还有什么办法? ”， 我答 : “ nginx， jsonp，php改header，好像还有一个window.name ”， 然后面试官接着问 : “ jsonp跨域原理和过程知道吗 ? ” ， “ 不知道，只了解过nginx和php改header”</p>
</div>

<div style="font-size: 16px">
    <p>面试官接着问 ：“ js闭包了解吗 ? ” ， 我答 : “ 我理解的闭包就是能够读取其他函数内部变量的函数。”， 比如巴拉巴拉举了个例子。 又问 : “ js原型链了解吗 ? ”，我说了一下我对js原型链的理解，然后又问我 : “ js的事件流” ， 我答 : 事件捕获阶段，处于目标阶段，事件冒泡阶段，然后举了个例子，大概讲了一下，接着面试官又问，“ webpack 用过吗 ? ”，我说 : “ 我的vue是基于webpack创建的vue-cli，然后webpack有了解过一点”，然后把自己对webpack的理解讲了一下。</p>
</div>

<div style="font-size: 16px">
    <p>面试官 : “ 既然讲到了webpack，那么少不了模块，讲一下js的模块化。 ”， 我答 : “ js的模块化巴拉巴拉，然后有CommonJS规范和AMD规范。node.js就是commonJS规范，它有一个require方法引入模块，比如require('math')，然后执行math.add(2, 3)，在服务器端操作很快，因为引入的模块是存在本地磁盘中，所以引入的时间就是访问本地磁盘的时间。但是在浏览器端，如果网速不好，那么页面会进入“假死”状态。AMD规范也有require()，但是有一个callback回调函数，在引入math.js之后，再去执行这个math.add，这样浏览器不会处于假死状态。”</p>
</div>

<div style="font-size: 16px">
    <p>面试官继续问 : “ JS 的 Promise 你怎么理解，在.then里面如何怎样用到promise ? (我忘记是不是这样问的了~) ”，就讲了promise的概念， 面试官好像不满意，然后又问我 : “ js的继承 ”， 这个我看过，但是我忘记了，然后我只能摇头说，不知道。</p>
</div>

<div style="font-size: 16px">
    <p>面试官 : “ 你是软件工程专业，数据结构学过吧，说一下栈和堆，用栈去实现一个堆 (我忘记是怎么问的，但是考察的就是栈和堆) ” ， 我就说栈是先进后出，然后忘了。。。。
</div>

<div style="font-size: 16px">
    <p>“ 小程序了解过吗 ? ”， 我答 : 有了解过，但是只做了静态页面，做了一点点没做完，然后把自己做的小程序给他看了一下，面试官接着问 : “ git平常用的多吗 ? ” ， 我答 : “ 还好，平常简单的操作，创仓库，传代码，拉代码等 ”， 面试官接着问 : “ git merge 和 git rebase 有什么区别 ? ”，这个学姐之前有叫我看，幸好有去了解了一下，然后大概讲了一下，接着问我 : “ 平常怎么学习前端 ? ”， 我说 : “ 看书，有时候去掘金，知乎，cnode，v2ex逛逛，看看一些大佬写的博客文章等 ~ ”</p>
</div>

<div style="font-size: 16px">
    <p> “ 你还有什么问的吗 ? ” ， 我就问了我的问题， “ 那今天的面试就先到这，面试结果快的话今晚就会有通知，慢点的话明天会出 ” , 我道了个谢，说了声辛苦你了，然后就走了，出了面试区，我还有点小高兴，因为居然没有考算法，接着就去官网查了一下进度， 显示初试未通过，我就知道凉了~</p>
</div>

## 再说一句 
<div style="font-size: 18px">
    <p>面试迟到是大忌， 个人觉得面京东感觉一般般，也不能说好，但我觉得也不算很糟糕，挂的原因我觉得 50%是因为迟到，50%在于自身。当然自己也有很多不足，气喘吁吁的到面试签到就进去面试，并且迟到给面试官留下一个“不守时”的坏印象，原因在于我对时间的拿捏不够好，只能说运气有点差了~</p>
</div>

------------------

# 总结一下

## 我自己复习的知识点有 : 
<ul style="font-size: 16px">
    <li>JS 闭包， 原型链， 事件模型， 事件代理， this对象</li>
    <li>git rebase 和 git merge</li>
    <li>HTTP状态码， HTTP和HTTPS的区别</li>
    <li>DOCTYPE作用，严格模式和混杂模式</li>
    <li>webpack， 跨域， 同源限制</li>
    <li>web安全和防护原理</li>
    <li>JS模块化， JS Promise， JSON的浅复制和深复制</li>
    <li>css sprite， 盒模型， position， transform</li>
    <li>三次握手， 四次握手</li>
    <li>浏览器渲染的原理和过程， 从浏览器输入url到页面显示过程</li>
    <li>JS的apply 和 call</li>
    <li>vue的生命周期 / vue的响应式系统原理（数据双向绑定原理）</li>
    <li>...</li>
</ul>

## 我有话要说
``` base
    面一是对基础的考察，一定要把基础打扎实，我就是js基础不够牢固扎实，其次要把操作系统，计算机网络，以及数据结构学好，特别是数据结构，算法是必考的，并且考递归较多。面试的时候，一定千万不能迟到，记住了！！！面试过程不要紧张，切记不要不懂装懂，不懂就说“没了解那么深” ，“不太清楚”等，这种话你应该会说。对了，简历的话，一定要简单明了，不要长长的一段文字，尽量一页纸。如何检测你的简历，把你做好的简历海投，如果有结果，说明简历还是能看，如果没有结果，说明简历不行，再改。
```

## 我理解的Vue的生命周期
<ol>
    <li>在new vue()之后，Vue会调用_init函数进行初始化，初始化生命周期 、 props 、 watch 、 data 等</li>
    <li>初始化之后到beforeCreate，在beforeCreate 和 Created 之间进行一个数据观测</li>
    <li>在Created 与 beforeMounted 之间，先判断有无el ，因为在我们main.js里面，有一个class Vue 里存在一个 el : #app ，所以判断有无el，有接着判断有无template，有则需进行编译步骤，将其作为模板编译成render函数，无template就将外部的html作为模板编译，无el就停止编译，暂时停止了生命周期，直到$mount(el)挂载组件。</li>
    <li>beforeMounted 和 Mounted 之间，个人理解是因为template比html优先级高，所以最后一般会存在一个外部html模板被Vue实例本身配置的template所“替换”</li>
    <li>beforeUpdated 和 updated 时，当数据改变时，会通过 setter -> watcher -> update 的流程来修改对应的试图，最后通过patch机制，将新的Vnode和旧的Vnode一起传入patch进行比较，经过diff算法算出差异，最后把这些差异的DOM进行修改。</li>
    <li>beforeDestory 和 destoryed 之间，destoryed在vue实例销毁后调用。</li>
 </ol>
 
 ### [ 编译过程 ]
 <div>
    <p>compile 编译可分为三个阶段 parse 、 optimise 、 generate ，最终得到render function() </p>
    <ol>
        <li>parse 会用正则等方式去解析template模板中的指令 、 style 、 class等数据，然后形成一颗AST语法抽象树</li>
        <li>optimise 主要作用就是标记static静态节点， 这是Vue在编译过程中的一处优化，后面当update更新界面时，会有一个patch过程，diff算法会直接跳过静态节点，从而减少了比较的过程，优化pathc的性能。</li>
        <li>generate是将AST转化为render function 字符串中的过程，得到结果是render 的字符串以及static RenderFns字符串</li>
        
    </ol>
</div>

### 数据双向绑定原理-响应式系统的基本原理
``` bash
    这个面试过程必问，于是在掘金上买了本小册，里面讲到了这方面的知识点，然后直接理解梳理了一遍。下面就顺道
```

##### Object.defineProperty(obj, prop, descriptor) ，vue.js就是基于它实现响应式系统的。
> 直接代码理解吧

```javascript
    1 : 定义一个 @class Vue
    
    class Vue{
        constructor(options){
        this._data = options.data
            ...
            ...
        // 调用observer()
        observer(this._data)
        
        // 新建一个Watcher
        new Watcher()
        
        }
        
        console.log( '' )
   }
   
   
   2 : observer  ,  需传入一个value(需要响应式化的对象)，通过变量所有属性对该对象的每一属性都做 defineReactive处理
   
    observer(value)
    {
        if(!value || (typeof value != 'object' ))
        {
            return
        }
        
        Object.keys(value).forEach((key) => {
            defineReactive(value, key, value[key])
        })
        
    }
    
    
    3 : 收集依赖，实现一个订阅者Dep类，主要存放Watcher对象的数组
    
    class Dep{
    
        constructor() {
            this.subs = [] 
        }
        
        addSub (sub) {
            this.subs.push(sub)     // 在subs中添加一个watcher对象
        }
        
        notify(){
            this.subs.forEach((sub) => {
                 sub.update()       // 通知所有的watcher对象更新视图
            })
        }
    }
    
    4 : 实现一个Watcher
    
    class Watcher {
       
        constructor(){
            Dep.target = this
        }
        
        update(){
            console.log('视图更新')
        }
        
    }
    
    5 : defineReactive 函数的实现
    
    function defineReactive(obj, key, value)
    {
        const dep = new Dep()
        
        Object.defineProperty(obj, key, {
            enumerable : true,          // 属性是否可枚举
            configurable : true,        // 属性是否可修改或删除
            
            get : function ReactiveGetter () {
                dep.addSub(dep.target)          // 将new出来的watcher对象加入到dep的subs数组中
                return value
            },
            
            set : function ReactiveSetter (newValue) {
                if(newValue  ===  value)
                {
                    dep.notify()            // 通知所有的watcher更新视图
                }   
            }
            
       })
```

#### 大概讲下 ?
其实最重要的就是Object.defineProperty，因为vue就是基于它实现响应式，也就是数据双向绑定的。经过defineReactive方法处理之后，obj的key属性在[读]的时候会触发reactiveGetter函数去收集依赖，加入到订阅者的subs数组里面，subs数组存的就是每一个new出来的watcher对象，之后在key属性被[写]的时候会触发reactiveSetter方法，去通知更新视图。
