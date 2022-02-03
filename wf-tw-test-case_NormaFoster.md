Hi! Here is a document that you need to review. Please convert this document t[o Markdown u](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)sing the editor of your choice (Atom, Sublime Text, etc.). Then, submit your Markdown file to[ github.com. ](https://github.com/)To do this, you may need to create an account and a repository. Note that the repository needs to be public so we can review your work.  

If you feel that some edits are a matter of style, follow the[ Google Developer Style Guide, ](https://developers.google.com/style/)or just leave your considerations as a comment. Thank you, and good luck!  

—————  

**Working With Bot Tasks**
Here is some helpful Bot Task terminology

**Bot Tasks** contain work to be done by WorkFusion’s Bot. These Bots perform the steps in your Business Process which are more suited for automation than human labor. Bot Tasks can exist only as a Business Processes step.  

For example: address parsing, determining the width and height of an image, interacting with your API or repository, or filtering content that do not meet certain criteria.  

**Bot Configs** are written using Web-Harvest library and are executed for each Record separately. For writing Web-Harvest XML configs you can use pre- defined Web-Harvest XML elements described here or WorkFusion plugins.  

**Bot Config Bundle** is a bundled java library containing a bot config and a java code reference that can be used in this bot config.  

**How to Create, Test, and Run**  

1. Create and test a Web-Harvest config using the WorkFusion Studio (Eclipse- based IDE).  
1. Create a Bot Use Case in WorkFusion. Choose the Bot Use Case type (ETL is the best to use for reusing and adds flexibility.)  
3. Create a BP and include a Bot Step based on this Use Case. Alternatively, you can use WorkFusion Repository and import a Bot Config Bundle to WorkFusion.  
3. Test the Bot Config in Business Process Step using a small input batch.  
3. If needed, make changes to column names, use proxy, datastore connection, output column names.  
3. Update the created Bot Use Case and use it in your production Business Process Step.  

Alternatively you can create a Bot Task in the Business Process Step (Design Process tab) from scratch (Blank Use Case) and paste your code, but this approach leads to multiple issues.  

**Execution Details**  

XML configuration is executing for each submission. If your input CSV file contains 40 Records, the WebHarvest XML configuration will be executed 40 times, once for each Record.  

If some error occurs, the Bot Config will be run 5 times.  

**Results**  

The results of a Bot Task are defined in the **export** plugin settings. All the columns created by the Bot Task can be used in further Business Process steps (both Manual and Bot).  

**Hello World Example**  

The following example:  

1. gets HTTP response from URLs listed in the **url\_to\_check** column of the input data file
2. records the HTTP response into the **http\_response** variable  
2. exports all original columns and appends a new **http** column containing the **http\_response** variable value

**Bot Config Example**  

<?xml version="1.0" encoding="UTF-8"?>  

<config>  

```
<!--defining variable-->  

    <var-def name="http\_response">  

    <!--passing the appropriate value from url\_to\_check column in input data file as a parameter for http plugin-->  

    <http url="${url\_to\_check}">
    
    </http>     
    
    </var-def>  
  
    <!--exporting all original input columns-->  

    <export include-original-data="true">  

    <!--adding a new column with the http plugin result to the export file-->          <single-column name="http" value="${http\_response}"/>     </export>  

</config> 
