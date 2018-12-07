# Security Challenge

- The organization has TWO types of roles PER line of business: managers and analysts
- EACH line of business has a SINGLE managed database named after itself
- Managers can create and write tables on their own database and read data from all databases
- Analysts can only read data on their line of business database
- The data for each line of business will be encrypted in HDFS
- Create all the Sentry SQL you need to restrict access (you can name the groups, databases, roles, etc. whatever you want provided it is clear what each represents)
create role finance_managers;
create role finance_analysts;
create role HR_managers;
create role HR_analysts;
grant role managers to group managers;
grant role analysts to group analysts;
grant all on database managers to role managers;
grant select on database analysts to role managers;
grant select on database analysts to role analysts;



- Describe what is required to ensure data is encrypted and ensure managers and analysts can read data from HDFS and Hive

- Describe the capabilities of Navigator Audit, Lineage, and Metadata. What is it useful for?
Navigator Audit is very useful to know what the users are doing or trying to do, since it logs every single action the clients request and/or perform.
Lineage helps you understand better where the object came from and which objets are being created from it.
Metadata its very helpful to enhance the information with tags and descriptions, it can help a lot to search types of objects in a huge cluster.
Cloudera Navigator its useful for all the things I just explained and it has other capabilities such as policies which I haven't tried yet.

- Which technology would you use for encrypting Kafka, Kudu and Flume volumes?
NAVIGATOR ENCRYPT can be used in all these cases

YET TO BE FINISHED IN CAB
