@echo off
if "%1"=="" (
	:: 请求指定GOPATH目录
	set /p goPath="Set GOPATH:"
) else (
	set goPath=%1
)

if "%2"=="" (
	:: 保持脚本路径
	set batPath=%cd%
) else (
	set batPath=%2
)

echo GOPATH=%goPath%

:: 进入GOPATH目录
cd /D %goPath%
:: 判断是否存在src\golang.org\x目录,不存在则创建
set xPath=%goPath%\src\golang.org\x
if NOT EXIST %xPath% (
	mkdir %xPath%
)
:: 进入src\golang.org\x目录
cd %xPath%

:: 请求输入所需安装的包名
set /p pkgName="Input PKG NAME:"

:: 通过git clone 获取包源码
if NOT EXIST %xPath%\%pkgName% (
	:: 不存在则克隆
	git clone https://github.com/golang/%pkgName%
) else (
	:: 已经存在则更新
	cd %xPath%\%pkgName%\
	git pull https://github.com/golang/%pkgName%
)

call %batPath%\goget.bat %goPath% %batPath%

