This Solution Kit has been built and verified for Studio version 2024.2.1.

**Step 1: Set up Orchestrator**

*Create following resources in Orchestrator.*

*Assets:*
'AppiumURL' (text) => This can be found on the organization Appium instance
'UiBank Web Credentials' (credential) => username:S4H_SD_DEM password: Welcome1

The workflow assumes that these Assets have been placed in the 'Shared' folder. If you are placing in a different folder, then search for all 'Get Asset' and 'Get Credential' activities using the universal search and replace the Orchestrator Folder Path property.

*Test Data Queue:*
Open the Project Pane and expand the >Test Data section. Right-click 'TestData_LoanInformation_Test Data' and select 'Create Test Data Queue'. 
Name the test data queue --   UiBank Loan Test Data Queue 

**Step 2: Set up Data Service**

*Data Entity:*
Choose 'Import Schema'. Select the 'UiBankLoanDataSchema.json' in the Test Data folder.
Upload data to created entity. Sample data can be found in the Test Data folder titled, 'UiBankLoanData_UploadtoDataService.csv'. 

**Step 3: Set up Test Manager**

An overview of all the Requirements, Test Cases, and manual test steps can be found in the 'Test Manager Details' folder.
To set up test manager import the CrossBrowserTesting.tmh file to your test manager instance.

Connect to your own Test Manager instance and link Automated Test Cases to manual test case definitions.

**Potential Errors**
-> Package Confusion: If you share a Test Manger/Orchestrator instance with others that are demo-ing the same project, then there may be a duplication of Test IDs in different published .nukpg.  is recommended to alter the Test IDs for each TestCase.xaml. To do this, simply right-click each workflow, convert it to a workflow, and then convert it back to a test case. Alternatively, you can alter the TestID in the project.json. 
Note: If you do this, then you will have to 'Add Test Data' back to the data-driven tests.

Mess Up? Don't worry, you can rebase your project from Git.
