---
# **efieldrestful project documentation**
---
## How to get started and get set up with the proper configuration
0. *[Download and setup mongodb](https://docs.mongodb.com/manual/administration/install-community/)*
1. *[Download and install golang](https://golang.org/doc/install)*
2. *Clone the repository*
3. *Go into the efieldrestful root directory*
4. *Make sure the configuration file is correct*

      | Configuration Key | Key Description |
      | ----------- | ----------- |
      | address | This is the address the web server will bind to, the default value is "127.0.0.1" |
      | port | This is the port the web server will listen and serve on, the default value is "8080" |
      | uri | This is the complete mongodb uri connection string, the default value is "mongodb://localhost:27017" (Make sure to setup authentication on your database) |
      | dbName | This is the name of the database the application will use to store it's data in, the default names are "efield-dev" and "efield-prod" |
      
      >**The proper naming convention for configuration files is config.(your profile(dev, prod, qa)).json which is located and to be created in the config directory in the root of the project.**
      ---
      >**The default configuration profiles that may be edited are config.dev.json, and config.prod.json**
      ---
 5. *Now that your configuration is properly setup, you can then proceed to either build the main file as an executable or run the main.go file*
 
 ## Environment flag for configs
 >When running the project you can specify the config file to use, by default the dev config is chosen if one is not provided. The "-env" flag is equal to extracting `filename.split(".")[1]` from the names of the files in the config directory.
 ---
 >**Example: "-env=prod" --> "config.prod.json" and "-env=dev" --> "config.dev.json" and so on.**
 ---
 ## How to build the project as an executable
  - Make sure to be in the root directory of the project
  - Run `go build main.go`
  - This should produce an executable with the name "main"
  
 ## How to run the project
 ***As an executable***
  - `./main -env=dev`
  - `./main -env=prod`
 ---
 ***From the main.go file***
  - `go run main.go -env=dev`
  - `go run main.go -env=prod`
 ---
 # **efieldrestful api documentation**
 ---
 # Api Models
   ## Attempt Struct
  | Field Name | Description | Json Identifier |
  | ----------- | ----------- | ----------- |
  | `AttemptId` | The uuid of the attempt | `_id` |
  | `Level` | The level the user was on | `level` |
  | `Track` | The track the user was on | `track` |
  | `StarsCollected` | The amount of stars collected on the attempt | `stars_collected` |
  | `Score` | The score obtained on the attempt | `score` |
  | `Time` | The duration of the attempt in seconds | `time` |
  | `Timestamp` | A human readable timestamp in the form of a date | `timestamp` |
 
   ## Device Struct
  | Field Name | Description | Json Identifier |
  | ----------- | ----------- | ----------- |
  | `DeviceId` | The uuid of the device | `_id` |
  | `StudentName` | The name of the student on this device | `student_name` |
  | `Attempts` | An array of attempts associated with this device | `attempts` |
  
   ## Class Struct
  | Field Name | Description | Json Identifier |
  | ----------- | ----------- | ----------- |
  | `ClassId` | The uuid of the class | `_id` |
  | `ClassName` | The name of the class | `class_name` |
  | `AccessCode` | The access code of the class | `access_code` |
  | `Devices` | The track the user was on | `devices` |
---
