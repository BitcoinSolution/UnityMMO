# UnityMMO
There are a lot of things that are not good to try on a work project (such as ECS), so there is this project, I plan to use my spare time to make a 3D-MMO game from scratch, although most of the functions have been more or less touched, but I want to change the approach, otherwise it will not be fun. The front end of the gameplay system with c#, the interface with lua development. The back end is skynet.
detailed design and progress see：[Wiki](https://github.com/liuhaopen/UnityMMO/wiki "Wiki")  

# Usage
The Clonebook Project: git clone https://github.com/liuhaopen/UnityMMO.git --recurse  
front end:  
After downloading it, the whole directory is the Unity project directory, open it with Unity, run main.unity to enter the login interface of the game.  
Note: Because the game resources are too big and change frequently (each version of the resources will be saved in the .git folder, clone will take a long time), so put it in another project, you can find it in [UnityMMO-Resource](https://github.com/liuhaopen/UnityMMO- Resource/tree/master/Assets/AssetBundleRes "UnityMMO-Resource") Download the files and copy Assets/AssetBundleRes and its meta files to the Assets directory of the project (Note: Some plugins are not uploaded because of copyright issues, see the buy link for download-page). plug-ins were not uploaded due to copyright issues, from which the download-page see the purchase link).  
Backend :  
Reference Projects：[SkynetMMO](https://github.com/liuhaopen/SkynetMMO "SkynetMMO")  

# Status & Prerequisites
```
Unity version: 2019.2.0f1
Platforms    : 
client for Windows Android IOS;  
server only for Linux;
```

# Recent GIF
20.03.08：把服务器代码分隔到另外的 git 项目
19.07.03：初步实现了自动寻路去找 npc 对话和打怪两种任务：    
![image](https://github.com/liuhaopen/ReadmeResources/blob/master/UnityMMO/auto_talk_and_fight.gif)     
19.07.10：增加一个副本场景：    
![image](https://github.com/liuhaopen/ReadmeResources/blob/master/UnityMMO/change_scene.gif)     
19.07.31：初步完成背包和 GM 系统      
19.08.11：初步完成基于 action 组件的技能系统,见 Server/lualib/Action及 FightMgr,Hurt 和 PickTarget.lua          
19.08.13：完成复活流程      
19.08.28：最近经常在手机上测试，优化了一波：摄像机操作，资源预加载，对象池，和使用了 AutoLOD 插件为各场景节点生成了两级简模（其实很多模型在最远处时是可以用一个面片替代的，就是做成公告板永远面向摄像机，但没美术资源就算了），树的话删了不少上万三角面的了。灯光烘培改成用 Distance ShadowMask,近处实时阴影远处贴图。暂时可以在我的垃圾手机流畅运行了。    
19.09.07：后端增加 buff:火，毒，冰冻，晕眩，吸血，扣属性(防御、攻击等)，沉默。详见 BuffActions.lua。前端目前只加了吸血和晕眩的效果。  
19.09.18：增加各平台的图片格式管理工具，针对不同用途的图片使用不同深度，比如安卓平台时 ui 文件夹里的图片用 ETC2_RGBA8，模型图片用 ETC_RGB8 等等，在 iOS 就用 ASTC 系列的格式。详细见 unity 编辑器菜单：TextureFormatter   
19.10.21：最近忙工作上的事，而且想要憋个大招，所以未来一个月进度会慢下来，先搞下小 ui 界面。  
