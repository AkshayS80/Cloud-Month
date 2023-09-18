# Module 11: Describe monitoring tools in Azure

This is the Eleventh Module of the Azure Fundementals Challenge

## Objectives

1. Describe the purpose of Azure Advisor
2. Describe Azure Service Health
3. Describe Azure Monitor, including Azure Log Analytics, Azure Monitor Alerts, and Application Insights

### Azure Advisor

Azure Advisor is like a helpful guide for your Azure resources. It looks at what you're doing and suggests ways to make things better in terms of reliability, security, performance, efficiency, and cost. Azure Advisor gives you recommendations that you can act on right away or choose to deal with later. It's like having a personal trainer for your cloud setup. You can see these recommendations in the Azure portal, and you can even set up alerts to notify you when there are new suggestions. It's a handy tool to keep your Azure resources in top shape.

### Azure Service Health

Azure Service Health is like your personal health monitor for Microsoft Azure. It helps you keep tabs on the overall health of Azure and your specific resources within it. Here's how it works:

1. **Azure Status**: This is like a big picture view of Azure's health worldwide. If there's a major issue affecting many people, you can check Azure Status to get the scoop on what's going on.

2. **Service Health**: This is more tailored to your specific usage. It focuses on the Azure services and regions you're using. So, if there's something happening that affects your stuff, you'll find out about it here. You can even set up alerts to notify you when there are issues that matter to you.

3. **Resource Health**: This one is all about your individual resources, like a particular virtual machine. It tells you if your specific cloud resources are doing well or if there are any issues. You can set up alerts for this too.

By using these three parts of Azure Service Health, you get a complete view of your Azure world. From the big global picture down to your own resources. Plus, it keeps a record of past issues, so you can see if something is becoming a pattern. And if you do run into a problem, it even gives you links to support to help you out.

### Azure Monitor

Azure Monitor is like your watchful eye over your digital world. It does four main things:

1. **Collects Data**: It gathers information from all kinds of sources in your applications, like the application itself, the operating system, and the network. It doesn't just work with stuff in Azure; it can even keep an eye on things in other clouds.

2. **Stores Data**: All that data it collects is stored in one place, so you can easily access it when you need it.

3. **Uses Data**: This is where the magic happens. You can see how well your systems are doing in real-time or look back in time to spot trends. It can show you the big picture or get super detailed, depending on what you need. You can even create your own custom views if you're into that.

4. **Takes Action**: If something goes wrong, Azure Monitor can give your team a heads up through alerts, like sending a text or email. It can also automatically adjust things, like scaling up resources if there's a sudden surge in demand.

So, it's like your trusty assistant, always watching, ready to tell you what's going on, and even helping out.

### Azure Log Analytics

Azure Log Analytics is like a detective's notebook for your digital world. It's where you go in the Azure portal to ask questions about what's happening with your stuff. You can ask simple questions like, "Show me all the records," and then you can use Log Analytics to organize and dig into those records. Or, you can get fancy and ask complex questions to find trends and create charts. Whether you're just poking around to see what's up or you're using the data for special tasks like alerts or reports, Log Analytics is where you do all the detective work.

### Azure Monitor Alerts

Azure Monitor Alerts are like your personal watchdogs for your Azure resources. They keep an eye on things and let you know if something goes wrong. To set them up, you use something called action groups. Action groups are like a list of who to call and what to do when the watchdogs see trouble. So, if there's a problem, they know who to alert, whether it's you or a team member, and what actions to take, like sending a message or trying to fix the issue.

### Application Insights

Application Insights watches over your apps to make sure they're working smoothly, whether they're in Azure, on your own servers, or even in other clouds. There are two ways to set it up. You can either put a special tool called an SDK right into your app's code, or you can use something called the Application Insights agent. This agent works with various programming languages like C#, Java, JavaScript, and more.

Once you've got Application Insights working, it starts collecting all sorts of useful data, like how fast your app responds, how often it fails, and if outside services are causing any slowdowns. It even keeps an eye on what users are doing and how your servers are holding up.You can tell it to send fake test requests to your app, even when there's not much real traffic. This way, you can always check if your app is running smoothly, no matter what.