# IAM Overview

EnOS Identity and Access Management (IAM) helps you manage user identities and control access to your resources in EnOS. IAM allows you to manage user account lifecycle, authenticate user identities, and control the access rights to the resources in EnOS. When multiple users exist in an organization unit, minimum permission principle can be enforced to reduce risks to your enterprise information security.

EnOS applies the identity and access management (IAM) scheme to achieve multi-tenancy. In EnOS, each tenant is managed as an organizational unit.  Data that belongs to different organizations are securely segregated and can only be accessed by users that are registered to the organization.

IAM also ensures that a user can access only resources that the user is authorized to access. This is achieved through properly group users and assigning proper access permissions.

The built-in IAM schemes of EnOS provide capabilities of identity management, authentication, and authorization.

## Identity Management

With IAM, a hierarchy structure is introduced to represent the relationship that exists within an organization. Each tenant is identified as an organizational unit (OU).

EnOS offers the following types of identities:
- *User accounts* are usually created for EnOS Console users and operation staff.
- *Service accounts* (a.k.a. Application tokens) are assigned to applications, for accessing the EnOS service APIs.
- *Device identities* are assigned to all devices (including edge devices) that connect to the EnOS Cloud.

All identities are created under organizations. Among the types of user identities, EnOS provides several types of user accounts. For more information, see [IAM Concepts](iam_concepts).

## Authentication

IAM provides different authentication methods for different account types.

- User accounts are authenticated through valid credentials (username and password). Strong password with required complexity is enforced by security policy managed by OU administrators. Multi-factor authentication is available as a configurable security option.

- Service accounts use access keys (i.e. digital signatures) to be authenticated by EnOS. For more information, see [Application Development Overview](https://docs.eniot.io/docs/app-development/en/latest/app_dev_overview.html).

- Devices and edges use X.509 certifications to establish the secure data communication tunnels with EnOS Cloud. For more information, see [Best Practice for Securing Communications between Edge Gateways and EnOS IoT Hub with X.509 Certificates](https://docs.eniot.io/docs/enos/en/latest/security/x509_ca/secure_communication_iothub.html).<!--Devices with TPM chips will be authenticated with its encrypted certifications stored in the hardware.-->

## Authorization

EnOS adopts Role-Based-Access-Control (RBAC) that is a policy neutral access control mechanism defined around roles and privileges. Access control rule is defined as a 3-tuples in the form of role-permission-resource. The resource includes the following:

- Applications: applications that a role has access to
- User Interface: menu items or buttons that a role can see
- API: APIs that a role can invoke<!--EnOS 1.1是否支持-->
- Data: data that a role can read or write<!--EnOS 1.1是否支持-->
- Reports: reports that a role can read<!--EnOS 1.1是否支持-->
- Events: events from an application that a role can view or handle<!--EnOS 1.1是否支持-->

IAM allows OU administrator to define access control rules to grant privileges/permissions of resources to other accounts through the EnOS Console GUI or through the APIs.

Accounts with ![ia](./media/authorization.png) proper privileges granted may access the corresponding resources via EnOS service APIs or EnOS Console. Access control validation is performed by IAM service for each access attempt.



| table | table12 |
| --- | --- |
| n1 | n2 |
