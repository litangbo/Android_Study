# 封面
![Android学习第一书](/img/00-FirstCode-Android-v2-guolin.jpg)
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

# 1 开始启程——你的第一行Android代码
	市场占有率最高的移动OS
	发展史：
		2003年10月，Andy Rubin等人创办Android公司；
		2005年8月，谷歌收购（仅成立了22个月，不到2年）；
		2008年，推出第一个版本……知识产权问题；
		两年后，Android就超过霸占市场逾十年的诺基亚，成为全球第一大智能手机操作系统。
		而近几年，国内的手机厂商也大放异彩，小米、华为、魅族等新兴品牌都推出了不错的Android手机。
## 1.1 Android简介
	二十几个版本、完整的生态系统。	
### 1.1.1 系统架构
	四层架构：
		Linux内核层：为各种硬件提供底层驱动；
		系统运行库层：通过C/C++库提供主要特性支持，运行时库（Dalvik虚拟机）；
		应用框架层：提供各种API；
		应用层：应用程序开发。
### 1.1.2 已发布版本
	版本号、系统代号、API、市场占有率
	2016年以前，4.0以上的系统已占据超过98%的市场份额，所以面向4.0以上的系统开发，不再去兼容2.x系统了。
### 1.1.3 应用特色
	四大组件：活动（Activity）、服务（Service）、广播接收器（Broadcast Receiver）、内容提供器（Content Provider）；
	丰富的系统控件：还可以自定义控件；
	SQLite数据库：轻量级、运算快的嵌入式关系型数据库；
	强大的多媒体：音乐、视频、录音、拍照、闹铃……
	地理位置定位：和PC相比，GPS+地图-》LBS领域潜力无限。
## 1.2 搭建开发环境
### 1.2.1 准备工具
	JDK、Android SDK、Android Studio
### 1.2.2 下载安装
	Android官网或百度网盘
## 1.3 第一个Android项目
### 1.3.1 创建HelloWorld项目
	创建流程、注意事项
### 1.3.2 启动模拟器
	版本选择
### 1.3.3 运行HelloWorld
	查看效果、收获喜悦
### 1.3.4 分析程序
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
### 1.3.5 详解项目中的资源
	res 图片、布局、字符串等资源目录
				drawable
				layout
				mipmap-...
				values
### 1.3.6 详解build.gradle文件
	Gradle构建工具
## 1.4 日志工具
### 1.4.1 使用Log
	Log.v() verbose 冗长的，打印琐碎、意义最小的日志信息
	Log.d() debug
	Log.i() info
	Log.w() warn
	Log.e() error
### 1.4.2 为什么使用Log而不使用System.out
	System.out的缺点，Log可以解决的问题：
		日志打印不可控制、打印时间无法确定、不能添加过滤器、日志没有级别区分
### 1.5 小结与点评
	很充实，甚至有点沾沾自喜：
		首先对Android系统有了更加充足的认识；
		然后成功搭建了开发环境；
		接着创建了第一个Android项目，并对其目录结构和执行过程有了一定认识；
		最后学习了日志工具。
	不过也别太过于满足，还需要付出更多努力。适当休息，继续前进！

# 2 探究活动
	制定后面的学习路线：界面（看得见，感兴趣）--》出色的程序算法、架构（不易看见、有难度）
## 2.1 活动是什么（四大组件之一，UI）
	活动（Activity）是最容易吸引用户的地方，它是一种可以【包含用户界面】的【组件】，主要【用于和用户交互】。
## 2.2 活动的基本用法
	手动创建活动：流程
### 2.2.1 手动创建活动
	创建项目-》切换到Project模式-》创建Empty Activity
### 2.2.2 创建和加载布局
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
### 2.2.3 活动注册
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
### 2.2.4 使用Toast
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
### 2.2.5 使用Menu
	理清过程……
### 2.2.6 销毁一个活动
	finish();
## 2.3 使用Intent(意图)
	怎样在主活动和其他活动之间跳转？用Intent实现
### 2.3.1 使用显示Intent
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
### 2.3.2 使用隐式Intent
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
### 2.3.3 更多隐式Intent的用法
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
### 2.3.4 向下一个活动传递数据
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
### 2.3.5 返回数据给上一个活动
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
## 2.4 活动的生命周期
	合理管理应用资源
### 2.4.1 返回栈
	任务（Task）：一组放在栈里的【活动的集合】。
	返回栈（Return Stack）:【后进先出】的数据结构
		启动新的活动，【入栈】，处于栈顶
		Back键或finish(),销毁活动，【出栈】，前一个入栈的活动处于栈顶
	如何管理活动入栈出栈？返回栈工作原理
### 2.4.2 活动状态
	4种状态——能够熟练判断当前活动处于哪个状态
		运行状态：活动处于栈顶（系统最不愿意回收的就是处于运行状态的活动，因为这会带来非常差的用户体验）
		暂停状态：不处于栈顶，但仍然可见（比如：对话框下面的活动。系统也不愿意回收这种存活着的活动，除非内存极低的情况下）
		停止状态：不处于栈顶，且完全不可见
		销毁状态：从返回栈中移除
### 2.4.3 活动的生存期
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

![活动生命周期的示意图](/img/01-ActivityLifeCycle-en-detail.png)

### 2.4.4 体验活动的生命周期
	ActivityLifeCycleTest
		MainActivity:Log.v()
		NormalActivity
		DialogActivity
### 2.4.5 活动被回收了怎么办
	onSaveInstanceState(Bundle outState)
	...
## 2.5 活动的启动模式
	四种——通过<activity>标签的android:launchMode属性配置启动模式
		standard
		singleTop
		singleTask
		singleInstance
### 2.5.1 standard
	体会效果...
### 2.5.2 singleTop
	体会效果...
### 2.5.3 singleTask
	体会效果...
### 2.5.4 singleInstance
	体会效果...
## 2.6 活动的最佳实践
### 2.6.1 当前在哪一个活动
	public class BaseActivity extends AppCompatActivity {
		// TODO
	}
### 2.6.2 随时随地退出程序
	public class ActivityCollector {
		// TODO
	}
### 2.6.3 启动活动的最佳写法
	// FirstActivity向SecondActivity传入两个字符串参数
	// SecondActivity.java
	public static void actionStart(Context context,String data1,String data2) {
		// TODO
	}
## 2.7 小结与点评
	有点疲惫，但内心仍充满喜悦：
		活动所有重要的知识点
			从活动的基本用法
			到启动活动和传递数据的方式
			再到活动的生命周期
			以及活动的启动模式
		活动的最佳实践技巧
	在活动方面算一个小高手了，但后面需要学习的还很多，要做好心理准备。
	适当休息，继续前进！

# 3 UI开发
	软件也要拼脸蛋
	界面设计和功能开发同样重要
## 3.1 如何编写程序界面
	两种方式
		可视化编辑器：拖放控件，不能编写复杂界面
		编写XML代码：可以了解界面背后的实现原理，而且具有很好的屏幕适应性。
## 3.2 常用控件的使用方法
	UIWidgetTest项目
	要学会所有控件的使用不现实，本节内容只是起到一个引导作用，以后慢慢实践学习。
### 3.2.1 TextView
	文本控件：显示一段文本信息。
	<TextView
        android:layout_width="match_parent"	// 高宽：match_parent/wrap_content(匹配父布局/包含内容)
        android:layout_height="wrap_content"
        android:gravity="top|center" 		// 重心：指定文字的对齐方式，可选值有top/bottom/left/right/center，可以用|指定多个值
        android:textSize="24sp"
        android:textColor="#ff0000"
        android:text="This is TextView" />	
### 3.2.2 Button
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
### 3.2.3 EditView
总结发现，控件的使用规律：<font color="#ff0000">**id + 高宽 + 控件特有属性**</font>

	编辑控件：允许用户在控件里输入和编辑内容。应用场景非常普遍：发短信、发微博、聊QQ等。	
	<EditText
        android:id="@+id/edit_text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Type something here" 	// 提示性文本
        android:maxLines="2"/> 				// 指定最大行数
### 3.2.4 ImageView
	图片控件：用于展示图片。
	// 图片通常放在“drawable”开头的目录下，因为drawable目录没有指定分辨率，所以一般新建一个drawable-xhdpi目录用于存放图片
	<ImageView
        android:id="@+id/image_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/img_1"/>
### 3.2.5 ProgressBar
	进度条：表示程序正在加载数据。
	<ProgressBar
        android:id="@+id/progress_bar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
		android:visibility="visible" // 所有控件都具有的可见属性，可选值有visible/invisible/gone
        android:progress="30"
        style="?android:attr/progressBarStyleHorizontal" // 默认是圆形滚动条，这里指定为水平滚动条
        android:maxWidth="100dp"/>
### 3.2.6 AlertDialog
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
### 3.2.7 ProgressDialog
	进度条对话框：和AlertDialog类似，不同的是，它会在对话框中显示一个进度条，表示当前操作比较耗时，让用户耐心等待。
	ProgressDialog progressDialog = new ProgressDialog(MainActivity.this);
                progressDialog.setTitle("This is ProgressDialog");
                progressDialog.setMessage("Loading...");
                progressDialog.setCancelable(false);// 不能通过Back键取消
                progressDialog.show();
## 3.3 详解4种基本布局
	布局：是一种可用于放置很多控件的容器，它可以按照一定规律调整内部控件的位置，从而编写出精美的界面。
		当然，布局的内部还可以放置布局，通过多层布局的嵌套，就能完成一些比较复杂的界面实现。
	还有AbsolutLayout、TableLayout等布局，只不过使用太少。
### 3.3.1 线性布局
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
### 3.3.2 相对布局
	RelativeLayout
		layout_alignParentLeft,layout_alignParentRight,layout_alignParentTop,layout_alignParentBottom
		layout_above,layout_below,layout_toLeftOf,layout_toRightOf
### 3.3.3 帧布局
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
### 3.3.4 百分比布局
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
## 3.4 自定义控件
常用控件和布局的继承结构图如下所示，可以看出：

	1、所有的布局都是直接或间接继承ViewGroup；
	2、View是一种最基本的UI组件，它可以在屏幕上绘制一块【矩形区域】，并能响应这块区域的【各种事件】;
	3、ViewGroup是一种特殊的View，可以包含很多子View和子ViewGroup，是一种用于【放置控件和布局的容器】。
	

![常用控件和布局的继承结构](/img/02-controls-layout-inherit-view.png)
### 3.4.1 引入布局
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
### 3.4.2 创建自定义控件
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
## 3.5 最常用和最难用的控件——ListView
	手机屏幕控件有限，通常借助ListView实现大量数据的展示。
### 3.5.1 ListView的简单用法
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
### 3.5.2 定制ListView的界面
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
### 3.5.3 提升ListView的使用效率
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
### 3.5.4 ListView的点击事件
	见3.5.2代码第5点
## 3.6 更强大的滚动控件——RecyclerView
	ListView功能强大，但存在一些缺点：
		1、若不使用一些技巧提升它的运行效率，其性能会非常差；
		2、扩展性不够好，它只能实现数据纵向滚动，不能横向滚动；
	更强大的滚动控件——RecyclerView，是增强版的ListView。
### 3.6.1 RecyclerView的基本用法
	
### 3.6.2 实现横向滚动和瀑布流布局
	
### 3.6.3 RecyclerView的点击事件
	
## 3.7 编写界面的最佳实践
### 3.7.1 制作Nine-Patch图片
	略...
### 3.7.2 编写精美的聊天界面
注意编程思路：界面设计-》分解组装
综合前面所学：自定义控件、适配器

	// 1、聊天界面布局
	...

## 3.8 小结与点评
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
# 4 手机平板要兼顾——探究碎片
	手机：3-6英寸
	平板：7-10英寸
	Android 3.0 引入碎片的概念，它可以让界面在平板上更好的展示。
## 4.1 碎片是什么
	碎片（Fragment）是一种嵌入活动当中的【UI片段】，它能让程序更加合理充分的利用大屏幕的控件，在平板上应用广泛。

