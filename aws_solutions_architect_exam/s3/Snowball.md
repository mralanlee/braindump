# Snowball

Three different types of Snowball.
- Snowball
- Snowball Edge
- Snowmobile

### Before Snowball...
AWS had Import/Export where you sent in your own disks **CANNOT EXPORT TO GLACIER**

Petabyte-scale data transport devices that uses secure appliances to transfer large amounts of data into and out of AWS. Overcomes challenges of long transfer times, high network costs, and security concerns. Simple, fast, secure, and cost as little as one-fifth the cost of high-speed internet.

80TB snowball in all regions. Snowball uses multiple layers of security to protect data including...
- Tamper-resistant enclosures
- 256 bit encryption
- Industry-standard Trusted Platform Module (TPM) to ensure both security and full chain of custody of data.
- Once data transfer job is complete and verfied, AWS performs a software erase of the Snowball appliance.
- Comes with kindles, and can track where snowball is at any time.
- Import to S3 and export from S3

## Snowball Edge
Can contain 100TB of data with onboard storage and compute capabilities.
- Used to move large amounts of data into and out of AWS
- Temporary storage tier for large local datasets
- Support local workloads in remote or offline locations
- Connects to exisitng apps and infrastrucuture
  - Using standard storage interafces,
  - Streamlining data transfer process and minimizing setup and integration
- Can cluster to forma  local storage tier and process your data on-prem, helping apps continue to run even when they are not able to access the cloud.
- An AWS data center that you can use on prem

## Snowmobile
Petabytes or Exabytes of data. Can transfer up to 100PB per snowmobile. A 45-foot long ruggedized shipping container, pulled by a semi-trailer truck. 
