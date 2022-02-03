*Hi! Here is a document that you need to review. Please convert this document to Markdown using the editor of your choice (Atom, Sublime Text, etc.). Then, submit your Markdown file to github.com. To do this, you may need to create an account and a repository. Note that the repository needs to be public so we can review your work.*  

**Intelligent Automation Cloud Version 10.2**

**RELEASE DATE** October 30, 2020

Increase you productivity and simplify your work with the new Intelligent Automation Cloud v.10.2. Beyond helpful bug fixes, improvements, and deprecations that address user requests and solve earlier flaws, the highlights of this release include:

- **WorkSpace 2.0** -- a human-in-the-loop tool, tackles exception-handling issue, allowing faster completion and improving compliance. Compared to the previous version, WorkSpace 2.0 is strengthened with a feature that enables you to manipulate and adjust the workflow.** 
- **New A/B testing** -- allows you to improve your pre-trained bots performance by helping you validate automation variations, review Analytics dashboards, and choose the most confident automation version. 
- **Automated retraining** -- allows you to start retraining on a collected training set, know the estimated duration, and see Analytics for validating models. This bot retraining workflow is now available in the Control Tower UI to make it even more accessible to your business users.** 
- **Centralized user management and role-based access control** -- controls all the ecosystem components, including Analytics dashboards and WorkSpace.** 
- **Analytics** -- introduces 20 new data points, drill-down capability, improved navigation, and simplified, user-friendly analysis.** 
- **Intelligent Automation Cloud Developer** -- includes the new Launcher application for component management, as well as other improvements to your local development environment.** 
- **ML SDK extensions** -- addresses complex problems like hybrid models, grouping, and classification cascade training.** 
- **Optimized orchestration of services** -- allows you to reduce hardware requirements to 11 servers for a high-availability environment.** 

For more information on each improvement, see detailed descriptions below.

**A/B-testing of the Use Cases**

The A/B testing functionality enables you to easily test adjustments or new versions of automation and gather key metrics to determine whether to implement these changes.

The intuitive workflow makes the whole procedure easy to run, with data available for comparison after actual testing.

With the help of A/B tests, you can:

- safely run data, historical or live, through a new version without impacting the original version. 
- manage variations of business processes to be tested. 
- test updated manual task efficiency and routing. 
- automatically gather data to measure and compare two different versions. 
- analyze business metrics and compare versions. 

**Bug fixes**

**Infrastructure**

- Fixed an issue with Logstash startup failing and secrets not taken from Secrets Vault. 
- Fixed a bug with not working jobs when cloning from the current directory. 
- Fixed a certificate error with Logstash unable to start. 
- Fixed an issue on the "Run postmigrate SQL script" step. 
- Fixed an issue with ports prechecker not working when the FirewallD service blocks ports. 
- Fixed an issue with the update\_artifacts task failing when running on the HA environment. 
- Fixed a Liquibase error when upgrading. 
