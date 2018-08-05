# 封面
1、封面信息

	第一行代码
	Android
	第 2 版
	郭霖·著

	人民邮电出版社 
	北京

	2016.12北京第2次印刷 定价：79元
2、内容提要

	Android学习第一书；系统全面、循序渐进；必备知识、经验和技巧；使用全新的开发工具Android Studio；
	对Material Design、运行时权限、Gradle、RecyclerView、百分比布局、OkHttp、Lamda表达式等全新知识点进行详细讲解；
	通俗易懂、由浅入深；初学者入门必备、开发者进阶首选。

	关键词：Android学习第一书；系统全面；Android Studio；全新知识点；入门必备、开发首选；
# 前言
	写一本好书的难度并不亚于开发一款好的应用程序。
	长期坚持在CSDN发表技术博文，得到大量网友认可，也积累了一些人气。荣幸地是，人民邮电出版社图灵公司的前副总编辑陈冰老师联系写书。

	基于Android 7.0系统  Enjoy it!
	
# 致谢

# 目录

#1 开始启程——你的第一行Android代码
	市场占有率最高的移动OS
	发展史：
		2003年10月，Andy Rubin等人创办Android公司；
		2005年8月，谷歌收购（仅成立了22个月，不到2年）；
		2008年，推出第一个版本……知识产权问题；
		两年后，Android就超过霸占市场逾十年的诺基亚，成为全球第一大智能手机操作系统。
		而近几年，国内的手机厂商也大放异彩，小米、华为、魅族等新兴品牌都推出了不错的Android手机。
##1.1 Android简介
	二十几个版本、完整的生态系统。	
###1.1.1 系统架构
	四层架构：
		Linux内核层：为各种硬件提供底层驱动；
		系统运行库层：通过C/C++库提供主要特性支持，运行时库（Dalvik虚拟机）；
		应用框架层：提供各种API；
		应用层：应用程序开发。
###1.1.2 已发布版本
	版本号、系统代号、API、市场占有率
	2016年以前，4.0以上的系统已占据超过98%的市场份额，所以面向4.0以上的系统开发，不再去兼容2.x系统了。
###1.1.3 应用特色
	四大组件：活动（Activity）、服务（Service）、广播接收器（Broadcast Receiver）、内容提供器（Content Provider）；
	丰富的系统控件：还可以自定义控件；
	SQLite数据库：轻量级、运算快的嵌入式关系型数据库；
	强大的多媒体：音乐、视频、录音、拍照、闹铃……
	地理位置定位：和PC相比，GPS+地图-》LBS领域潜力无限。
##1.2 搭建开发环境
###1.2.1 准备工具
	JDK、Android SDK、Android Studio
###1.2.2 下载安装
	Android官网或百度网盘
##1.3 第一个Android项目
###1.3.1 创建HelloWorld项目
	创建流程、注意事项
###1.3.2 启动模拟器
	版本选择
###1.3.3 运行HelloWorld
	查看效果、收获喜悦
###1.3.4 分析程序
	项目结构:Android模式切换到Project模式。
		.gradle和.idea
		app 代码、资源（工作重点）
			build 包含编译时自动生成的文件
			libs 添加第三方jar包
			androidTest 编写测试用例
			java 编写java代码
			res 图片、布局、字符串等资源目录
				drawable
				layout
				mipmap-...
				values
			AndroidManifest.xml 四大组件注册、权限声明
			test 编写Unit Test用例
			.gitignore
			app.iml
			build.gradle 各种闭包，配置项目构建的各种属性
			proguard-rules.pro 指定代码混淆规则，保护源码
			
		build
		gradle
		.gitignore
		build.gradle 代码托管库jcenter、声明Gradle插件
		gradle.properties
		gradlew和gradlew.bat
		HelloWorld.iml
		local.properties 配置Android SDK路径
		settings.gradle
###1.3.5 详解项目中的资源
	res 图片、布局、字符串等资源目录
				drawable
				layout
				mipmap-...
				values
###1.3.6 详解build.gradle文件
	Gradle构建工具
##1.4 日志工具
###1.4.1 使用Log
	Log.v() verbose 冗长的，打印琐碎、意义最小的日志信息
	Log.d() debug
	Log.i() info
	Log.w() warn
	Log.e() error
###1.4.2 为什么使用Log而不使用System.out
	System.out的缺点，Log可以解决的问题：
		日志打印不可控制、打印时间无法确定、不能添加过滤器、日志没有级别区分
###1.5 小结与点评
	很充实，甚至有点沾沾自喜：
		首先对Android系统有了更加充足的认识；
		然后成功搭建了开发环境；
		接着创建了第一个Android项目，并对其目录结构和执行过程有了一定认识；
		最后学习了日志工具。
	不过也别太过于满足，还需要付出更多努力。

#2 探究活动
	制定后面的学习路线：界面（看得见，感兴趣）--》出色的程序算法、架构（不易看见、有难度）
##2.1 活动是什么（四大组件之一，UI）
	活动（Activity）是最容易吸引用户的地方，它是一种可以【包含用户界面】的【组件】，主要【用于和用户交互】。
##2.2 活动的基本用法
	手动创建活动：流程
###2.2.1 手动创建活动
	创建项目-》切换到Project模式-》创建Empty Activity
###2.2.2 创建和加载布局
	res-》创建layout目录-》创建布局文件（Layout resource file）-》编辑布局-》加载布局
	编辑布局：
		线性布局：LinearLayout 
			orientation="vertical/horizontal"
			layout_width="match_parent/wrap_content"
			layout_height"match_parent/wrap_content"
		文本控件：TextView
			id="@+id/text_view"
			layout_width="wrap_parent"
			layout_height"wrap_content"
		按钮控件：Button
			id="@+id/button_1"
			layout_width="match_parent"
			layout_height"wrap_content"
			text="Button 1"
###2.2.3 活动注册
	在AndroidManifest.xml文件中注册-》查看运行效果
		<?xml version="1.0" encoding="utf-8"?>
		<manifest xmlns:android="http://schemas.android.com/apk/res/android"
	    package="com.jc.uibestpractice">
	
		    <application
		        android:allowBackup="true"
		        android:icon="@mipmap/ic_launcher"
		        android:label="@string/app_name"
		        android:roundIcon="@mipmap/ic_launcher_round"
		        android:supportsRtl="true"
		        android:theme="@style/AppTheme">
		        <activity android:name=".MainActivity">
		            <intent-filter>
		                <action android:name="android.intent.action.MAIN" />
		
		                <category android:name="android.intent.category.LAUNCHER" />
		            </intent-filter>
		        </activity>
		    </application>
		</manifest>
###2.2.4 使用Toast
	// 按钮控件获取（View是控件的顶层设计，findViewById就是通过id查找控件）
	final Button button1 = findViewById(R.id.button_1);
    // 点击事件监听
    button1.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            // 注意：监听器里面的this指的不是活动上下文，要用...Activity.this
			String msg = "you clicked:"+button1.getText().toString();
			// 提醒用户一些短消息，过会儿自动消失
            Toast.makeText(FirstActivity.this,msg,Toast.LENGTH_SHORT).show();
        }
    });
###2.2.5 使用Menu
	理清过程……
###2.2.6 销毁一个活动
	finish();
##2.3 使用Intent(意图)
	怎样在主活动和其他活动之间跳转？用Intent实现
###2.3.1 使用显示Intent
	Intent是各组件之间进行交互的一种重要方式：
		不仅可以指明当前组件想要执行的动作；
		还可以在组件之间传递数据；
	用于启动活动、启动服务以及发送广播等场景。
	分为显示Intent和隐式Intent。

	// 多个构造函数的重载（构造意图）
	new Intent(
		Context packageContext,// 启动活动的上下文
		Class<?> cls// 想要启动的目标活动
	);
	// 
	startActivity(Intent intent);// 用于启动目标活动
###2.3.2 使用隐式Intent
	含蓄：不明确指出启动哪个活动，而是指定一系列更为抽象的action和category等信息，
	然后交由系统去分析这个Intent，并帮我们找出【合适的活动】去启动。

	合适的活动？同时匹配上Intent指定的一个action和多个category
		<activity android:name=".SecondActivity">

            <intent-filter>
                <action android:name="com.jc.activitytest.ACTION_START" />

                <category android:name="android.intent.category.DEFAULT" />
                <category android:name="com.jc.activitytest.MY_CATEGORY" />

            </intent-filter>
        </activity>

	// 构造意图
	Intent intent = new Intent("com.jc.activitytest.ACTION_START");
	intent.addCategory("android.intent.category.DEFAULT");// 默认的category，系统自动添加到Intent中
	intent.addCategory("com.jc.activitytest.MY_CATEGORY");// 自定义category
	startActivity(intent);
###2.3.3 更多隐式Intent的用法
展示一个网页

	// 不仅可以启动自己程序内的活动，还可以启动其他程序的活动（应用功能共享）
	// 展示一个网页，只需要调用系统浏览器打开它即可
	// ACTION_VIEW：系统内置动作，其常量值为android.intent.action.VIEW
	Intent intent = new Intent(Intent.ACTION_VIEW);
	// Uri.parse(String uriString):将网址字符串解析成一个Uri对象
	// intent.setData(Uri data)
	intent.setData(Uri.parse("http://www.baidu.com"));
	startActivity(intent);

	// 更精确地指定当前活动能响应什么类型的数据？配置<data>标签的各种属性
	<data 
		android:scheme="http"// 协议
		android:host="www.baidu.com"// 主机名
		android:port=""// 端口
		android:path=""// 端口之后的部分
		android:mineType=""// 指定可以处理的数据类型，允许通配符
	/>
调用系统拨号界面

	// FirstActivity.java 按钮点击事件
	Intent intent = new Intent(Intent.ACTION_DIAL);
	intent.setData(Uri.parse("tel:10086"));
	startActivity(intent);

	// AndroidManifest.xml 配置注册活动
	<activity android:name=".ThirdActivity">
        <intent-filter>
            <action android:name="android.intent.action.VIEW" />
            <category android:name="android.intent.category.DEFAULT" />
            <!-- 系统浏览器打开网页 -->
            <data android:scheme="http" />
        </intent-filter>
        <intent-filter>
            <action android:name="android.intent.action.DIAL" />
            <category android:name="android.intent.category.DEFAULT" />
            <!-- 系统拨号 -->
            <data android:scheme="tel" />
        </intent-filter>
    </activity>
###2.3.4 向下一个活动传递数据
	前面都是简单的使用Intent【启动活动】，其实Intent还可以在启动活动的时候【传递数据】。
	
	// FirstActivity.java 传递字符串数据
	intent.putExtra("extra_data","hello...");

	// SecondActivity.java 取出数据
	@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

		// 获取用于启动SecondActivity的Intent
		Intent intent = getIntent();
		String data = intent.getStringExtra("extra_data");
	}
###2.3.5 返回数据给上一个活动
编码流程：  
=》ForResult(intent,1);// 期望返回结果  
=》setResult(RESULT_OK,intent);// 两种触发条件  
=》重写onActivityResult方法// 判断数据来源，处理返回结果  

	// FirstActivity.java ...ForResult(intent,1); 期望 返回数据
	Intent intent = new Intent(FirstActivity.this,SecondActivity.class);
	// 也可以用于启动活动，并期望在活动销毁的时候能够返回结果给上一个活动
	// 第一个参数是intent,第二个参数是requestCode
    startActivityForResult(intent,1);

	// SecondActivity.java setResult(RESULT_OK/RESULT_CANCELED,intent); 点击某按钮 返回数据
	// 用按钮触发返回数据操作
	Button button2 = findViewById(R.id.button_2);
    button2.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            // 构建一个Intent,它用于传递数据，没有指定任何“意图”
            Intent intent = new Intent();
            intent.putExtra("data_return","return data...");
            // 专门用于向上一个活动返回数据
            // 第一个参数用于向上一个活动返回结果，一般使用RESULT_OK(=-1)或RESULT_CANCELED(=0)
            setResult(RESULT_OK,intent);
            // 调用finish销毁当前活动
            finish();
        }
    });

	// SecondActivity.java 重写onBackPressed 触发Back键 返回数据
	@Override
    public void onBackPressed() {
        // super.onBackPressed();
        Intent intent = new Intent();
        intent.putExtra("data_return","return data...");
        setResult(RESULT_OK,intent);
        finish();
    }

	// FirstActivity.java 重写onActivityResult 监听 返回结果
	/**
     * 监听结果返回
     * @param requestCode 启动活动时传入的请求码，判断数据来源（哪个活动）
     * @param resultCode 返回数据时传入的处理结果，判断处理结果是否成功（RESULT_OK,失败或取消则是RESULT_CANCELED）
     * @param intent 携带返回数据的意图
     */
	@Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
        // super.onActivityResult(requestCode, resultCode, data);
        if(intent != null){// 判断是否返回数据
            switch (requestCode){// 请求码
	            case 1:
	                if(resultCode == RESULT_OK ){// 结果码
	                    String returnedData = data.getStringExtra("data_return");
	                }
	                break;
	            default:
	        }
        }    
    }
##2.4 活动的生命周期
	合理管理应用资源
###2.4.1 返回栈
	任务（Task）：一组放在栈里的【活动的集合】。
	返回栈（Return Stack）:【后进先出】的数据结构
		启动新的活动，【入栈】，处于栈顶
		Back键或finish(),销毁活动，【出栈】，前一个入栈的活动处于栈顶
	如何管理活动入栈出栈？返回栈工作原理
###2.4.2 活动状态
	4种状态——能够熟练判断当前活动处于哪个状态
		运行状态：活动处于栈顶（系统最不愿意回收的就是处于运行状态的活动，因为这会带来非常差的用户体验）
		暂停状态：不处于栈顶，但仍然可见（比如：对话框下面的活动。系统也不愿意回收这种存活着的活动，除非内存极低的情况下）
		停止状态：不处于栈顶，且完全不可见
		销毁状态：从返回栈中移除
###2.4.3 活动的生存期
7个回调方法(钩子函数)——覆盖活动生命周期的每一个环节

		
三种生存期——除onRestart()方法外，其他都是两两相对的

		完整生存期
			onCreate()-完成各种初始化操作
			onDestroy()-完成释放内存的操作
		可见生存期：活动对用户总是【可见的】，有可能无法和用户交互
			onStart()-加载资源
			onStop()-释放资源，节约内存
		前台生存期：活动总是处于【运行状态的】，可以和用户进行交互
			onResume()-继续，重新开始
			onPause()-暂停
活动周期示意图

![a](C:\\Users\\38415\Desktop\\Android知识截图\\01-Activity生命周期-英文版-详细.png)
	