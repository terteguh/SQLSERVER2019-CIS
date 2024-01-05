
1 Installation, Updates and Patches 
1.1 Ensure Latest SQL Server Cumulative and Security Updates are Installed (Manual) 

```
SELECT SERVERPROPERTY('ProductLevel') as SP_installed, SERVERPROPERTY('ProductVersion') as Version;
```

1.2 Ensure Single-Function Member Servers are Used (Manual) 

2 Surface Area Reduction 
2.1 Ensure 'Ad Hoc Distributed Queries' Server Configuration Option is set to '0' (Automated) 

```
EXECUTE sp_configure 'show advanced options', 1; 
RECONFIGURE; 
EXECUTE sp_configure 'Ad Hoc Distributed Queries', 0; 
RECONFIGURE; 
GO 
EXECUTE sp_configure 'show advanced options', 0; 
RECONFIGURE;
```

2.2 Ensure 'CLR Enabled' Server Configuration Option is set to '0' (Automated) 

```
EXECUTE sp_configure 'clr enabled', 0; 
RECONFIGURE;
```

2.3 Ensure 'Cross DB Ownership Chaining' Server Configuration Option is set to '0' (Automated) 

```
EXECUTE sp_configure 'cross db ownership chaining', 0; 
RECONFIGURE; 
GO
```

2.4 Ensure 'Database Mail XPs' Server Configuration Option is set to '0' (Automated) 

```
EXECUTE sp_configure 'show advanced options', 1; 
RECONFIGURE; 
EXECUTE sp_configure 'Database Mail XPs', 0; 
RECONFIGURE; 
GO EXECUTE sp_configure 'show advanced options', 0; 
RECONFIGURE;
```

2.5 Ensure 'Ole Automation Procedures' Server Configuration Option is set to '0' (Automated) 
2.6 Ensure 'Remote Access' Server Configuration Option is set to '0' (Automated) 
2.7 Ensure 'Remote Admin Connections' Server Configuration Option is set to '0' (Automated) 
2.8 Ensure 'Scan For Startup Procs' Server Configuration Option is set to '0' (Automated) 
2.9 Ensure 'Trustworthy' Database Property is set to 'Off' (Automated) 
2.10 Ensure Unnecessary SQL Server Protocols are set to 'Disabled' (Manual) 
2.11 Ensure SQL Server is configured to use non-standard ports (Automated) 
2.12 Ensure 'Hide Instance' option is set to 'Yes' for Production SQL Server instances (Automated) 
2.13 Ensure the 'sa' Login Account is set to 'Disabled' (Automated) 
2.14 Ensure the 'sa' Login Account has been renamed (Automated) 
2.15 Ensure 'AUTO_CLOSE' is set to 'OFF' on contained databases (Automated) 
2.16 Ensure no login exists with the name 'sa' (Automated) 
2.17 Ensure 'clr strict security' Server Configuration Option is set to '1' (Automated) 

3 Authentication and Authorization 
3.1 Ensure 'Server Authentication' Property is set to 'Windows Authentication Mode' (Automated) 
3.2 Ensure CONNECT permissions on the 'guest' user is Revoked within all SQL Server databases (Automated) 
3.3 Ensure 'Orphaned Users' are Dropped From SQL Server Databases (Automated) 
3.4 Ensure SQL Authentication is not used in contained databases (Automated) 
3.5 Ensure the SQL Server’s MSSQL Service Account is Not an Administrator (Manual) 
3.6 Ensure the SQL Server’s SQLAgent Service Account is Not an Administrator (Manual) 
3.7 Ensure the SQL Server’s Full-Text Service Account is Not an Administrator (Manual) 
3.8 Ensure only the default permissions specified by Microsoft are granted to the public server role (Automated) 
3.9 Ensure Windows BUILTIN groups are not SQL Logins (Automated) 
3.10 Ensure Windows local groups are not SQL Logins (Automated) 
3.11 Ensure the public role in the msdb database is not granted access to SQL Agent proxies (Automated) 

4 Password Policies 
4.1 Ensure 'MUST_CHANGE' Option is set to 'ON' for All SQL Authenticated Logins (Manual) 
4.2 Ensure 'CHECK_EXPIRATION' Option is set to 'ON' for All SQL Authenticated Logins Within the Sysadmin Role (Automated) 
4.3 Ensure 'CHECK_POLICY' Option is set to 'ON' for All SQL Authenticated Logins (Automated) 

5 Auditing and Logging 
5.1 Ensure 'Maximum number of error log files' is set to greater than or equal to '12' (Automated) 
5.2 Ensure 'Default Trace Enabled' Server Configuration Option is set to '1' (Automated) 
5.3 Ensure 'Login Auditing' is set to 'failed logins' (Automated) 
5.4 Ensure 'SQL Server Audit' is set to capture both 'failed' and 'successful logins' (Automated) 

6 Application Development 
6.1 Ensure Database and Application User Input is Sanitized (Manual) 
6.2 Ensure 'CLR Assembly Permission Set' is set to 'SAFE_ACCESS' for All CLR Assemblies (Automated) 

7 Encryption 
7.1 Ensure 'Symmetric Key encryption algorithm' is set to 'AES_128' or higher in non-system databases (Automated) 
7.2 Ensure Asymmetric Key Size is set to 'greater than or equal to 2048' in non-system databases (Automated) 
7.3 Ensure Database Backups are Encrypted (Automated) 
7.4 Ensure Network Encryption is Configured and Enabled (Automated) 
7.5 Ensure Databases are Encrypted with TDE (Automated) 

8 Appendix: Additional Considerations 
8.1 Ensure 'SQL Server Browser Service' is configured correctly (Manual) 