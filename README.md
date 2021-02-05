# WonderRuleTool
A simple, configurable and expandable Service for recurring background Jobs. Made with Clean Architecture principles and .NET 5.0


## Configuration
Every Job is defined by a "[RuleName].rule" file. located in *WonderRuleTool/Rules* Folder. 
The Name of the File can be chosen without limitations as long as it ends up with ".rule". 

**Example**
```
NAME: "MyJobName"
RUNONSTART : True
EXECUTIONINTERVAL:"*/5 * * * *"
ACTIVE: True
METHOD : "FirstTestAction"
MAXERRORS: 3
RESETERRORSAFTERSUCCESFULEXECUTION: True
PARAMETERS: 
    AfterDate : LASTEXECUTION
    SecondParameter: Value1|Value2|Value3
```

**Parameter**

|Parameter|Description|Values|Mandatory|Default|
| ------------- |:-------------| -----:|-----:|-----:|
|NAME|The Name of the Rule|Text|Yes|-|
|RUNONSTART|Run the Method on Application Startup. Even if the planned execution was not yet due | True/False |Yes|False|
|EXECUTIONINTERVAL|The Interval of execution. [Crontab Syntax](https://en.wikipedia.org/wiki/Cron)|Crontab|Yes|* * * * * |
|ACTIVE|Activate or Deactivate the Rule|True/False|Yes|True|
|METHOD|The Name of the Class which has to be executed|Text|Yes|-|
|MAXERRORS|The maximum number of errors before this rule stops executing|Int|No|3|
|RESETERRORSAFTERSUCCESFULEXECUTION|Should the error counter be reset upon successful execution|True/False|No|True|
|PARAMETERS|The List of Parameters passed to the method|List|No|-|







(c) Sebastian Wolff , 2021

