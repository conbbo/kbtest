 * 表单添加绑定事件（focus、blur、upload）返回
 * @id 
 * @param {Object} box form的页面范围
 * @param {Object} rlues 验证范围
 * @return {Object} 实例
 * @author kongbo | kongbo@staff.sina.com.cn v2.1
 * 添加button按钮，submit及其他
 * @example
 * 
 * 
 * <input type="text" value="" name="title" class="W_input ev_input" 
 * defval="默认显示文字" //for兼容ie6/7（ie6/7 getAttribute('placeholder')=null）,ie7+浏览器使用placeholder
 * vmax/vmin="10"		//最大/最小字数
 * tip="tipids"			//显示提示错误的 tipid
 * autocut="max=10&rule=截取应用的规则"//自动截取rule可在rule参数中添加
 * get="/aj/get/request"
 * post="/aj/post/request"
 * verify=""
 * 按钮：	button=submit|reset
 * 默认：	focusval=focus默认显示文字&
 * 			focusval	focus时默认文案
 * 验证：	acttype=notEmpty|max&errmsg=请输入活动标题||标题不能超过30个字&sucmsg=true&tipmsg=给你的活动起一个好名字
 * 			acttype		blur触发的事件（|）分割(common.form.regular)
 *			errmsg		错误提示信息（||）分割
 *			tipmsg		提示问案
 *			sucmsg		显示正确提示信息 true(无文字)
 * >
 * 
 * <div tipid="tipids">显示提示信息</div>
 * tip="tipids" vmax="10" verify="acttype=notEmpty|max&errmsg=请输入活动标题||标题不能超过10个字"
 * return:
 *  that.fire(el,isfocus)	//可用于触发focus|blur事件;el(提示元素||提示元素tip值)
 *  that.json(true)			//当前表单内容，有错误返回false,true滚动到最顶出错标签的位置
 *  that.clearTip			//清除所有提示
 *  that.tips(el,opts)		//提示信息;el(提示元素||提示元素tip值)opts(msg 提示信息,type 1/error 2/success 3/tips 4/loading def/null)
 *  that.setDef				//设置默认值，insertHTML或innerHTML后需要操作
 *  that.tipMsg=function	//编辑提示信息返回格式;
 * 
 * @example
 * $.common.form.verify(node,
 		{
 			rules:{
 				newRule:function(el){
					return true//发生错误
 				},
 			},
			//getTip不存在按照唯一弹层方式进行
			getTip: 'dl span[errTip]'||function(el){
				return showerr Tipid Dom
			},
			tipTemp: function(msg, type){
				return msg;
			},
			showTip: true,
			forceCheck: true  //强制check，包括disable和hidden的
 		});
