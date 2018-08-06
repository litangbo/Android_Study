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
	不过也别太过于满足，还需要付出更多努力。适当休息，继续前进！

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
7个回调方法(钩子函数)——覆盖活动生命周期的每一个环节，什么时候调用？

	onCreate()-活动在第一次被创建的时候调用。完成各种初始化操作，比如加载布局、绑定事件等。
	onStart()-在活动由不可见变为可见的时候调用。
	onResume()-在活动准备和用户交互的时候调用。此时活动一定位于栈顶，并处于运行状态。
	onPause()-在启动或恢复另一个活动的时候调用。	
	onStop()-在活动完全不可见的时候调用。和onPause()主要区别在于，如果启动的新活动是一个对话框式的活动，那么onPause()会执行，onStop()不会执行。
	onDestroy()-活动销毁前调用，之后活动变为销毁状态	。
	onRestart()-活动从停止变为运行状态之前调用，即活动被重新启动了。
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
活动生命周期的示意图

![活动生命周期的示意图](https://raw.githubusercontent.com/litangbo/Android_Study/master/01-Activity%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F-%E8%8B%B1%E6%96%87%E7%89%88-%E8%AF%A6%E7%BB%86.png)

###2.4.4 体验活动的生命周期
	ActivityLifeCycleTest
		MainActivity:Log.v()
		NormalActivity
		DialogActivity
###2.4.5 活动被回收了怎么办
	onSaveInstanceState(Bundle outState)
	...
##2.5 活动的启动模式
	四种——通过<activity>标签的android:launchMode属性配置启动模式
		standard
		singleTop
		singleTask
		singleInstance
###2.5.1 standard
	体会效果...
###2.5.2 singleTop
	体会效果...
###2.5.3 singleTask
	体会效果...
###2.5.4 singleInstance
	体会效果...
##2.6 活动的最佳实践
###2.6.1 当前在哪一个活动
	public class BaseActivity extends AppCompatActivity {
		// TODO
	}
###2.6.2 随时随地退出程序
	public class ActivityCollector {
		// TODO
	}
###2.6.3 启动活动的最佳写法
	// FirstActivity向SecondActivity传入两个字符串参数
	// SecondActivity.java
	public static void actionStart(Context context,String data1,String data2) {
		// TODO
	}
##2.7 小结与点评
	有点疲惫，但内心仍充满喜悦：
		活动所有重要的知识点
			从活动的基本用法
			到启动活动和传递数据的方式
			再到活动的生命周期
			以及活动的启动模式
		活动的最佳实践技巧
	在活动方面算一个小高手了，但后面需要学习的还很多，要做好心理准备。
	适当休息，继续前进！

#3 UI开发
	软件也要拼脸蛋
	界面设计和功能开发同样重要
##3.1 如何编写程序界面
	两种方式
		可视化编辑器：拖放控件，不能编写复杂界面
		编写XML代码：可以了解界面背后的实现原理，而且具有很好的屏幕适应性。
##3.2 常用控件的使用方法
	UIWidgetTest项目
	要学会所有控件的使用不现实，本节内容只是起到一个引导作用，以后慢慢实践学习。
###3.2.1 TextView
	文本控件：显示一段文本信息。
	<TextView
        android:layout_width="match_parent"	// 高宽：match_parent/wrap_content(匹配父布局/包含内容)
        android:layout_height="wrap_content"
        android:gravity="top|center" 		// 重心：指定文字的对齐方式，可选值有top/bottom/left/right/center，可以用|指定多个值
        android:textSize="24sp"
        android:textColor="#ff0000"
        android:text="This is TextView" />	
###3.2.2 Button
	按钮：用于和用户交互的重要控件，前面使用得很多。
	<Button
        android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button" 				// 所有英文字母自动进行大写转换
        android:textAllCaps="false"/> 		// Caps:Capitals，大写字母,所有文本大写

	// 为Button的点击事件注册监听器
	// 匿名类的方式
	// 实现接口的方式
###3.2.3 EditView
总结发现，控件的使用规律：<font color="#ff0000">**id + 高宽 + 控件特有属性**</font>

	编辑控件：允许用户在控件里输入和编辑内容。应用场景非常普遍：发短信、发微博、聊QQ等。	
	<EditText
        android:id="@+id/edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Type something here" 	// 提示性文本
        android:maxLines="2"/> 				// 指定最大行数
###3.2.4 ImageView
	图片控件：用于展示图片。
	// 图片通常放在“drawable”开头的目录下，因为drawable目录没有指定分辨率，所以一般新建一个drawable-xhdpi目录用于存放图片
	<ImageView
        android:id="@+id/image_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/img_1"/>
###3.2.5 ProgressBar
	进度条：表示程序正在加载数据。
	<ProgressBar
        android:id="@+id/progress_bar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
		android:visibility="visible" // 所有控件都具有的可见属性，可选值有visible/invisible/gone
        android:progress="30"
        style="?android:attr/progressBarStyleHorizontal" // 默认是圆形滚动条，这里指定为水平滚动条
        android:maxWidth="100dp"/>
###3.2.6 AlertDialog
	警告对话框：用于提示一些非常重要的内容或者警告信息。比如为了防止用户误删重要内容，在删除前弹出一个确认对话框。
	// 创建一个AlertDialog实例
	AlertDialog.Builder dialog = new AlertDialog.Builder(MainActivity.this);
	// 设置标题、内容、是否取消等属性
    dialog.setTitle("This is Dialog");
    dialog.setMessage("Something Important.");
    dialog.setCancelable(false);// 不能通过Back键取消
    // 设置确定按钮的点击事件
    dialog.setPositiveButton("OK", new DialogInterface.OnClickListener() {
        @Override
        public void onClick(DialogInterface dialogInterface, int which) {

        }
    });
    // 设置取消按钮的点击事件
    dialog.setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
        @Override
        public void onClick(DialogInterface dialogInterface, int which) {

        }
    });
	// 显示对话框
    dialog.show();
###3.2.7 ProgressDialog
	进度条对话框：和AlertDialog类似，不同的是，它会在对话框中显示一个进度条，表示当前操作比较耗时，让用户耐心等待。
	ProgressDialog progressDialog = new ProgressDialog(MainActivity.this);
                progressDialog.setTitle("This is ProgressDialog");
                progressDialog.setMessage("Loading...");
                progressDialog.setCancelable(false);// 不能通过Back键取消
                progressDialog.show();
##3.3 详解4种基本布局
	布局：是一种可用于放置很多控件的容器，它可以按照一定规律调整内部控件的位置，从而编写出精美的界面。
		当然，布局的内部还可以放置布局，通过多层布局的嵌套，就能完成一些比较复杂的界面实现。
	还有AbsolutLayout、TableLayout等布局，只不过使用太少。
###3.3.1 线性布局
orientation属性

	// 注意1：线性布局的排列方向和内部控件的高宽设置。
	// 排列方向是horizontal，内部控件就不能将宽度指定为match_parent，这样单独一个控件就会把水平方向占满；
	// 排列方向是vertical，内部控件就不能将高度指定为match_parent，这样单独一个控件就会把竖直方向占满；

	// 注意2：layout_gravity和gravity属性的区别
	// layout_gravity：指定【控件在布局中】的对齐方式
	// gravity：指定【文字】的对齐方式

	// 注意3：排列方式和layout_gravity怎样搭配才能生效
	// 排列方向水平时，只有垂直方向上的对齐方式才会生效
	// 排列方向竖直时，只有水平方向上的对齐方式才会生效
	
	<LinearLayout
		android:layout_width="match_parent"
    	android:layout_height="match_parent"
		android:orientation="horizontal">
		<Button
	        android:id="@+id/button1"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="top"				// 控件水平排列时，只有竖直方向上的对齐方式才会生效
	        android:text="Button 1"
	        android:textAllCaps="false"/>
	
	    <Button
	        android:id="@+id/button2"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center_vertical"	// 控件水平排列时，只有竖直方向上的对齐方式才会生效
	        android:text="Button 2"
	        android:textAllCaps="false"/>
	
	    <Button
	        android:id="@+id/button3"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="bottom"				// 控件水平排列时，只有竖直方向上的对齐方式才会生效
	        android:text="Button 3"
	        android:textAllCaps="false"/>
	</LinearLayout>
layout_weight属性，允许使用比例的方式指定控件大小，在【手机屏幕的适配性】方面有很重要的作用

	// 编写一个消息发送界面
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:orientation="horizontal">			// 内部控件水平排列
		<!-- 更好的宽度自适配效果 -->
	    <EditText
	        android:id="@+id/edit_text"
	        android:layout_width="0dp"				// 宽度：0dp
	        android:layout_height="wrap_content"
	        android:layout_weight="1"				// 设置0dp的高宽属性比重，实现高宽自适应
	        android:hint="Type Something"/>
	
	    <Button
	        android:id="@+id/send"
	        android:layout_width="wrap_content"		// 宽度：包含内容
	        android:layout_height="wrap_content"	
	        android:textAllCaps="false"
	        android:text="Send"/>
	</LinearLayout>
###3.3.2 相对布局
	RelativeLayout
		layout_alignParentLeft,layout_alignParentRight,layout_alignParentTop,layout_alignParentBottom
		layout_above,layout_below,layout_toLeftOf,layout_toRightOf
###3.3.3 帧布局
	FrameLayout：相对简单，应用少。所有控件都会默认摆放到布局的左上角，控件相互重叠。
	可以通过内部控件的layout_gravity属性设置其对齐方式，和LinearLayout有点类似。

	<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent">

		<TextView
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="right"			// 居右对齐
	        android:text="This is TextView"/>
	
	    <ImageView
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="left"			// 居左对齐
	        android:src="@mipmap/ic_launcher"/>
	</FrameLayout>
###3.3.4 百分比布局
	由于LinearLayout支持按比例指定控件的大小，因此百分比布局只为FrameLayout和RelativeLayout进行功能扩展，
	提供PercentFrameLayout和PercentRelativeLayout两种全新的布局。

	// 新增布局定义在support库中（为了兼容性考虑），只需在项目的build.gradle中添加百分比布局的依赖就能使用了
	// app/build.gradle文件，dependencies闭包：
	dependencies {
	    implementation fileTree(dir: 'libs', include: ['*.jar'])
	    implementation 'com.android.support:appcompat-v7:28.0.0-alpha3'
	    /*添加百分比布局库的依赖*/
	    implementation 'com.android.support:percent:28.0.0-alpha3'
	    implementation 'com.android.support.constraint:constraint-layout:1.1.2'
	    testImplementation 'junit:junit:4.12'
	    androidTestImplementation 'com.android.support.test:runner:1.0.2'
	    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.2'
	}

	// 4个按钮平分屏幕
	<android.support.percent.PercentFrameLayout
	    xmlns:android="http://schemas.android.com/apk/res/android"
	    xmlns:app="http://schemas.android.com/apk/res-auto"		// 引入布局高宽百分比属性的命名控件
	    android:layout_width="match_parent"
	    android:layout_height="match_parent">
	    <!-- 详解4中基本布局 -->
	
	    <!-- 百分比布局，过时了 -->
	    <!--app:layout_widthPercent="50%"
	        app:layout_heightPercent="50%"-->

		<!-- 4个按钮平分屏幕 -->
	    <Button
	        android:id="@+id/button1"
	        android:text="Button 1"
	        android:layout_gravity="left|top"		// 左上
	        app:layout_widthPercent="50%"
	        app:layout_heightPercent="50%"/>
	
	    <Button
	        android:id="@+id/button2"
	        android:text="Button 2"
	        android:layout_gravity="right|top"		// 右上
	        app:layout_widthPercent="50%"
	        app:layout_heightPercent="50%"/>
	
	    <Button
	        android:id="@+id/button3"
	        android:text="Button 3"
	        android:layout_gravity="left|bottom"	// 左下
	        app:layout_widthPercent="50%"
	        app:layout_heightPercent="50%"/>
	
	    <Button
	        android:id="@+id/button4"
	        android:text="Button 4"
	        android:layout_gravity="right|bottom"	// 右下
	        app:layout_widthPercent="50%"
	        app:layout_heightPercent="50%"/>
	</android.support.percent.PercentFrameLayout>
##3.4 自定义控件
常用控件和布局的继承结构图如下所示，可以看出：

	1、所有的布局都是直接或间接继承ViewGroup；
	2、View是一种最基本的UI组件，它可以在屏幕上绘制一块【矩形区域】，并能响应这块区域的【各种事件】;
	3、ViewGroup是一种特殊的View，可以包含很多子View和子ViewGroup，是一种用于【放置控件和布局的容器】。
	

![常用控件和布局的继承结构][img_view_inherit]
###3.4.1 引入布局
创建一个自定义标题栏

	// 新建一个布局title.xml
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:orientation="horizontal"
	    android:layout_width="match_parent"
	    android:layout_height="wrap_content"
	    android:background="@drawable/title_bg">		// 为布局指定一个背景，标题栏
	
	    <Button
	        android:id="@+id/title_back"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:layout_margin="5dp"					// 外边距（上下左右）
	        android:background="@drawable/back_bg"		// 为控件指定一个背景，返回按钮
	        android:text="Back"
	        android:textColor="#fff"/>
	
	    <TextView
	        android:id="@+id/title_text"
	        android:layout_width="0dp"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:layout_weight="1"
	        android:gravity="center"
	        android:text="Title Text"
	        android:textColor="#fff"
	        android:textSize="24sp"/>
	
	    <Button
	        android:id="@+id/title_edit"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center"
	        android:layout_margin="5dp"					// 外边距（上下左右）
	        android:background="@drawable/edit_bg"		// 为控件指定一个背景，编辑按钮
	        android:text="Edit"
	        android:textColor="#fff"/>
	</LinearLayout>

	// 在activity_main.xml中，引入布局
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:orientation="vertical">
	
	    <include layout="@layout/title" />
	</LinearLayout>

	// 最后别忘了
	public class MainActivity extends AppCompatActivity {

	    @Override
	    protected void onCreate(Bundle savedInstanceState) {
	        super.onCreate(savedInstanceState);
	        setContentView(R.layout.activity_main);
	
	        // 隐藏系统自带的标题栏，关于ActionBar的更多用法将在第12章中讲解
	        ActionBar actionBar = getSupportActionBar();
	        if(actionBar != null){
	            actionBar.hide();
	        }
	    }
	}
###3.4.2 创建自定义控件
引入布局的技巧解决了重复编写【布局代码】的问题，但不能解决控件【响应事件注册代码】重复的问题，  
比如标题栏中的返回按钮，不管在哪个活动中，这个按钮的功能都是相同的，即销毁活动。  
这种情况最好用自定义控件的方式解决。  
**注意区别：**  
**LayoutInflater.from(context).inflate(R.layout.title,this);//3.4.2节**  
**View view = LayoutInflater.from(getContext()).inflate(resourceId,parent,false);//3.5.2节**

	// 1、自定义标题栏控件
	public class TitleLayout extends LinearLayout {
	    /**
	     * 重写LinearLayout中带有两个参数的构造函数
	     * @param context
	     * @param attrs
	     */
	    public TitleLayout(Context context, AttributeSet attrs){
	        super(context,attrs);
	        // 对标题栏布局进行动态加载？
	        // 通过LayoutInflater.from()方法构建出一个LayoutInflater对象
	        // 然后调用inflate()方法动态加载一个布局文件
	        // 第一个参数是要加载的【布局文件的id】，第二个参数是给加载好的布局添加一个【父布局】
	        LayoutInflater.from(context).inflate(R.layout.title,this);
	
	        // 2、为标题栏按钮注册点击事件
	        Button titleBack = findViewById(R.id.title_back);
	        titleBack.setOnClickListener(new OnClickListener() {
	            @Override
	            public void onClick(View view) {
	                ((Activity)getContext()).finish();
	            }
	        });
	        Button titleEdit = findViewById(R.id.title_edit);
	        titleEdit.setOnClickListener(new OnClickListener() {
	            @Override
	            public void onClick(View view) {
	                Toast.makeText(getContext(),"You clicked Edit button",Toast.LENGTH_SHORT).show();
	            }
	        });
	    }
	}

	// 3、添加自定义控件(非系统控件，都需要指定完整类名)
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent"
	    android:orientation="vertical">

	    <!-- 添加自定义控件和添加普通控件的方式是一样的，
	         只不过在添加自定义控件的时候，需要指明控件的完整类名-->
	    <com.jc.uicustomviews.TitleLayout
	        android:layout_width="match_parent"
	        android:layout_height="wrap_content" />
	</LinearLayout>
##3.5 最常用和最难用的控件——ListView
	手机屏幕控件有限，通常借助ListView实现大量数据的展示。
###3.5.1 ListView的简单用法
	public class MainActivity extends AppCompatActivity {

	    private String[] data = {"banana","apple","pear","orange","strawberry","watermelon",
	            "banana","apple","pear","orange","strawberry","watermelon",
	            "banana","apple","pear","orange","strawberry","watermelon"};
	
	    private List<Fruit> fruitList = new ArrayList<>();
	
	    @Override
	    protected void onCreate(Bundle savedInstanceState) {
	        super.onCreate(savedInstanceState);
	        setContentView(R.layout.activity_main);
	
	        // 数组中的数据是无法直接传递给ListView，需要借助适配器完成。
	        // 其中最好用的是ArrayAdapter，可以通过泛型指定适配的数据类型，在构造函数中把适配的数据传入。
	        // 依次传入【当前上下文、ListView子项布局的id，以及要适配的数据】
	        // 注意：android.R.layout.simple_list_item_1是内置布局文件，里面只有一个TextView，可用于简单的显示一段文本。
	        ArrayAdapter<String> adapter = new ArrayAdapter<>(
	                MainActivity.this,android.R.layout.simple_list_item_1,data
	        );
	
	        // 获取ListView
	        ListView listView = findViewById(R.id.list_view);
	        // 设置构建好的适配器，从而建立ListView和数据之间的关联
	        listView.setAdapter(adapter);
	    }
	}
###3.5.2 定制ListView的界面
只能显示一段文本太单调，准备在水果名称的旁边放置一张图片。  
**注意理解：View view = LayoutInflater.from(getContext()).inflate(resourceId,parent,false);**
	
	// 1、定义水果实体类，作为ListView适配器的适配类型
	public class Fruit {
	    private String name;// 水果名称
	    private int id;// 水果对应图片的资源id
	
	    public Fruit(String name, int id){
	        this.name = name;
	        this.id = id;
	    }
	
	    public String getName(){
	        return name;
	    }
	
	    public int getId(){
	        return id;
	    }
	}

	// 2、自定义ListView的子项（item）布局，fruit_item.xml
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:layout_width="match_parent"
	    android:layout_height="wrap_content">
	
	    <!-- 显示水果图片 -->
	    <ImageView
	        android:id="@+id/fruit_image"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content" />
	
	    <!-- 显示水果名称，并在垂直方向上居中显示 -->
	    <TextView
	        android:id="@+id/fruit_name"
	        android:layout_width="wrap_content"
	        android:layout_height="wrap_content"
	        android:layout_gravity="center_vertical"	// 在垂直方向上居中显示
	        android:layout_margin="10dp"/>
	</LinearLayout>

	// 3、创建自定义适配器
	// 继承自ArrayAdapter,泛型为Fruit类
	public class FruitAdapter extends ArrayAdapter<Fruit> {

	    private int resourceId;// 子项id
	
	    /**
	     * 重写父类的一组构造函数
	     * @param context 上下文
	     * @param textViewResourceId ListView子项布局的id
	     * @param objects 数据
	     */
	    public FruitAdapter(Context context, int textViewResourceId, List<Fruit> objects){
	        super(context,textViewResourceId,objects);
	        resourceId = textViewResourceId;
	    }
	
	    /**
	     * 重写，这个方法在每个子项滚动到屏幕内的时候被调用
	     * @param position
	     * @param convertView
	     * @param parent
	     * @return
	     */
	    @NonNull
	    @Override
	    public View getView(int position, @Nullable View convertView, @NonNull ViewGroup parent) {
	        // 获取当前项的Fruit实例
        	Fruit fruit = getItem(position);
        	// 【为子项加载传入的布局】
			// 第一个参数是要加载的【布局文件的id】，第二个参数是给加载好的布局添加一个【父布局】（前面3.4.2、自定义控件已经了解）
	        // 第三个参数指定成false,表示只让我们在父布局中声明的layout属性生效，但不为这个View添加父布局
	        // 因为一旦View有了父布局，它就不能添加到ListView中了（这是ListView的标准写法，以后对View理解更深刻就没问题了）
	        View view = LayoutInflater.from(getContext()).inflate(resourceId,parent,false);
	        ImageView fruitImage = view.findViewById(R.id.fruit_image);
	        TextView fruitName = view.findViewById(R.id.fruit_name);
	        // 设置显示的图片和文字
	        fruitImage.setImageResource(fruit.getId());
	        fruitName.setText(fruit.getName());
	        // 最后将布局返回
	        return view;
	    }
	}

	// 4、使用自定义适配器
	public class MainActivity extends AppCompatActivity {
	    private List<Fruit> fruitList = new ArrayList<>();
	
	    @Override
	    protected void onCreate(Bundle savedInstanceState) {
	        super.onCreate(savedInstanceState);
	        setContentView(R.layout.activity_main);
			
			// 初始化水果数据
	        initFruits();
	        // 构建自定义水果适配器
	        FruitAdapter adapter = new FruitAdapter(MainActivity.this,R.layout.fruit_item,fruitList);
	
	        // 获取ListView
	        ListView listView = findViewById(R.id.list_view);
	        // 设置构建好的适配器，从而建立ListView和数据之间的关联
	        listView.setAdapter(adapter);
			
			// 5、ListView的点击事件
	        listView.setOnItemClickListener(new AdapterView.OnItemClickListener() {
	            @Override
	            public void onItemClick(AdapterView<?> adapterView, View view, int position, long id) {
	                Fruit fruit = fruitList.get(position);
	                Toast.makeText(MainActivity.this,"我想吃："+fruit.getName(),Toast.LENGTH_SHORT).show();
	            }
	        });
	    }
	
	    private void initFruits(){
	        for(int i=0;i<2;i++){
	            Fruit apple = new Fruit("Apple",R.drawable.apple_pic);
	            fruitList.add(apple);// 苹果
	            Fruit banana = new Fruit("Banana",R.drawable.banana_pic);
	            fruitList.add(banana);// 香蕉
	            Fruit orange = new Fruit("Orange",R.drawable.orange_pic);
	            fruitList.add(orange);// 橘子
	            Fruit watermelon = new Fruit("Watermelon",R.drawable.watermelon_pic);
	            fruitList.add(watermelon);// 西瓜
	            Fruit pear = new Fruit("Pear",R.drawable.pear_pic);
	            fruitList.add(pear);// 梨子
	            Fruit grape = new Fruit("Grape",R.drawable.grape_pic);
	            fruitList.add(grape);// 葡萄
	            Fruit pineapple = new Fruit("Pineapple",R.drawable.pineapple_pic);
	            fruitList.add(pineapple);// 菠萝，凤梨
	            Fruit strawberry = new Fruit("Strawberry",R.drawable.strawberry_pic);
	            fruitList.add(strawberry);// 草莓
	            Fruit cherry = new Fruit("Cherry",R.drawable.cherry_pic);
	            fruitList.add(cherry);// 樱桃
	            Fruit mango = new Fruit("Mango",R.drawable.mango_pic);
	            fruitList.add(mango);// 芒果
	        }
	    }
	}
###3.5.3 提升ListView的使用效率
	在FruitAdapter的getView()方法中，每次都要重新加载布局，怎么优化？
		优化一：可以用convertView参数将之前加载好的布局进行缓存，以便之后重用。
	每次都会调用View的findViewById()方法获取控件实例，怎么优化？
		优化二：借助ViewHolder进行优化，ViewHolder用于缓存控件实例。

	public class FruitAdapter extends ArrayAdapter<Fruit> {

	    private int resourceId;// 子项id
	
	    /**
	     * 重写父类的一组构造函数
	     * @param context 上下文
	     * @param textViewResourceId ListView子项布局的id
	     * @param objects 数据
	     */
	    public FruitAdapter(Context context, int textViewResourceId, List<Fruit> objects){
	        super(context,textViewResourceId,objects);
	        resourceId = textViewResourceId;
	    }
	
	    /**
	     * 重写，这个方法在每个子项滚动到屏幕内的时候被调用
	     * @param position
	     * @param convertView 用于将之前【加载好的布局进行缓存】
	     * @param parent
	     * @return
	     */
	    @NonNull
	    @Override
	    public View getView(int position, @Nullable View convertView, @NonNull ViewGroup parent) {
	        // 获取当前项的Fruit实例
	        Fruit fruit = getItem(position);
	        View view;
	        ViewHolder viewHolder;
	        if(convertView == null){
	            // 【为子项加载传入的布局】
	            // 第一个参数是要加载的【布局文件的id】，第二个参数是给加载好的布局添加一个【父布局】（前面3.4.2、自定义控件已经了解）
	            // 第三个参数指定成false,表示只让我们在父布局中声明的layout属性生效，但不为这个View添加父布局
	            // 因为一旦View有了父布局，它就不能添加到ListView中了（这是ListView的标准写法，以后对View理解更深刻就没问题了）
	            view = LayoutInflater.from(getContext()).inflate(resourceId,parent,false);
	
	            // 2、优化二：控件实例缓存
	            viewHolder = new ViewHolder();
	            viewHolder.fruitImage = view.findViewById(R.id.fruit_image);
	            viewHolder.fruitName = view.findViewById(R.id.fruit_name);
	            view.setTag(viewHolder);// 将ViewHolder存储在View中
	        }else{
	            // 1、优化一：加载布局缓存
	            view = convertView;
	            viewHolder = (ViewHolder) view.getTag();// 将ViewHolder从View中取出
	        }
	        // 设置显示的图片和文字
	        viewHolder.fruitImage.setImageResource(fruit.getId());
	        viewHolder.fruitName.setText(fruit.getName());
	        // 最后将布局返回
	        return view;
	    }
	}
	
	/**
	 * 新增一个内部类，用于【对控件的实例进行缓存】
	 */
	class ViewHolder {
	    ImageView fruitImage;
	    TextView fruitName;
	}
###3.5.4 ListView的点击事件
	见3.5.2代码第5点
##3.6 更强大的滚动控件——RecyclerView
	ListView功能强大，但存在一些缺点：
		1、若不使用一些技巧提升它的运行效率，其性能会非常差；
		2、扩展性不够好，它只能实现数据纵向滚动，不能横向滚动；
	更强大的滚动控件——RecyclerView，是增强版的ListView。
###3.6.1 RecyclerView的基本用法
	
###3.6.2 实现横向滚动和瀑布流布局
	
###3.6.3 RecyclerView的点击事件
	
##3.7 编写界面的最佳实践
###3.7.1 制作Nine-Patch图片
	略...
###3.7.2 编写精美的聊天界面
注意编程思路：界面设计-》分解组装
综合前面所学：自定义控件、适配器

	// 1、聊天界面布局
	...

##3.8 小结与点评
	本章内容较多，但收获也颇丰。
	本章使用了各种控件，制作出了丰富多彩的界面，尤其在实战环节，编写出了精美的聊天界面。
	基本将重要的UI知识点都覆盖了：
		从常用控件入手，
		依次介绍了基本布局、
		自定义控件、
		ListView、
		RecyclerView
	真正理解编写界面的原理
	目前只学习了手机方面的开发技巧，接下来将设计平板方面的知识。
	适当休息、继续前行！
#4 手机平板要兼顾——探究碎片
	手机：3-6英寸
	平板：7-10英寸
	Android 3.0 引入碎片的概念，它可以让界面在平板上更好的展示。
##4.1 碎片是什么
	碎片（Fragment）是一种嵌入活动当中的【UI片段】，它能让程序更加合理充分的利用大屏幕的控件，在平板上应用广泛。

# 附录图片
	img_view_inherit
[img_view_inherit]:data:image/png;base64,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