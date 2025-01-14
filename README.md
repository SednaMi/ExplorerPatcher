# ExplorerPatcher Custom Libraries Chainloader

ExplorerPatcher has a simple, built-in mechanism that allows users to load their own DLL into `explorer.exe` right after ExplorerPatcher finishes initializing its hooks. Interested users should place a DLL called `ep_extra.dll` in `C:\Windows`. When ExplorerPatcher finishes its setup, it loads the `ep_extra.dll` library and calls the `ep_extra_EntryPoint` function. Although this is very useful so that users can load their custom code, it is quite limited at the moment, as it loads just one DLL.

This project is a solution to this issue. A chainloader is implemented here, that looks for other modules matching the `ep_extra_*.dll` pattern in `C:\Windows` as well, and loads them one after the other.

ExplorerPatcher 自定义库链式加载器
ExplorerPatcher 具有一个简单的内置机制，允许用户在 ExplorerPatcher 完成其钩子初始化后，将自己的 DLL 加载到 explorer.exe 中。对此感兴趣的用户应该将一个名为 ep_extra.dll 的 DLL 放置在 C:\Windows 目录中。当 ExplorerPatcher 完成其设置时，它会加载 ep_extra.dll 库并调用 ep_extra_EntryPoint 函数。虽然这对于用户加载自定义代码非常有用，但目前它的限制在于只加载一个 DLL。

本项目解决了这个问题。在这里实现了一个链式加载器，它在 C:\Windows中查找与 ep_extra_*.dll 模式匹配的其他模块，并依次加载它们。