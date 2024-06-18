# 【命令行延暂停新10年】

<mark>家庭版不适用</mark>

> ### 方法一

用命令直接禁止更新的。CMD直接运行下列命令，禁止更新10年，
3650改为1可恢复更新。

`reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings" /v FlightSettingsMaxpauseDays /t reg_dword /d 3650 /f`

运行后  还要去手动设置延迟更新的时间   这个时间就从7天  变成了N周

再windows更新选项那里点高级选项  然后下拉到暂停更新  自己选时间就行了

> ### 方法二

1. 运行gpedit.msc—计算机配置—管理模板—Windows组件—Windows更新—指定 Intranet Microsoft 更新服务位置—启用

2. 然后在下面的三个输入框（Intranet更新、统计、备用下载服务地址）均填入 127.0.0.1，如上图所示

3. 运行gpedit.msc—计算机配置—管理模板—Windows组件—Windows更新—配置自动更新—禁用

4. 运行compmgmt.msc—系统工具—任务计划程序—任务计划程序库—Microsoft—Windows—WindowsUpdate—禁用所有任务

5. 再找到UpdateOrchestrator，同样禁用它的所有任务（不过失败了，提示：你所使用的用户账户没有禁用此任务的权限，于是作罢）

6. 运行services.msc—Windows Update—停止并禁用—右键属性恢复选项卡—三次失败下拉框均改为无操作

7. 运行services.msc—Windows Update Medic Service—这里禁用时会提示拒绝访问，那改它的注册表就行了
   `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WaaSMedicSvc`
   双击右侧Start值，修改其值为4（十六进制不变）（原值为3，表示手动）
   双击右侧FailureActions值，修改它的二进制数据：将0010、0018行的左起第5个数值由原来的01改为00<br/>

补充：该服务是Win10升级到1809版后新增的，作为Windows Update服务的保镖，它开机会自动运行Windows Update服务