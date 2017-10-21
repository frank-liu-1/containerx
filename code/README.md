#containerx
----
<b>简介：<b/> <br/>
containerx是一款迷你型的bean容器，IoC框架。是作者学习了Spring源码后，为了进一步学习Spring原理而自行开发的框架。
极少使用其他的第三方jar包。<br/><br/>

<b>用途：<b/>
主要用于学习Spring/AOP原理 <br/>
<b>核心开发者</b> Frank Liu(刘少明) 个人git https://github.com/frank-liu-1 <br/>
邮箱liushaomingdev@163.com
<br/>

<b>已经实现的功能：</b>
1. setter注入; <br/>
2. 单例bean的注册和获取; <br/>

<br/>
小demo<br/>
<pre><code>
public class DemoApp {
	public static void main(String[] args) {
		XmlBeanFactory beanFactory = new XmlBeanFactory("beans.xml");
		Person person = (Person)beanFactory.getBean("myPerson");
		System.out.println("name=" + person.getName());
		System.out.println("address=" + person.getAddress());
		Person person1 = (Person)beanFactory.getBean("myPerson");
		System.out.println("person=" + person);
		System.out.println("person1=" + person1);
		System.out.println("person == person1? " + (person == person1));
	}
}
</pre></code>
运行结果如下：
<pre><code>
name=Frank Liu
address=Shanghai,China(中国-上海)
person=com.frank.containerx.demo.model.Person@33909752
person1=com.frank.containerx.demo.model.Person@33909752
person == person1? true
</pre></code>