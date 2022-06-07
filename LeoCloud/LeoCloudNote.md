# LeoCloud

## 1.安装MySql Linux版本

[Linux下MySQL的安装与使用](https://docs.qq.com/pdf/DVWVOR2pMa0VJTmlV)





## 2.net cli 搭建项目

查看sdk列表

~~~ powershell
dotnet --list-sdks
~~~



创建解决方案,创建初始web项目

~~~ powershell
dotnet new globaljson --sdk-version 6.0.203 --output MyWebProject/Web
dotnet new web --no-https --output MyWebProject/Web --framework net6.0
dotnet new sln -o MyWebProject
dotnet sln MyWebProject add MyWebProject/Web
~~~



向项目中添加类库

~~~ powershell
dotnet new classlib -o MyWebProject/ApplicationCore --framework net6.0
dotnet sln MyWebProject add MyWebProject/ApplicationCore
~~~



添加测试项目

~~~ powershell
dotnet new xunit -o MyWebProject/Tests/ApplicationCore.Tests --framework net6.0
dotnet sln add Tests/ApplicationCore.Tests
dotnet add Tests/ApplicationCore.Tests reference ApplicationCore
~~~





