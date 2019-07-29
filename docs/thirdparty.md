* 在OpenAuth中设计表单，注意表单中的控件名称。

* 在OpenAuth中设计流程，制定相关的工作流程，并在每个流程节点配置回调URL路径，在流程运行时，后台会以WEBAPI POST的方式回调指定的接口地址；

* 三方已有系统界面，提交表单时，调用创建流程实例接口：http://localhost:52789/api/FlowInstances/Add，在OpenAuth中创建一条新的流程实例； 接口参数如下：

```
    {
        schemeId:'cdd8191e-6a99-4d66-aac0-fae52c0f2232', //流程模板中已存在的模板ID
        schemeCode:'', //与流程模板ID二者选一个即可
        frmData:'{\"TOOLS\":\"电脑\",\"NUMBERS\":\"1\"}', //严格按照第一步中表单规则
        code:'1563811467051',
        customName:'三方创建的新物品领用',
    }
```

* 用户正常在OpenAuth中执行流程，三方系统既可以获得流程执行的反馈；