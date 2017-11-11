#AMD <br>
1.AMD就是Asynchronous Module Definition，中文名是异步模块定义的意思。<br>
2.AMD解决两个问题：解决依赖、异步加载<br>
3.requireJs语法<br>
    定义：define(id,dependencies,factory);
                id:可选参数，用来定义模块的标识，如果没有，则默认是脚本的文件名（去掉扩展名）
                dependencies:当前模块依赖的其他模块名称数组
                factory:工厂方法，模块初始化的函数或者对象。
    加载：require([dependencies],function(){});
                  dependencies:数组，依赖的模块
                  function:回调函数，当模块加载成功后，在函数中调用这些模块。
#CMD <br>
1.CMD即Common Module Definition通用模块定义
2.seajs和requirejs一样，只不过在模块定义方式和加载的时候不一样
3.seajs语法<br>
    定义：define(function(require,exports,module){});
                require:是一个方法，接受模块标识作为唯一参数，用来获取其他模块提供的接口。require(id)
                exports:是一个对象，用来向外提供模块接口
                module:是一个对象，用来批量输出模块的属性和方法
    加载：seajs.use(['1.js','2.js',...],function(mod1,mod2,...){})
#AMD和CMD区别
1.AMD推荐依赖前置，在定义模块的时候就要声明其依赖的模块.用户体验好，没有延迟，依赖模块提前执行了。
2.CMD推荐就近依赖，只有再用到某个模块的时候去require。性能好，只有去使用的时候才去执行。
