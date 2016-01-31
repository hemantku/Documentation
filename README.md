# TabInsight
#### Providing analytical insight in to Handheld Devices


## Underlying Idea

Handheld devices such as tablets have huge potential to revolutionize the classroom and enhance whole learnng process.
Governments and Non Profit Organizations are now providing school students  with handheld devices as way of augmenting the learning process or in some cases to replace text books (<a href="http://www.huffingtonpost.com/2013/03/06/textbooks-tablets_n_2816567.html"   target="_blank">more</a>)

The problem that TabInsight tries to solve is to track the tablet and app usage patterns so that Governments/ Organizations will have an insight into the usage patterns. (Don't get me wrong: no intrusion in to private space intended). By tracking usage patterns, Organizations will be able to determine how effective the learning apps are, understand how much they interest the students so that the ineffective apps can be swapped out for other similar apps. Tracking the tablet usuage patterns will help Organizations track when the handheld devices  are being used, which apps are being used when. This way they can ensure that the devices are being used for the intended purpose.

The text focuses entirely on how  tabinsight can be used in the education sector. Fortunately, TabInsight is versatile and not restricted to this use case. Any Organization that wants usage analytics on their devices can leverage this solution in some way.

## Demystifying TabInsight
### Building Blocks
* **Client App**

  Client App runs on the target device. The responsibilites of this app include:

    1. Runs a background service periodically to collect app usage information from device manager and stores this information in a light weight database (db) in the device
    2. Detect change in network connection status. Once, the app confirms that the device is connected to a WIFI network it queries the local db and tries to send this to the server. This is done record by record. The moment a record is sent to the server and the server acknowledges the receipt of the same, this record is deleted from the local db.
    
* **Server**

  The responsibilities of the server side components includes:

    1. Collect information payload from client devices
    2. Aggregate and publish data to the Data Analysis module
      
*  **Data Analysis and Dashboarding**

  The responsibilities of the Data Analysis module include:
    1. Ingests data from server
    2. Publish processed data  to a data store
    3. Provide dashboarding services based on data from the data store
    

### Under the hood
![alt text](../master/resources/tabinsight_architecture.png "TabInsight Architecture")

### Constituent Projects

#### <a href="https://github.com/TabInsight/TabInsight-Android"  target="_blank">1. Client Android App</a>

#### <a href="https://github.com/TabInsight/TabInsight-Server-Nodejs"  target="_blank">2. Nodejs Server App</a>

#### <a href="https://github.com/TabInsight/TabInsight-Server/tree/master/elk_installers"  target="_blank">3. ELK Setup</a>

### Contributing
[TODO]


