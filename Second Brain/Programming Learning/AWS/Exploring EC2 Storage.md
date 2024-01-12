Elastic Block Storage (EBS):
	- EBS provides persistent block storage volumes for EC2 instances
	- Highly available and durable
		- Suited for EC2 instances
		- Ensures data is preserved even if the instance crashes
	- Scalability
		- Expands on the fly without any downtime
		- Can take backups and also use the backups to create new volumes
- EBS Use Cases:
	- Hosting relational or NoSQL databases
	- Data warehousing and big data analytics
	- ERP and CRM application

Elastic File System (EFS):
- Scalable file storage system for EC2 and other AWS services.
	- Fully managed
		- Removes the complexity of deploying and maintaining file systems.
	- Scales Automatically
		- Automatically scales on demand without disrupting applications.
	- Concurrent Access
		- Multiple EC2 instances can access an EFS system simultaneously.
- EFS Use Cases:
	- Content management and web serving
	- Data analytics applications
	- Development and testing environments.

Instance Stores:
- Provide temporary block level storage directly attached to the EC2 instance.
- Storage is ephemeral and its ideal for temporary data.
- Key Features:
	- High I.O Performance
		- Offers very high input/output operations per second.
		- Temporary Storage
			- Data is lost if the instance is stopped
		- No Extra Cost
			- Come as part of the instance
- Instance Stores Use Cases:
	- Temporary storage of cache and buffers
	- Write and discard large amounts of data
	- Storage for application that replicate data across multiple instances