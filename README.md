# Now Next Later X Feature Monte Carlo

### What is this report? 
This report will combine both a Now/Next/Later roadmap with a Feature Monte Carlo using your Azure DevOps data. It will allow you to see the future direction for your product/team whilst also being able to drill down into the 'Now' and provide dates for when delivery is likely to occur. 

### Why would you use it? 
Balance the need for focusing on outcomes and the 'big picture' whilst managing expectations around delivery. Crucially, this acknowledges a range of outcomes that can occur with delivery (by thinking probabilistically).

### When would you use it?
Use this when wanting to convey direction whilst also making stakeholders aware of when they can expect delivery for items in the 'now'.

### Prerequisites
* To get the best out of this template:
  - All work (Epics/Features/Stories) sits in the same ADO project and are 'owned' by a single team (i.e. not shared across multiple teams)
  - Your team regularly review and move work items (User Stories, PBIs, Features, Epics, etc.) to in progress (when started) and done (once complete)
  - Your Epics are articulated as outcomes and are tagged 'Now' / 'Next' / 'Later' depending on where they are in the roadmap
  - At all levels you always try to break work down to thin, vertical slices
  - For more info, please read the [accompanying blog](https://medium.com/@nbrown02/outcome-focused-roadmaps-and-feature-monte-carlo-unite-833a3bb4366b) first
* Download the template file:
  - [Azure DevOps / Azure DevOps Server / TFS version](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/raw/main/Capacity%20Planning%20&%20Feature%20Monte%20Carlo%20(ADO).pbit)
* Create/save an access token 
  - [Personal Access Token (PAT) if using Azure DevOps (make sure you have 'Read' Analytics access)](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows)
* Then you're good to get started!

### Connectivity (Azure DevOps Version)
* Open the .pbit file in Power BI Desktop
* Select http/https (only choose http if your Azure DevOps Server is HTTP)
* Add the Analytics / Azure DevOps Server URL - for Azure DevOps services enter 'analytics.dev.azure.com' / for Azure DevOps Server enter your server details
* Add your organization, project name and team name

Don't confuse the team name with the project name, a common mistake. If the URL you use is "http://dev.azure.com/Microsoft-UK/AzureDevOpsTeam/Database", then Microsoft-UK is the Organization Name, AzureDevOpsTeam is the Project name, Database is the team name.

* It should then look something like this:

![image](https://github.com/nbrown02/Capacity-Planning-Feature-Monte-Carlo/assets/29369962/16424b1e-e43e-44c9-b460-3f69c75e083e)

* Hit 'Load' 
* You will be prompted for a login, choose Basic and enter:
  - Your PAT you created in the Prerequisites in the password field
  - Leave the username as blank or enter 'Dummy'
  
![alt text](https://docs.microsoft.com/en-us/azure/devops/report/powerbi/media/authentication-7.png?view=azure-devops)

* Once signed in hit 'Load' and wait for your charts to populate!

## Using the report
There are a few different ways you can use each chart.

### Now Next Later

![image-20230922-111614](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/9031b0aa-3d5f-46a2-ac14-a52c486b608c)

We can use this visual to see, of our Epics, which is aligned with the different section in our roadmap. Each Epic is clickable to open in ADO

GIF

### Feature Monte Carlo
There are two main ways to use this report:

Better understand/manage expectations on delivery - by using this report you are able to define a target date and percentage likelihood outcome to aim for. You can play around with the drop down options for these two fields to see the different outcomes that could occur and how likely (or unlikely!) an outcome for a particular Feature is.

![1_Qy8ivTXv3DuBaZ1FOKY13w](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/fc51122d-1c68-4a15-a58a-67ba29491f52)

Understand the impact WIP has on delivery - the problem with forecasting at Feature level is that it typically assumes one feature is worked on sequentially in priority order by a team, which is simply not the reality we face. It is underestimated just how much of an impact Feature WIP has on teams. Even if a team is limiting WIP at story level, this is redundant for Feature throughput if WIP is not limited at the level above that. We can see the impact of this with a very quick example:

![1_P6Gk1x_ijr3t_Ca-hzhV3g](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/ae7ba0cc-c159-44b4-bad0-7d2a8e56f360)

This report also shows the number of Features without Child items (at PBI/Story level) and the number of unparented Features. 

IMAGE

Please note, the Feature priority order is determined from the priority order in the Feature backlog in ADO (any Features without children are skipped - can't simulate against 0 child items!).

### Now Next Later WITH Feature Monte Carlo

![image-20230922-111614](https://github.com/nbrown02/5-Minute-Capacity-Planning/assets/29369962/9031b0aa-3d5f-46a2-ac14-a52c486b608c)

For any Epics in the 'Now', a user can click on a row and the Feature Monte Carlo will dynamically update to show the Features that make up that Epic.

GIF

A user can then of course adjust the parameters if need be to see what would need to happen for those Features to become possible by the given date.
