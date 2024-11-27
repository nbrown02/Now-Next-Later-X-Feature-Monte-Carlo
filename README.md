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
* [Download the template file](https://github.com/nbrown02/Now-Next-Later-X-Feature-Monte-Carlo/raw/refs/heads/main/Now%20Next%20Later%20X%20Feature%20Monte%20Carlo.pbit)
* [Create/save an access token for ADO](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=Windows)
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

### Now Next Later Roadmap

![image](https://github.com/user-attachments/assets/acdf931c-039b-4822-8ec0-27bbddb4a3f7)

We can use this visual to see, of our Epics, which is aligned with the different section in our roadmap. Each Epic is clickable to open in ADO.

### Feature Monte Carlo
There are two main ways to use this report:

Better understand/manage expectations on delivery - by using this report you are able to define a target date and percentage likelihood outcome to aim for. You can play around with the drop down options for these two fields to see the different outcomes that could occur and how likely (or unlikely!) an outcome for a particular Feature is.

![FMC1](https://github.com/user-attachments/assets/797dc54e-f190-4151-ba86-72d34a879535)

Understand the impact WIP has on delivery - the problem with forecasting at Feature level is that it typically assumes one feature is worked on sequentially in priority order by a team, which is simply not the reality we face. It is underestimated just how much of an impact Feature WIP has on teams. Even if a team is limiting WIP at story level, this is redundant for Feature throughput if WIP is not limited at the level above that. This report also shows the number of Features without Child items (at PBI/Story level) and the number of unparented Features. 

![image](https://github.com/user-attachments/assets/a3ab257c-c5da-43dd-ba6a-405584d4de88)

Please note, the Feature priority order is determined from the priority order in the Feature backlog in ADO (any Features without children are skipped - can't simulate against 0 child items!).

### Now Next Later WITH Feature Monte Carlo

![FMC2](https://github.com/user-attachments/assets/31e85b20-bd0d-4291-a511-25b510881f0b)

For any Epics in the 'Now', a user can click on a row and the Feature Monte Carlo will dynamically update to show the Features that make up that Epic:

![FMC3](https://github.com/user-attachments/assets/5d715c4f-e496-4b6a-bed8-68906652dc81)

A user can then of course adjust the parameters if need be to see what would need to happen for those Features to become possible by the given date.
