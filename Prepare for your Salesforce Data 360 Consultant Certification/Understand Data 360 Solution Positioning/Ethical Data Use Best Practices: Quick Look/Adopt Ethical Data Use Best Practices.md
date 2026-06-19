# Adopt Ethical Data Use Best Practices

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the five Salesforce Data Ethics best practices.  
    
*   Adopt and apply data ethics best practices.  
    

## Trailcast

If you'd like to listen to an audio recording of this module, please use the player below. When you’re finished listening to this recording, remember to come back to each unit, check out the resources, and complete the associated assessments.

## Personalization and Privacy Don’t Have to Be at Odds

An inherent tension exists today between personalization and privacy. Consumers expect personalized experiences, but they also want companies to protect and respect their privacy. To provide elevated experiences, organizations need consumer data. Companies need to find ways to deliver amazing personalization while building long-lasting trust with their customers.

The Salesforce Research and Insights team conducted an in-depth study with both consumers and marketers to understand their perspectives on personalization and data usage. The results identify ways to drive ethical personalization, and help us get the right message to the right person without crossing into creepy or the unexpected. Our findings, detailed in the [State of the Connected Customer, 5th edition](https://www.salesforce.com/content/dam/web/en_us/www/documents/research/salesforce-state-of-the-connected-customer-fifth-ed.pdf), can help you and your team deliver personalized experiences that make customers feel understood while fulfilling expectations for privacy and transparency. 

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

61% of customers are comfortable with companies using relevant personal information—but only if it’s used transparently and beneficially.

## Five Data Ethics Best Practices

Data ethics are guideposts about the gathering, protecting, and use of personally identifiable information. Knowing and applying these five data ethics best practices helps you manage data thoughtfully while delivering personalized experiences and deepening trust. 

1.  Use and collect individual information appropriately.  
    
2.  Provide clear exchange of value for data.  
    
3.  Treat sensitive data carefully.  
    
4.  Collect and use only what you need.  
    
5.  Choose third-party partners carefully.  
    

## Use and Collect Individual Information Appropriately

**Give customers control of their preferences—and honor them.** The Preference Manager component of Salesforce Privacy Center allows you to configure and publish forms to capture end-user consent and preferences. This helps you easily update their preferences, build a unified profile of each customer, and better track and honor their explicit preferences throughout all your omni-channel marketing practices.

**Practice data minimization.** Digital privacy laws expect companies to respect end users’ rights to data minimization. That means collecting and retaining only the minimum amount of personal data necessary to fulfill the specific purpose for which it was shared. 

## Provide Clear Exchange of Value for Data

Examples of clear benefits including adding convenience_,_ like providing recommendations. For example, suggesting items a customer might need based on what’s currently in their cart or offering a coupon in exchange for entering an email address.

![A website shows a user, Aubrey, what items other customers frequently buy with the items currently in the cart.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/ethical-data-use-best-practices-quick-look/adopt-ethical-data-use-best-practices/images/2fb44a0a54eb0d1b76783c020bbf5a95_kix.gql8r4n6jyz8.png)

## Treat Sensitive Data Carefully

**What data should you collect?** While we can’t give you a definitive list of sensitive data points, carefully consider which data is most valuable and what might be considered proxies for protected classes of information. Ultimately, it’s up to you and your organization to identify sensitive data and validate the reasons you’re asking for it. 

If you do have a valid use case for storing sensitive data such as financial or medical information, use that data appropriately and treat it with respect. For example, in the US, ZIP codes are often highly correlated with race, so knowing a customer’s ZIP code can create bias and derail accurate personalization. 

**Observe the “right of least privilege.”** That means ensuring that only those folks inside your organization who truly need data should have access to it. The fewer the people with access, the better. By default, those who _do_ have access should be able to read, but not change, the data.

## Collect and Use Only What You Need

**Data can be an asset, but it can also be a liability.** For example, if you want to know your customers’ birthday so you can send them a gift, consider asking for only a month and date: July 1. Omitting the year lets you store less information, preventing age-related bias or discrimination from creeping into your systems. 

**Focus on intent and behavioral-based patterns, not just the attributes you collect.** To help develop trust over time and demonstrate authenticity by responsibly using customer data, consider segmenting your audiences based on intent or behavioral attributes (browses shoes, likes the color green, shows an interest in soccer, and so on), not just demographics (age, gender, race, and so forth). 

## Choose Third-Party Partners Carefully

In addition to being mindful and intentional about ingesting first- and third-party data, be intentional about activating data through various ad platforms. When engaging with an activation partner, ensure that you understand the chain of custody for data being provided to the partner. 

What happens after the activation partner uses the data for your campaign? Is it deleted? Reused? Review contracts with your activation partners to ensure that there are clear obligations with respect to the care, custody and control of any data sent to the [partner](https://salesforce.quip.com/KU3zA7r9UCTZ). 

## Summary

Building and maintaining trust can be challenging when it comes to the collection and use of data to deliver personalized experiences. Salesforce empowers users to implement the five best practices for ethical data. Making ethical choices about data, personalization, and privacy at every turn can save time, reduce costs, and eliminate frustration for you and your customers.

## Resources

*   [_Salesforce_: State of the Connected Customer, 5th Edition](https://www.salesforce.com/content/dam/web/en_us/www/documents/research/salesforce-state-of-the-connected-customer-fifth-ed.pdf) (Download)
*   [_Salesforce Help_: Data Ethics](https://help.salesforce.com/s/articleView?id=data.c360a_ethics.htm)

---

Two quiz questions:

**Question 1:** When a customer consents to providing data, how long should you keep that data?

**Answer: D – Until the specific purpose it was collected for is fulfilled.**

The document explains the principle of *data minimization*, which means collecting and retaining only the minimum amount of personal data necessary to fulfill the specific purpose for which it was shared.

---

**Question 2:** True or false: It's best to collect all individual information and determine the use cases later.

**Answer: B – False.**

The fourth best practice is explicitly "Collect and Use Only What You Need." The document states that data can be a *liability*, not just an asset, and encourages organizations to be intentional about what they gather rather than collecting everything speculatively.