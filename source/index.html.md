---
title: Redfish Schema

language tabs:
  - shell

search: true
---


# Introduction


Lucid brings clarity to your meetings by making it easy for everyone in an organization to run consistently successful meetings using your chosen process.


Template-driven processes give every meeting a quick start, with sensible defaults pre-filled, pre-formatted, and prepared for you. Step-by-step prompts and one-click access guide meeting leaders through prep to follow-up. Automated tracking, timing, and reminders keep everyone in synch.



# AccountService 1.0.2

This resource shall be used to represent a management account service for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **AccountLockoutCounterResetAfter** | number<br><br>*read-write* | This property shall reference the threshold of time in seconds from the last failed login attempt at which point the AccountLockoutThreshold counter (that counts number of failed login attempts) is reset back to zero (at which point AccountLockoutThreshold failures would be required before the account is locked).  This value shall be less than or equal to AccountLockoutDuration. The threshold counter also resets to zero after each successful login. |
| **AccountLockoutDuration** | number, null<br><br>*read-write* | This property shall reference the period of time in seconds that an account is locked after the number of failed login attempts reaches the threshold referenced by AccountLockoutThreshold, within the window of time referenced by AccountLockoutCounterResetAfter.  The value shall be greater than or equal to the value of AccountLockoutResetAfter.  If set to 0, no lockout shall occur. |
| **AccountLockoutThreshold** | number, null<br><br>*read-write* | This property shall reference the threshold of failed login attempts at which point the user's account is locked.  If set to 0, no lockout shall ever occur. |
| **Accounts** { | object<br><br>*read-write* | This property shall contain the link to a collection of type ManagerAccountCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **AuthFailureLoggingThreshold** | number<br><br>*read-write* | This property shall reference the threshold for when an authorization failure is logged.  This represents a modulo function value, thus the failure shall be logged every nth occurrence where n represents the value of this property. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **MaxPasswordLength** | number<br><br>*read-only* | This property shall reference the maximum password length that the implementation will allow a password to be set to. |
| **MinPasswordLength** | number<br><br>*read-only* | This property shall reference the minimum password length that the implementation will allow a password to be set to. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Roles** { | object<br><br>*read-write* | This property shall contain the link to a collection of type RoleCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# AttributeRegistry 1.0.0

This resource shall be used to represent an Attribute registry for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Language** | string<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OwningEntity** | string<br><br>*read-only* | The value of this property shall be a string that represents the publisher of this registry. |
| **RegistryEntries** { | object<br><br>*read-write* | The value of this property shall a list of all attributes for this component, along with their possible values, dependencies, and other metadata. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Attributes** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array containing the attributes and their possible values and other metadata. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Dependencies** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array containing a list of dependencies of attributes on this component. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Menus** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array containing the attributes menus and their hierarchy. |
| } |   |   |
| **RegistryVersion** | string<br><br>*read-only* | The value of this property shall be the version of this attribute registry. The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification. |
| **SupportedSystems** [ { | array<br><br>*read-write* | The value of this property shall be an array containing a list of systems supported by this attribute registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProductName** | string, null<br><br>*read-only* | The version of the component firmware image that this registry applies to. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SystemId** | string, null<br><br>*read-only* | The value of this property shall be the system ID that identifies the computer system model that this registry applies to. |
| } ] |   |   |

# Bios 1.0.0

This resource shall be used to represent BIOS attributes for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ChangePassword** {} | object<br><br>*read-write* | This action shall perform a change of the selected BIOS password. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ResetBios** {} | object<br><br>*read-write* | This action shall perform a reset of the BIOS attributes to teir default values. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AttributeRegistry** | string, null<br><br>*read-write* | The reference to the Attribute Registry that lists the metadata describing the BIOS attribute settings in this resource. |
| **Attributes** {} | object<br><br>*read-write* | BIOS Attribute settings appear as additional properties in this object, and can be looked up in the Attribute Registry by their AttributeName. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# Chassis 1.2.0

This resource shall be used to represent a chassis or other physical enclosure for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Chassis.Reset** {} | object<br><br>*read-write* | This defines the name of the custom action supported on this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The value of this property shall be an identifying string used to track the chassis for inventory purposes. |
| **ChassisType** | string<br><br>*read-write* | ChassisType shall indicate the physical form factor for the type of chassis. *See Property Details, below, for more information about this property.* |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **IndicatorLED** | string, null<br><br>*read-write* | This value of this property shall contain the indicator light state for the indicator light associated with this system. *See Property Details, below, for more information about this property.* |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems** [ {} ] | array<br><br>*read-only* | The value of this property shall be a reference to the resource that this physical container is associated with and shall reference a resource of type ComputerSystem.  If a ComputerSystem is also referenced in a Chassis that is referenced in a Contains link from this resource, that ComputerSystem shall not be referenced in this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ContainedBy** {} | object<br><br>*read-write* | The value of this property shall be a reference to the resource that represents the chassis that contains this chassis and shall be of type Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains** [ {} ] | array<br><br>*read-only* | The value of this property shall be a reference to the resource that represents the chassis that this chassis contains and shall be of type Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that cools this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** [ {} ] | array<br><br>*read-only* | The value of this property shall reference one or more resources of type Drive that are in this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** [ {} ] | array<br><br>*read-only* | The value of this property shall be a reference to the resource that manages this chassis and shall reference a resource of type Manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis** [ {} ] | array<br><br>*read-only* | The value of this property shall reference one or more resources of type Manager that are in this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage** [ {} ] | array<br><br>*read-only* | The value of this property shall reference one or more resources of type Storage that are connected to or contained inside this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage\@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **Location** *(v1.2.0)* { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Info** | string, null<br><br>*read-only* | This property shall represent the location of the resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InfoFormat** | string, null<br><br>*read-only* | This property shall represent the format of the Info property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| } |   |   |
| **LogServices** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type LogServiceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Manufacturer** | string, null<br><br>*read-only* | The value of this property shall be the name of the organization responsible for producing the chassis. This organization might be the entity from whom the chassis is purchased, but this is not necessarily true. |
| **Model** | string, null<br><br>*read-only* | The value of this property shall be the name by which the manufacturer generally refers to the chassis. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **PartNumber** | string, null<br><br>*read-only* | The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the chassis. |
| **PhysicalSecurity** *(v1.1.0)* { | object<br><br>*read-write* | This value of this property shall contain the sensor state of the physical security. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensor** | string, null<br><br>*read-write* | This property shall represent the state of this physical security sensor.  Hardware intrusion indicates the internal hardware is detected as being accessed in an insecure state. Tampering detected indicates the physical tampering of the monitored entity is detected. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorNumber** | number, null<br><br>*read-only* | The value of this property shall be a numerical identifier for this physical security sensor that is unique within this resource.  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorReArm** | string, null<br><br>*read-write* | This property shall represent the method to set back to the Normal statue of this physical security sensor.  Manual indicates manual re-arm is needed.  Automatic indicates the state is restored automatically as no abnormal physical security conditions are detected. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Power** { | object<br><br>*read-write* | The value of this property shall be a reference to the resource that represents the power characteristics of this chassis and shall be of type Power. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl** [ {} ] | array<br><br>*read-write* | These properties shall be the definition for power control (power reading and limiting) for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies** [ {} ] | array<br><br>*read-write* | This object shall contain details of the power supplies associated with this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | Redundancy information for the power subsystem of this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages** [ {} ] | array<br><br>*read-write* | These properties shall be the definition for voltage sensors for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages\@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **PowerState** *(v1.0.1)* | string, null<br><br>*read-write* | The value of this property shall contain the power state of the chassis. *See Property Details, below, for more information about this property.* |
| **SKU** | string, null<br><br>*read-only* | The value of this property shall be the stock-keeping unit number for this chassis. |
| **SerialNumber** | string, null<br><br>*read-only* | The value of this property shall be a manufacturer-allocated number used to identify the chassis. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Thermal** { | object<br><br>*read-write* | The value of this property shall be a reference to the resource that represents the thermal characteristics of this chassis and shall be of type Thermal. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans** [ {} ] | array<br><br>*read-write* | These properties shall be the definition for fans for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | The values of the properties in this array shall be used to show redundancy for fans and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures** [ {} ] | array<br><br>*read-write* | These properties shall be the definition for temperature sensors for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures\@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |

## Property Details

### ChassisType:

| string | Description |
| --- | --- |
| Blade | An enclosed or semi-enclosed, typically vertically-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Card | A loose device or circuit board intended to be installed in a system or other enclosure |
| Cartridge | A small self-contained system intended to be plugged into a multi-system chassis |
| Component | A small chassis, card, or device which contains devices for a particular subsystem or function |
| Drawer | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which may be slid into a multi-system chassis. |
| Enclosure | A generic term for a chassis that does not fit any other description |
| Expansion | A chassis which expands the capabilities or capacity of another chassis |
| Module | A small, typically removable, chassis or card which contains devices for a particular subsystem or function |
| Other | A chassis that does not fit any of these definitions |
| Pod | A collection of equipment racks in a large, likely transportable, container |
| Rack | An equipment rack, typically a 19-inch wide freestanding unit |
| RackMount | A single system chassis designed specifically for mounting in an equipment rack |
| Row | A collection of equipment racks |
| Shelf | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Sidecar | A chassis that mates mechanically with another chassis to expand its capabilities or capacity |
| Sled | An enclosed or semi-enclosed, system chassis which must be plugged into a multi-system chassis to function normally similar to a blade type chassis. |
| StandAlone | A single, free-standing system, commonly called a tower or desktop chassis |
| Zone | A logical division or portion of a physical chassis that contains multiple devices or systems that cannot be physically separated |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |
| Unknown | The state of the Indicator LED cannot be determined. Deprecated: Return null if state is unknown. |

### IntrusionSensor:

| string | Description |
| --- | --- |
| HardwareIntrusion | A door, lock, or other mechanism protecting the internal system hardware from being accessed is detected as being in an insecure state. |
| Normal | No abnormal physical security conditions are detected at this time. |
| TamperingDetected | Physical tampering of the monitored entity is detected. |

### IntrusionSensorReArm:

| string | Description |
| --- | --- |
| Automatic | This sensor would be restored to the Normal state automatically as no abnormal physical security conditions are detected. |
| Manual | This sensor would be restored to the Normal state by a manual re-arm. |

### PowerState:

| string | Description |
| --- | --- |
| Off | The components within the chassis has no power, except some components may continue to have AUX power such as management controller. |
| On | The components within the chassis has power on. |
| PoweringOff | A temporary state between On and Off. The components within the chassis can take time to process the power off action. |
| PoweringOn | A temporary state between Off and On. The components within the chassis can take time to process the power on action. |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# ChassisCollection

A Collection of Chassis resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssetTag** | string, null<br><br>*read-write* | The value of this property shall be an identifying string used to track the chassis for inventory purposes. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ChassisType** | string<br><br>*read-write* | ChassisType shall indicate the physical form factor for the type of chassis. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IndicatorLED** | string, null<br><br>*read-write* | This value of this property shall contain the indicator light state for the indicator light associated with this system. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LogServices** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type LogServiceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | The value of this property shall be the name of the organization responsible for producing the chassis. This organization might be the entity from whom the chassis is purchased, but this is not necessarily true. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | The value of this property shall be the name by which the manufacturer generally refers to the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PhysicalSecurity** {} | object<br><br>*read-write* | This value of this property shall contain the sensor state of the physical security. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Power** {} | object<br><br>*read-write* | The value of this property shall be a reference to the resource that represents the power characteristics of this chassis and shall be of type Power. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerState** | string, null<br><br>*read-write* | The value of this property shall contain the power state of the chassis. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SKU** | string, null<br><br>*read-only* | The value of this property shall be the stock-keeping unit number for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | The value of this property shall be a manufacturer-allocated number used to identify the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Thermal** {} | object<br><br>*read-write* | The value of this property shall be a reference to the resource that represents the thermal characteristics of this chassis and shall be of type Thermal. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### ChassisType:

| string | Description |
| --- | --- |
| Blade | An enclosed or semi-enclosed, typically vertically-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Card | A loose device or circuit board intended to be installed in a system or other enclosure |
| Cartridge | A small self-contained system intended to be plugged into a multi-system chassis |
| Component | A small chassis, card, or device which contains devices for a particular subsystem or function |
| Drawer | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which may be slid into a multi-system chassis. |
| Enclosure | A generic term for a chassis that does not fit any other description |
| Expansion | A chassis which expands the capabilities or capacity of another chassis |
| Module | A small, typically removable, chassis or card which contains devices for a particular subsystem or function |
| Other | A chassis that does not fit any of these definitions |
| Pod | A collection of equipment racks in a large, likely transportable, container |
| Rack | An equipment rack, typically a 19-inch wide freestanding unit |
| RackMount | A single system chassis designed specifically for mounting in an equipment rack |
| Row | A collection of equipment racks |
| Shelf | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Sidecar | A chassis that mates mechanically with another chassis to expand its capabilities or capacity |
| Sled | An enclosed or semi-enclosed, system chassis which must be plugged into a multi-system chassis to function normally similar to a blade type chassis. |
| StandAlone | A single, free-standing system, commonly called a tower or desktop chassis |
| Zone | A logical division or portion of a physical chassis that contains multiple devices or systems that cannot be physically separated |

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |
| Unknown | The state of the Indicator LED cannot be determined. Deprecated: Return null if state is unknown. |

### PowerState:

| string | Description |
| --- | --- |
| Off | The components within the chassis has no power, except some components may continue to have AUX power such as management controller. |
| On | The components within the chassis has power on. |
| PoweringOff | A temporary state between On and Off. The components within the chassis can take time to process the power off action. |
| PoweringOn | A temporary state between Off and On. The components within the chassis can take time to process the power on action. |


# ComputerSystem 1.1.0

This resource shall be used to represent resources that represent a computing system in the Redfish specification.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#ComputerSystem.Reset** {} | object<br><br>*read-write* | This action shall perform a reset of the ComputerSystem.  For systems which implement APCI Power Button functionality, the PushPowerButton value shall perform or emulate an ACPI Power Button push.  The ForceOff value shall remove power from the system or perform an ACPI Power Button Override (commonly known as a 4-second hold of the Power Button).  The ForceRestart value shall perform a ForceOff action followed by a On action. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The value of this property shall contain the value of the asset tag of the system. |
| **Bios** *(v1.1.0)* { | object<br><br>*read-write* | The value of this property shall be a link to a resource of type Bios that lists the BIOS settings for this system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AttributeRegistry** | string, null<br><br>*read-write* | The reference to the Attribute Registry that lists the metadata describing the BIOS attribute settings in this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Attributes** {} | object<br><br>*read-write* | BIOS Attribute settings appear as additional properties in this object, and can be looked up in the Attribute Registry by their AttributeName. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **BiosVersion** | string, null<br><br>*read-write* | The value of this property shall be the version string of the currently installed and running BIOS (for x86 systems).  For other systems, the value may contain a version string representing the primary system firmware. |
| **Boot** { | object<br><br>*read-write* | This object shall contain properties which describe boot information for the current resource. Changes to this object do not alter the BIOS persistent boot order configuration. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BootSourceOverrideEnabled** | string, null<br><br>*read-write* | The value of this property shall be Once if this is a one time boot override and Continuous if this selection should remain active until cancelled. If the property value is set to Once, the value will be reset back to Disabled after the BootSourceOverrideTarget actions have been completed. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BootSourceOverrideMode** | string, null<br><br>*read-write* | The value of this property shall be Legacy for non-UEFI BIOS boot or UEFI for UEFI boot from boot source specified in BootSourceOverrideTarget property. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BootSourceOverrideTarget** | string, null<br><br>*read-write* | The value of this property shall contain the source to boot the system from, overriding the normal boot order. The valid values for this property are specified through the Redfish.AllowableValues annotation. Pxe indicates to PXE boot from the primary NIC; Floppy, Cd, Usb, Hdd indicates to boot from their devices respectively. BiosSetup indicates to boot into the native BIOS screen setup. Utilities and Diags indicate to boot from the local utilities or diags partitions and UefiTarget indicates to boot from the UEFI device path found in UefiTargetBootSourceOverride. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UefiTargetBootSourceOverride** | string, null<br><br>*read-write* | The value of this property shall be the UEFI device path of the override boot target. The valid values for this property are specified through the Redfish.AllowableValues annotation. BootSourceOverrideEnabled = Continuous is not supported for UEFI Boot Source Override as this setting is defined in UEFI as a one time boot only. |
| } |   |   |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EthernetInterfaces** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type EthernetInterfaceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **HostName** | string, null<br><br>*read-write* | The value of this property shall be the host name for this system, as reported by the operating system or hypervisor.  This value is typically provided to the Manager by a service running in the host operating system. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **IndicatorLED** | string, null<br><br>*read-write* | The value of this property shall contain the indicator light state for the indicator light associated with this system. *See Property Details, below, for more information about this property.* |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis** [ {} ] | array<br><br>*read-only* | The value of this property shall reference a resource of type Chassis that represents the physical container associated with this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this computer system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** [ {} ] | array<br><br>*read-only* | The value of this property shall reference a resource of type manager that represents the resource with management responsibility for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this computer system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy\@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **LogServices** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type LogServiceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Manufacturer** | string, null<br><br>*read-only* | The value of this property shall contain a value that represents the manufacturer of the system. |
| **Memory** *(v1.1.0)* { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type MemoryCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **MemorySummary** { | object<br><br>*read-write* | This object shall contain properties which describe the central memory for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryMirroring** | string, null<br><br>*read-write* | This property shall contain the ability and type of memory mirring supported by this system. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TotalSystemMemoryGiB** | number, null<br><br>*read-only* | This property shall contain the amount of system general purpose volatile (RAM) memory as measured in gibibytes. |
| } |   |   |
| **Model** | string, null<br><br>*read-only* | The value of this property shall contain the information about how the manufacturer references this system. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **PartNumber** | string, null<br><br>*read-only* | The value of this property shall contain the part number for the system as defined by the manufacturer. |
| **PowerState** | string, null<br><br>*read-write* | The value of this property shall contain the power state of the system. *See Property Details, below, for more information about this property.* |
| **ProcessorSummary** { | object<br><br>*read-write* | This object shall contain properties which describe the central processors for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Count** | number, null<br><br>*read-only* | This property shall contain the number of central processors in the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This property shall contain the processor model for the central processors in the system, per the description in Table 22 of the SMBIOS Specification DSP0134 2.8 or later. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } |   |   |
| **Processors** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type ProcessorCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **SKU** | string, null<br><br>*read-only* | The value of this property shall contain the Stock Keeping Unit (SKU) for the system. |
| **SecureBoot** *(v1.1.0)* { | object<br><br>*read-write* | The value of this property shall be a link to a resource of type SecureBoot. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootCurrentBoot** | string, null<br><br>*read-write* | The value of this property shall indicate the UEFI Secure Boot state during the current boot cycle. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootEnable** | boolean, null<br><br>*read-write* | Setting this property to true enables UEFI Secure Boot, and setting it to false disables it. This property can be enabled only in UEFI boot mode. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootMode** | string, null<br><br>*read-write* | This property shall contain the current Secure Boot mode, as defined in the UEFI Specification. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **SerialNumber** | string, null<br><br>*read-only* | The value of this property shall contain the serial number for the system. |
| **SimpleStorage** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type SimpleStorageCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Storage** *(v1.1.0)* { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type StorageCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **SystemType** | string<br><br>*read-write* | An enumeration that indicates the kind of system that this resource represents. *See Property Details, below, for more information about this property.* |
| **TrustedModules** *(v1.1.0)* [ { | array<br><br>*read-write* | This object shall contain an array of objects with properties which describe the truted modules for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FirmwareVersion** | string, null<br><br>*read-only* | This property shall contain the firwmare version as defined by the manufacturer for the Trusted Module. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InterfaceType** | string, null<br><br>*read-write* | This property shall contain the interface type of the installed Trusted Module. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } ] |   |   |
| **UUID** | string, null<br><br>*read-write* | The value of this property shall be used to contain a universal unique identifier number for the system. RFC4122 describes methods that can be used to create the value. The value should be considered to be opaque. Client software should only treat the overall value as a universally unique identifier and should not interpret any sub-fields within the UUID. If the system supports SMBIOS, the value and byte order of the property should match byte-for-byte with the memory byte order (from lowest address to highest) of the SMBIOS UUID. Following this order will make it simpler to correlate the UUID with the SMBIOS UUID |

## Property Details

### BootSourceOverrideEnabled:

| string | Description |
| --- | --- |
| Continuous | The system will boot to the target specified in the BootSourceOverrideTarget until this property is set to Disabled. |
| Disabled | The system will boot normally. |
| Once | On its next boot cycle, the system will boot (one time) to the Boot Source Override Target. The value of BootSourceOverrideEnabled is then reset back to Disabled. |

### BootSourceOverrideMode:

| string | Description |
| --- | --- |
| Legacy | The system will boot in non-UEFI boot mode to the Boot Source Override Target. |
| UEFI | The system will boot in UEFI boot mode to the Boot Source Override Target. |

### BootSourceOverrideTarget:

| string | Description |
| --- | --- |
| BiosSetup | Boot to the BIOS Setup Utility |
| Cd | Boot from the CD/DVD disc |
| Diags | Boot the manufacturer's Diagnostics program |
| Floppy | Boot from the floppy disk drive |
| Hdd | Boot from a hard drive |
| None | Boot from the normal boot device |
| Pxe | Boot from the Pre-Boot EXecution (PXE) environment |
| SDCard | Boot from an SD Card |
| UefiHttp | Boot from a UEFI HTTP network location |
| UefiShell | Boot to the UEFI Shell |
| UefiTarget | Boot to the UEFI Device specified in the UefiTargetBootSourceOverride property |
| Usb | Boot from a USB device as specified by the system BIOS |
| Utilities | Boot the manufacturer's Utilities program(s) |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |
| Unknown | The state of the Indicator LED cannot be determined. Deprecated: Return null if state is unknown. |

### InterfaceType:

| string | Description |
| --- | --- |
| TCM1_0 | Trusted Cryptography Module (TCM) 1.0 |
| TPM1_2 | Trusted Platform Module (TPM) 1.2 |
| TPM2_0 | Trusted Platform Module (TPM) 2.0 |

### MemoryMirroring:

| string | Description |
| --- | --- |
| DIMM | The system supports DIMM mirroring at the DIMM level.  Individual DIMMs can be mirrored. |
| Hybrid | The system supports a hybrid mirroring at the system and DIMM levels.  Individual DIMMs can be mirrored. |
| None | The system does not support DIMM mirroring. |
| System | The system supports DIMM mirroring at the System level.  Individual DIMMs are not paired for mirroring in this mode. |

### PowerState:

| string | Description |
| --- | --- |
| Off | The system is powered off, although some components may continue to have AUX power such as management controller. |
| On | The system is powered on. |
| PoweringOff | A temporary state between On and Off. The power off action can take time while the OS is in the shutdown process. |
| PoweringOn | A temporary state between Off and On. This temporary state can be very short. |

### SecureBootCurrentBoot:

| string | Description |
| --- | --- |
| Disabled | Secure Boot is currently disabled. |
| Enabled | Secure Boot is currently enabled. |

### SecureBootMode:

| string | Description |
| --- | --- |
| AuditMode | Secure Boot is currently in Audit Mode. |
| DeployedMode | Secure Boot is currently in Deployed Mode. |
| SetupMode | Secure Boot is currently in Setup Mode. |
| UserMode | Secure Boot is currently in User Mode. |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |

### SystemType:

| string | Description |
| --- | --- |
| OS | An operating system instance |
| Physical | A computer system |
| PhysicallyPartitioned | A hardware-based partition of a computer system |
| Virtual | A virtual machine instance running on this system |
| VirtuallyPartitioned | A virtual or software-based partition of a computer system |


# ComputerSystemCollection

A Collection of ComputerSystem resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssetTag** | string, null<br><br>*read-write* | The value of this property shall contain the value of the asset tag of the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Bios** {} | object<br><br>*read-write* | The value of this property shall be a link to a resource of type Bios that lists the BIOS settings for this system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BiosVersion** | string, null<br><br>*read-write* | The value of this property shall be the version string of the currently installed and running BIOS (for x86 systems).  For other systems, the value may contain a version string representing the primary system firmware. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Boot** {} | object<br><br>*read-write* | This object shall contain properties which describe boot information for the current resource. Changes to this object do not alter the BIOS persistent boot order configuration. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EthernetInterfaces** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type EthernetInterfaceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HostName** | string, null<br><br>*read-write* | The value of this property shall be the host name for this system, as reported by the operating system or hypervisor.  This value is typically provided to the Manager by a service running in the host operating system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IndicatorLED** | string, null<br><br>*read-write* | The value of this property shall contain the indicator light state for the indicator light associated with this system. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LogServices** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type LogServiceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | The value of this property shall contain a value that represents the manufacturer of the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Memory** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type MemoryCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemorySummary** {} | object<br><br>*read-write* | This object shall contain properties which describe the central memory for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | The value of this property shall contain the information about how the manufacturer references this system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | The value of this property shall contain the part number for the system as defined by the manufacturer. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerState** | string, null<br><br>*read-write* | The value of this property shall contain the power state of the system. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProcessorSummary** {} | object<br><br>*read-write* | This object shall contain properties which describe the central processors for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Processors** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type ProcessorCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SKU** | string, null<br><br>*read-only* | The value of this property shall contain the Stock Keeping Unit (SKU) for the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBoot** {} | object<br><br>*read-write* | The value of this property shall be a link to a resource of type SecureBoot. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | The value of this property shall contain the serial number for the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SimpleStorage** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type SimpleStorageCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type StorageCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SystemType** | string<br><br>*read-write* | An enumeration that indicates the kind of system that this resource represents. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TrustedModules** [ {} ] | array<br><br>*read-write* | This object shall contain an array of objects with properties which describe the truted modules for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UUID** | string, null<br><br>*read-write* | The value of this property shall be used to contain a universal unique identifier number for the system. RFC4122 describes methods that can be used to create the value. The value should be considered to be opaque. Client software should only treat the overall value as a universally unique identifier and should not interpret any sub-fields within the UUID. If the system supports SMBIOS, the value and byte order of the property should match byte-for-byte with the memory byte order (from lowest address to highest) of the SMBIOS UUID. Following this order will make it simpler to correlate the UUID with the SMBIOS UUID |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |
| Unknown | The state of the Indicator LED cannot be determined. Deprecated: Return null if state is unknown. |

### PowerState:

| string | Description |
| --- | --- |
| Off | The system is powered off, although some components may continue to have AUX power such as management controller. |
| On | The system is powered on. |
| PoweringOff | A temporary state between On and Off. The power off action can take time while the OS is in the shutdown process. |
| PoweringOn | A temporary state between Off and On. This temporary state can be very short. |

### SystemType:

| string | Description |
| --- | --- |
| OS | An operating system instance |
| Physical | A computer system |
| PhysicallyPartitioned | A hardware-based partition of a computer system |
| Virtual | A virtual machine instance running on this system |
| VirtuallyPartitioned | A virtual or software-based partition of a computer system |


# Drive 1.0.0

This resource shall be used to represent a disk drive or other physical storage medium for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Drive.SecureErase** {} | object<br><br>*read-write* | This defines the name of the custom action supported on this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The value of this property shall be an identifying string used to track the drive for inventory purposes. |
| **BlockSizeBytes** | number, null<br><br>*read-only* | This property shall contain size of the smallest addressible unit of the associated drive. |
| **CapableSpeedGbs** | number, null<br><br>*read-only* | This property shall contain fastest capable bus speed of the associated drive. |
| **CapacityBytes** | number, null<br><br>*read-only* | This property shall contain the raw size in bytes of the associated drive. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EncryptionAbility** | string, null<br><br>*read-write* | This property shall contain the encryption ability for the associated drive. *See Property Details, below, for more information about this property.* |
| **EncryptionStatus** | string, null<br><br>*read-write* | This property shall contain the encrytion status for the associated drive. *See Property Details, below, for more information about this property.* |
| **FailurePredicted** | boolean, null<br><br>*read-only* | This property shall contain failure information as defined by the manufacturer for the associated drive. |
| **HotspareType** | string, null<br><br>*read-write* | This property shall contain the hot spare type for the associated drive. If the drive is currently serving as a hot spare its Status.State field shall be 'StandbySpare' and 'Enabled' when it is being used as part of a Volume. *See Property Details, below, for more information about this property.* |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Identifiers** [ { | array<br><br>*read-only* | This property shall contain a list of all known durable names for the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DurableName** | string, null<br><br>*read-only* | This property shall contain the world wide unique identifier for the resource. The string shall be in the format described by the value of the Identifier.DurableNameFormat property |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DurableNameFormat** | string, null<br><br>*read-write* | This property shall represent the format of the DurableName property. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **IndicatorLED** | string, null<br><br>*read-write* | This value of this property shall contain the indicator light state for the indicator light associated with this drive. *See Property Details, below, for more information about this property.* |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes** [ {} ] | array<br><br>*read-only* | The value of this property shall be a reference to the resources that this drive is associated with and shall reference a resource of type Volume. This shall include all Volume resources of which this Drive is a member and all Volumes for which this Drive is acting as a spare if the HotspareType is Dedicated. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes\@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **Location** [ { | array<br><br>*read-only* | This property shall contain location information of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Info** | string, null<br><br>*read-only* | This property shall represent the location of the resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InfoFormat** | string, null<br><br>*read-only* | This property shall represent the format of the Info property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| } ] |   |   |
| **Manufacturer** | string, null<br><br>*read-only* | The value of this property shall be the name of the organization responsible for producing the drive. This organization might be the entity from whom the drive is purchased, but this is not necessarily true. |
| **MediaType** | string, null<br><br>*read-write* | This property shall contain the type of media contained in the associated drive. *See Property Details, below, for more information about this property.* |
| **Model** | string, null<br><br>*read-only* | The value of this property shall be the name by which the manufacturer generally refers to the drive. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **NegotiatedSpeedGbs** | number, null<br><br>*read-only* | This property shall contain current bus speed of the associated drive. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **PartNumber** | string, null<br><br>*read-only* | The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the drive. |
| **PredictedMediaLifeLeftPercent** | number, null<br><br>*read-only* | This property shall contain an indicator of the percentage of life remaining in the Drive's media. |
| **Protocol** | , null<br><br>*read-write* | This property shall contain the protocol the associated drive is using to communicate to the storage controller for this system. |
| **Revision** | string, null<br><br>*read-only* | This property shall contain the revision as defined by the manufacturer for the associated drive. |
| **RotationSpeedRPM** | number, null<br><br>*read-only* | This property shall contain rotation speed of the associated drive. |
| **SKU** | string, null<br><br>*read-only* | The value of this property shall be the stock-keeping unit number for this drive. |
| **SerialNumber** | string, null<br><br>*read-only* | The value of this property shall be a manufacturer-allocated number used to identify the drive. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **StatusIndicator** | string, null<br><br>*read-write* | The value of this property shall contain the status indicator state for the status indicator associated with this drive. The valid values for this property are specified through the Redfish.AllowableValues annotation. *See Property Details, below, for more information about this property.* |

## Property Details

### DurableNameFormat:

| string | Description |
| --- | --- |
| EUI | IEEE-defined 64-bit Extended Unique Identifier |
| FC_WWN | Fibre Channel World Wide Name |
| NAA | Name Address Authority Format |
| UUID | Universally Unique Identifier |
| iQN | iSCSI Qualified Name |

### EncryptionAbility:

| string | Description |
| --- | --- |
| None | The drive is not capable of self encryption |
| Other | The drive is capable of self encryption through some other means |
| SelfEncryptingDrive | The drive is capable of self encryption per the Trusted Computing Group's Self Encrypting Drive Standard |

### EncryptionStatus:

| string | Description |
| --- | --- |
| Foreign | The drive is currently encrypted, the data is not accessible to the user, and the system requires user intervention to expose the data |
| Locked | The drive is currently encrypted and the data is not accessible to the user, however the system has the ability to unlock the drive automatically |
| Unecrypted | The drive is not currently encrypted |
| Unlocked | The drive is currently encrypted but the data is accessible to the user unencrypted |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HotspareType:

| string | Description |
| --- | --- |
| Chassis | The drive is currently serving as a hotspare for all other drives in the chassis |
| Dedicated | The drive is currently serving as a hotspare for a user defined set of drives |
| Global | The drive is currently serving as a hotspare for all other drives in the storage system |
| None | The drive is not currently a hotspare |

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |

### MediaType:

| string | Description |
| --- | --- |
| HDD | The drive media type is traditional magnetic platters |
| SMR | The drive media type is shingled magnetic recording |
| SSD | The drive media type is solid state or flash memory |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |

### StatusIndicator:

| string | Description |
| --- | --- |
| Fail | The drive has failed. |
| Hotspare | The drive is marked to be automatically rebuilt and used as a replacement for a failed drive. |
| InACriticalArray | The array that this drive is a part of is degraded. |
| InAFailedArray | The array that this drive is a part of is failed. |
| OK | The drive is OK. |
| PredictiveFailureAnalysis | The drive is still working but predicted to fail soon. |
| Rebuild | The drive is being rebuilt. |


# EthernetInterface 1.0.2

This resource shall be used to represent NIC resources as part of the Redfish specification.

|     |     |     |
| --- | --- | --- |
| **AutoNeg** | boolean, null<br><br>*read-write* | The value of this property shall be true if auto negotiation of speed and duplex is enabled on this interface and false if it is disabled. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **FQDN** | string, null<br><br>*read-write* | The value of this property shall be the fully qualified domain name for this interface. |
| **FullDuplex** | boolean, null<br><br>*read-write* | The value of this property shall represent the duplex status of the Ethernet connection on this interface. |
| **HostName** | string, null<br><br>*read-write* | The value of this property shall be host name for this interface. |
| **IPv4Addresses** [ { | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv4 connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Address** | string, null<br><br>*read-write* | The value of this property shall be an IPv4 address assigned to this interface.  If DHCPv4 is enabled on the interface, this property becomes read-only. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AddressOrigin** | string, null<br><br>*read-write* | The value of this property shall be the IP address origin for this network interface. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Gateway** | string, null<br><br>*read-write* | The value of this property shall be the IPv4 default gateway address for this interface. If DHCPv4 is enabled on the interface and is configured to set the IPv4 default gateway address, this property becomes read-only. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SubnetMask** | string, null<br><br>*read-write* | The value of this property shall be the IPv4 subnet mask for this address.  If DHCPv4 is enabled on the interface, this property becomes read-only. |
| } ] |   |   |
| **IPv6AddressPolicyTable** [ { | array<br><br>*read-write* | The value of this property shall be an array of objects used to represent the Address Selection Policy Table as defined in RFC 6724. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Label** | number, null<br><br>*read-write* | This property shall contain the IPv6 Label value for this table entry as defined in RFC 6724 section 2.1. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Precedence** | number, null<br><br>*read-write* | This property shall contain the IPv6 Precedence value for this table entry as defined in RFC 6724 section 2.1. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Prefix** | string, null<br><br>*read-write* | This property shall contain the IPv6 Address Prefix for this table entry as defined in RFC 6724 section 2.1. |
| } ] |   |   |
| **IPv6Addresses** [ { | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv6 connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Address** | string, null<br><br>*read-write* | This property lists an IPv6 address that is currently assigned on this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AddressOrigin** | string, null<br><br>*read-write* | The value of this property shall be the IPv6 address origin for this interface. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AddressState** | string, null<br><br>*read-write* | Preferred and Deprecated states follow the definitions given RFC4862 Section 5.5.4. An address is in the Tentative state while undergoing Duplicate Address Detection (DAD) per RFC4862 Section 5.4.  The Failed state indicates a Static addresses which did not pass DAD.  A Static address in the Failed state is not in use on the network stack, and corrective action will be needed to remedy this condition. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PrefixLength** | number, null<br><br>*read-write* | The value of this property shall be the IPv6 address prefix length for this interface. |
| } ] |   |   |
| **IPv6DefaultGateway** | string, null<br><br>*read-only* | The value of this property shall be the current IPv6 default gateway address that is in use on this interface. |
| **IPv6StaticAddresses** [ { | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv6 static connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Address** | string, null<br><br>*read-write* | This property provides access to a static IPv6 address that is currently assigned on a network interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PrefixLength** | number, null<br><br>*read-write* | Provides the IPv6 network prefix length in bits for this address. |
| } ] |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **InterfaceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this interface is enabled. |
| **MACAddress** | string, null<br><br>*read-write* | The value of this property shall be the effective current MAC Address of this interface. If an assignable MAC address is not supported, this is a read only alias of the PermanentMACAddress. |
| **MTUSize** | number, null<br><br>*read-write* | The value of this property shall be the size in bytes of largest Protocol Data Unit (PDU) that can be passed in an Ethernet (MAC) frame on this interface. |
| **MaxIPv6StaticAddresses** | number, null<br><br>*read-only* | The value of this property shall indicate the number of array items supported by IPv6StaticAddresses. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **NameServers** [ {} ] | array<br><br>*read-only* | The value of this property shall be the DNS name servers used on this interface. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **PermanentMACAddress** | string, null<br><br>*read-write* | The value of this property shall be the Permanent MAC Address of this interface (port). This value is typically programmed during the manufacturing time. This address is not assignable. |
| **SpeedMbps** | number, null<br><br>*read-write* | The value of this property shall be the link speed of the interface in Mbps. |
| **Status** { | object, null<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **UefiDevicePath** | string, null<br><br>*read-only* | The value of this property shall be the UEFI device path to the device which implements this interface (port). |
| **VLAN** | , null<br><br>*read-write* | The value of this property shall be the VLAN for this interface.  If this interface supports more than one VLAN, the VLAN property shall not be present and the VLANS collection link shall be present instead. |
| **VLANs** { | object<br><br>*read-write* | The value of this property shall reference a collection of VLAN resources. If this property is used, the VLANEnabled and VLANId property shall not be used. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |

## Property Details

### AddressOrigin:

| string | Description |
| --- | --- |
| DHCPv6 | Address is provided by a DHCPv6 service |
| LinkLocal | Address is valid only for this network segment (link) |
| SLAAC | Address is provided by a Stateless Address AutoConfiguration (SLAAC) service |
| Static | A static address as configured by the user |

### AddressState:

| string | Description |
| --- | --- |
| Deprecated | This address is currently within it's valid lifetime, but is now outside of it's preferred lifetime as defined in RFC 4862. |
| Failed | This address has failed Duplicate Address Detection testing as defined in RFC 4862 section 5.4 and is not currently in use. |
| Preferred | This address is currently within both it's valid and preferred lifetimes as defined in RFC 4862. |
| Tentative | This address is currently undergoing Duplicate Address Detection testing as defined in RFC 4862 section 5.4. |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# EthernetInterfaceCollection

A Collection of EthernetInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AutoNeg** | boolean, null<br><br>*read-write* | The value of this property shall be true if auto negotiation of speed and duplex is enabled on this interface and false if it is disabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FQDN** | string, null<br><br>*read-write* | The value of this property shall be the fully qualified domain name for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FullDuplex** | boolean, null<br><br>*read-write* | The value of this property shall represent the duplex status of the Ethernet connection on this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HostName** | string, null<br><br>*read-write* | The value of this property shall be host name for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPv4Addresses** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv4 connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPv6AddressPolicyTable** [ {} ] | array<br><br>*read-write* | The value of this property shall be an array of objects used to represent the Address Selection Policy Table as defined in RFC 6724. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPv6Addresses** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv6 connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPv6DefaultGateway** | string, null<br><br>*read-only* | The value of this property shall be the current IPv6 default gateway address that is in use on this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPv6StaticAddresses** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of objects used to represent the IPv6 static connection characteristics for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InterfaceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this interface is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MACAddress** | string, null<br><br>*read-write* | The value of this property shall be the effective current MAC Address of this interface. If an assignable MAC address is not supported, this is a read only alias of the PermanentMACAddress. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MTUSize** | number, null<br><br>*read-write* | The value of this property shall be the size in bytes of largest Protocol Data Unit (PDU) that can be passed in an Ethernet (MAC) frame on this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxIPv6StaticAddresses** | number, null<br><br>*read-only* | The value of this property shall indicate the number of array items supported by IPv6StaticAddresses. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NameServers** [ {} ] | array<br><br>*read-only* | The value of this property shall be the DNS name servers used on this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PermanentMACAddress** | string, null<br><br>*read-write* | The value of this property shall be the Permanent MAC Address of this interface (port). This value is typically programmed during the manufacturing time. This address is not assignable. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SpeedMbps** | number, null<br><br>*read-write* | The value of this property shall be the link speed of the interface in Mbps. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object, null<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UefiDevicePath** | string, null<br><br>*read-only* | The value of this property shall be the UEFI device path to the device which implements this interface (port). |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VLAN** | , null<br><br>*read-write* | The value of this property shall be the VLAN for this interface.  If this interface supports more than one VLAN, the VLAN property shall not be present and the VLANS collection link shall be present instead. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VLANs** {} | object<br><br>*read-write* | The value of this property shall reference a collection of VLAN resources. If this property is used, the VLANEnabled and VLANId property shall not be used. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# Event 1.1.0

This resource shall be used to represent an event for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Context** *(v1.1.0)* | string<br><br>*read-only* | This property shall contain a client supplied context for the Event Destination to which this event is being sent. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Events** [ { | array<br><br>*read-write* | The value of this resource shall be an array of Event objects used to represent the occurrence of one or more events. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Context** | string<br><br>*read-only* | This property shall contain a client supplied context for the Event Destination to which this event is being sent. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventId** | string<br><br>*read-only* | The value of this property shall indicate a unique identifier for the event, the format of which is implementation dependent. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventTimestamp** | string<br><br>*read-only* | The value of this property shall indicate the time the event occurred where the value shall be consistent with the Redfish service time that is also used for the values of the Modified property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventType** | string<br><br>*read-write* | The value of this property shall indicate the type of event as defined in the EventService schema. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Message** | string<br><br>*read-only* | This property shall contain an optional human readable message. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MessageArgs** [ {} ] | array<br><br>*read-only* | This property has the same semantics as the MessageArgs property in the Event schema for Redfish. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MessageId** | string<br><br>*read-only* | This property shall be a key into message registry as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OriginOfCondition** {} | object<br><br>*read-write* | The value of this property shall contain a pointer consistent with JSON pointer syntax to the resource that caused the event to be generated. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Severity** | string<br><br>*read-only* | The value of this property shall be the severity of the event, as defined in the Status section of the Redfish specification. |
| } ] |   |   |
| **Events\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### EventType:

| string | Description |
| --- | --- |
| Alert | A condition exists which requires attention |
| ResourceAdded | A resource has been added |
| ResourceRemoved | A resource has been removed |
| ResourceUpdated | The value of this resource has been updated |
| StatusChange | The status of this resource has changed |


# EventDestination 1.0.2

An Event Destination desribes the target of an event subscription, including the types of events subscribed and context to provide to the target in the Event payload.

|     |     |     |
| --- | --- | --- |
| **Context** | string<br><br>*read-write* | This property shall contain a client supplied context that will remain with the connection through the connections lifetime. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Destination** | string<br><br>*read-only* | This property shall contain a URI to the destination where the events will be sent. |
| **EventTypes** [ {} ] | array<br><br>*read-only* | This property shall contain the types of events that shall be sent to the desination. |
| **HttpHeaders** [ {} ] | array<br><br>*read-write* | This property shall contain an object consisting of the names and values of of HTTP header to be included with every event POST to the Event Destination.  This property shall be null on a GET. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Protocol** | string<br><br>*read-write* | This property shall contain the protocol type that the event will use for sending the event to the destination.  A value of Redfish shall be used to indicate that the event type shall adhere to that defined in the Redfish specification. *See Property Details, below, for more information about this property.* |

## Property Details

### Protocol:

| string |
| --- |
| Redfish | 


# EventDestinationCollection

A Collection of EventDestination resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Context** | string<br><br>*read-write* | This property shall contain a client supplied context that will remain with the connection through the connections lifetime. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Destination** | string<br><br>*read-only* | This property shall contain a URI to the destination where the events will be sent. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventTypes** [ {} ] | array<br><br>*read-only* | This property shall contain the types of events that shall be sent to the desination. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HttpHeaders** [ {} ] | array<br><br>*read-write* | This property shall contain an object consisting of the names and values of of HTTP header to be included with every event POST to the Event Destination.  This property shall be null on a GET. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Protocol** | string<br><br>*read-write* | This property shall contain the protocol type that the event will use for sending the event to the destination.  A value of Redfish shall be used to indicate that the event type shall adhere to that defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### Protocol:

| string |
| --- |
| Redfish | 


# EventService 1.0.2

The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#EventService.SubmitTestEvent** {} | object<br><br>*read-write* | This action shall add a test event to the event service with the event data specified in the action parameters. This message should then be sent to any appropriate ListenerDestination targets. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **DeliveryRetryAttempts** | number<br><br>*read-only* | The value of this property shall be the number of retrys attempted for any given event to the subscription destination before the subscription is terminated. |
| **DeliveryRetryIntervalSeconds** | number<br><br>*read-only* | The value of this property shall be the interval in seconds between the retry attempts for any given event to the subscription destination. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EventTypesForSubscription** [ {} ] | array<br><br>*read-only* | The value of this property shall be the types of events that subscriptions can subscribe to.  The semantics associated with the enumerations values are defined in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Subscriptions** { | object<br><br>*read-write* | The value of this property shall contain the link to a collection of type EventDestinationCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# JsonSchemaFile 1.0.2

This resource shall be used to represent the Schema File locator resource for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Languages** [ {} ] | array<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code. |
| **Location** [ { | array<br><br>*read-only* | Location information for this schema file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ArchiveFile** | string<br><br>*read-only* | The value of this property shall be the file name of the individual schema file within the archive file specified by the ArchiveUri property.  The file name shall conform to the format [SchemaType].[MajorVersion].[MinorVersion].json and be in conformance with the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ArchiveUri** | string<br><br>*read-only* | The value of this property shall be a URI co-located with the Redfish service that specifies the location of the schema file.  This property shall only be used for archive files (zip or other formats).  The value of ArchiveFile shall have the file name of the individual schema file within the archive file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Language** | string<br><br>*read-only* | The value of this property shall be a string consisting of an RFC5646 language code or the string 'default'. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PublicationUri** | string<br><br>*read-only* | The value of this property shall be a URI not co-located with the Redfish service that specifies the canonical location of the schema file.  This property shall only be used for individual schema files. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Uri** | string<br><br>*read-only* | The value of this property shall be a URI co-located with the Redfish service that specifies the location of the schema file.  This property shall only be used for individual schema files.  The file name portion of the URI shall conform to the format [SchemaType].[MajorVersion].[MinorVersion].json and be in conformance with the Redfish specification. |
| } ] |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Schema** | string<br><br>*read-only* | The value of this property shall be the value of the @odata.type property for that schema and shall conform to the syntax specified in the Redfish specification for the Type property. |

# JsonSchemaFileCollection

A Collection of JsonSchemaFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Languages** [ {} ] | array<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** [ {} ] | array<br><br>*read-only* | Location information for this schema file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Schema** | string<br><br>*read-only* | The value of this property shall be the value of the @odata.type property for that schema and shall conform to the syntax specified in the Redfish specification for the Type property. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# LogEntry 1.0.2

This resource shall represent the log format for log services in a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Created** | string<br><br>*read-only* | The value of this property shall be the time at which the log entry was created. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EntryCode** | string, null<br><br>*read-write* | This property shall be present if the EntryType value is SEL.  These enumerations are the values from table 42-1 and 42-2 of the IPMI specification *See Property Details, below, for more information about this property.* |
| **EntryType** | string<br><br>*read-write* | This property shall represent the type of LogEntry.  If the resource represents an IPMI SEL log entry, the value shall be SEL.  If the resource represents an Event log, the value shall be Event.  If the resource represents an OEM log format, the value shall be Oem. *See Property Details, below, for more information about this property.* |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OriginOfCondition** {} | object<br><br>*read-write* | The value of this property shall be an href that references the resource for which the log is associated. |
| } |   |   |
| **Message** | string, null<br><br>*read-only* | The value of this property shall be the Message property of the event if the EntryType is Event, the Description if EntryType is SEL and OEM Specific if the EntryType is OEM. |
| **MessageArgs** [ {} ] | array<br><br>*read-only* | This contains message arguments to be substituted into the message included or in the message looked up via a registry. |
| **MessageId** | string<br><br>*read-only* | The value of this property shall the MessageId property of the event if the EntryType is Event, the EventData if EntryType is SEL and OEM Specific if the EntryType is OEM.  The format of this property shall be as defined in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OemRecordFormat** | string, null<br><br>*read-only* | The value of this property shall represent the OEM specific format of the Entry.  This property shall be required if the value of EntryType is Oem |
| **SensorNumber** | number, null<br><br>*read-only* | The value of this property shall be the EntityInstance from IPMI spec if EntryType is SEL, the count of events if EntryType is Event and OEM Specific if the EntryType is OEM. |
| **SensorType** | string, null<br><br>*read-write* | This property shall be present if the EntryType value is SEL. *See Property Details, below, for more information about this property.* |
| **Severity** | string, null<br><br>*read-write* | The value of this property shall be the severity of the condition resulting in the log entry, as defined in the Status section of the Redfish specificaiton. *See Property Details, below, for more information about this property.* |

## Property Details

### EntryCode:

| string |
| --- |
| Assert | 
| Deassert | 
| Lower Non-critical - going low | 
| Lower Non-critical - going high | 
| Lower Critical - going low | 
| Lower Critical - going high | 
| Lower Non-recoverable - going low | 
| Lower Non-recoverable - going high | 
| Upper Non-critical - going low | 
| Upper Non-critical - going high | 
| Upper Critical - going low | 
| Upper Critical - going high | 
| Upper Non-recoverable - going low | 
| Upper Non-recoverable - going high | 
| Transition to Idle | 
| Transition to Active | 
| Transition to Busy | 
| State Deasserted | 
| State Asserted | 
| Predictive Failure deasserted | 
| Predictive Failure asserted | 
| Limit Not Exceeded | 
| Limit Exceeded | 
| Performance Met | 
| Performance Lags | 
| Transition to OK | 
| Transition to Non-Critical from OK | 
| Transition to Critical from less severe | 
| Transition to Non-recoverable from less severe | 
| Transition to Non-Critical from more severe | 
| Transition to Critical from Non-recoverable | 
| Transition to Non-recoverable | 
| Monitor | 
| Informational | 
| Device Removed / Device Absent | 
| Device Inserted / Device Present | 
| Device Disabled | 
| Device Enabled | 
| Transition to Running | 
| Transition to In Test | 
| Transition to Power Off | 
| Transition to On Line | 
| Transition to Off Line | 
| Transition to Off Duty | 
| Transition to Degraded | 
| Transition to Power Save | 
| Install Error | 
| Fully Redundant | 
| Redundancy Lost | 
| Redundancy Degraded | 
| Non-redundant:Sufficient Resources from Redundant | 
| Non-redundant:Sufficient Resources from Insufficient Resources | 
| Non-redundant:Insufficient Resources | 
| Redundancy Degraded from Fully Redundant | 
| Redundancy Degraded from Non-redundant | 
| D0 Power State | 
| D1 Power State | 
| D2 Power State | 
| D3 Power State | 

### EntryType:

| string |
| --- |
| Event | 
| SEL | 
| Oem | 

### SensorType:

| string |
| --- |
| Platform Security Violation Attempt | 
| Temperature | 
| Voltage | 
| Current | 
| Fan | 
| Physical Chassis Security | 
| Processor | 
| Power Supply / Converter | 
| PowerUnit | 
| CoolingDevice | 
| Other Units-based Sensor | 
| Memory | 
| Drive Slot/Bay | 
| POST Memory Resize | 
| System Firmware Progress | 
| Event Logging Disabled | 
| System Event | 
| Critical Interrupt | 
| Button/Switch | 
| Module/Board | 
| Microcontroller/Coprocessor | 
| Add-in Card | 
| Chassis | 
| ChipSet | 
| Other FRU | 
| Cable/Interconnect | 
| Terminator | 
| SystemBoot/Restart | 
| Boot Error | 
| BaseOSBoot/InstallationStatus | 
| OS Stop/Shutdown | 
| Slot/Connector | 
| System ACPI PowerState | 
| Watchdog | 
| Platform Alert | 
| Entity Presence | 
| Monitor ASIC/IC | 
| LAN | 
| Management Subsystem Health | 
| Battery | 
| Session Audit | 
| Version Change | 
| FRUState | 

### Severity:

| string |
| --- |
| OK | 
| Warning | 
| Critical | 


# LogEntryCollection

A Collection of LogEntry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Created** | string<br><br>*read-only* | The value of this property shall be the time at which the log entry was created. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EntryCode** | string, null<br><br>*read-write* | This property shall be present if the EntryType value is SEL.  These enumerations are the values from table 42-1 and 42-2 of the IPMI specification *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EntryType** | string<br><br>*read-write* | This property shall represent the type of LogEntry.  If the resource represents an IPMI SEL log entry, the value shall be SEL.  If the resource represents an Event log, the value shall be Event.  If the resource represents an OEM log format, the value shall be Oem. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Message** | string, null<br><br>*read-only* | The value of this property shall be the Message property of the event if the EntryType is Event, the Description if EntryType is SEL and OEM Specific if the EntryType is OEM. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MessageArgs** [ {} ] | array<br><br>*read-only* | This contains message arguments to be substituted into the message included or in the message looked up via a registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MessageId** | string<br><br>*read-only* | The value of this property shall the MessageId property of the event if the EntryType is Event, the EventData if EntryType is SEL and OEM Specific if the EntryType is OEM.  The format of this property shall be as defined in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OemRecordFormat** | string, null<br><br>*read-only* | The value of this property shall represent the OEM specific format of the Entry.  This property shall be required if the value of EntryType is Oem |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SensorNumber** | number, null<br><br>*read-only* | The value of this property shall be the EntityInstance from IPMI spec if EntryType is SEL, the count of events if EntryType is Event and OEM Specific if the EntryType is OEM. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SensorType** | string, null<br><br>*read-write* | This property shall be present if the EntryType value is SEL. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Severity** | string, null<br><br>*read-write* | The value of this property shall be the severity of the condition resulting in the log entry, as defined in the Status section of the Redfish specificaiton. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### EntryCode:

| string |
| --- |
| Assert | 
| Deassert | 
| Lower Non-critical - going low | 
| Lower Non-critical - going high | 
| Lower Critical - going low | 
| Lower Critical - going high | 
| Lower Non-recoverable - going low | 
| Lower Non-recoverable - going high | 
| Upper Non-critical - going low | 
| Upper Non-critical - going high | 
| Upper Critical - going low | 
| Upper Critical - going high | 
| Upper Non-recoverable - going low | 
| Upper Non-recoverable - going high | 
| Transition to Idle | 
| Transition to Active | 
| Transition to Busy | 
| State Deasserted | 
| State Asserted | 
| Predictive Failure deasserted | 
| Predictive Failure asserted | 
| Limit Not Exceeded | 
| Limit Exceeded | 
| Performance Met | 
| Performance Lags | 
| Transition to OK | 
| Transition to Non-Critical from OK | 
| Transition to Critical from less severe | 
| Transition to Non-recoverable from less severe | 
| Transition to Non-Critical from more severe | 
| Transition to Critical from Non-recoverable | 
| Transition to Non-recoverable | 
| Monitor | 
| Informational | 
| Device Removed / Device Absent | 
| Device Inserted / Device Present | 
| Device Disabled | 
| Device Enabled | 
| Transition to Running | 
| Transition to In Test | 
| Transition to Power Off | 
| Transition to On Line | 
| Transition to Off Line | 
| Transition to Off Duty | 
| Transition to Degraded | 
| Transition to Power Save | 
| Install Error | 
| Fully Redundant | 
| Redundancy Lost | 
| Redundancy Degraded | 
| Non-redundant:Sufficient Resources from Redundant | 
| Non-redundant:Sufficient Resources from Insufficient Resources | 
| Non-redundant:Insufficient Resources | 
| Redundancy Degraded from Fully Redundant | 
| Redundancy Degraded from Non-redundant | 
| D0 Power State | 
| D1 Power State | 
| D2 Power State | 
| D3 Power State | 

### EntryType:

| string |
| --- |
| Event | 
| SEL | 
| Oem | 

### SensorType:

| string |
| --- |
| Platform Security Violation Attempt | 
| Temperature | 
| Voltage | 
| Current | 
| Fan | 
| Physical Chassis Security | 
| Processor | 
| Power Supply / Converter | 
| PowerUnit | 
| CoolingDevice | 
| Other Units-based Sensor | 
| Memory | 
| Drive Slot/Bay | 
| POST Memory Resize | 
| System Firmware Progress | 
| Event Logging Disabled | 
| System Event | 
| Critical Interrupt | 
| Button/Switch | 
| Module/Board | 
| Microcontroller/Coprocessor | 
| Add-in Card | 
| Chassis | 
| ChipSet | 
| Other FRU | 
| Cable/Interconnect | 
| Terminator | 
| SystemBoot/Restart | 
| Boot Error | 
| BaseOSBoot/InstallationStatus | 
| OS Stop/Shutdown | 
| Slot/Connector | 
| System ACPI PowerState | 
| Watchdog | 
| Platform Alert | 
| Entity Presence | 
| Monitor ASIC/IC | 
| LAN | 
| Management Subsystem Health | 
| Battery | 
| Session Audit | 
| Version Change | 
| FRUState | 

### Severity:

| string |
| --- |
| OK | 
| Warning | 
| Critical | 


# LogService 1.0.2


**You don't have to attend every meeting to know what happened.**

Meeting records capture who showed up, what they reviewed, what was decided, and what tasks were assigned. Publish records to the team and your existing business systems.


|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#LogService.ClearLog** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **DateTime** | string, null<br><br>*read-write* | The value of this property shall represent the current DateTime value that the log service is using, with offset from UTC, in Redfish Timestamp format. |
| **DateTimeLocalOffset** | string, null<br><br>*read-write* | The value is property shall represent the offset from UTC time that the current value of DataTime property contains. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Entries** { | object<br><br>*read-write* | The value of this property shall reference a collection of resources of type LogEntry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **MaxNumberOfRecords** | number<br><br>*read-only* | The value of this property shall be the maximum numbers of LogEntry resources in the Entries collection for this service. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OverWritePolicy** | string<br><br>*read-write* | The value of this property shall indicate the policy of the log service when the MaxNumberOfRecords has been reached. Unknown indicates the log overwrite policy is unknown. WrapsWhenFull indicates that the log overwrites its entries with new entries when the log has reached its maximum capacity. NeverOverwrites indicates that the log never overwrites its entries by the new entries and ceases logging when the limit has been reached. *See Property Details, below, for more information about this property.* |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| **Status** { | object, null<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### OverWritePolicy:

| string | Description |
| --- | --- |
| NeverOverWrites | When full, new entries to the Log will be discarded |
| Unknown | The overwrite policy is not known or is undefined |
| WrapsWhenFull | When full, new entries to the Log will overwrite previous entries |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# LogServiceCollection

A Collection of LogService resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTime** | string, null<br><br>*read-write* | The value of this property shall represent the current DateTime value that the log service is using, with offset from UTC, in Redfish Timestamp format. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTimeLocalOffset** | string, null<br><br>*read-write* | The value is property shall represent the offset from UTC time that the current value of DataTime property contains. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Entries** {} | object<br><br>*read-write* | The value of this property shall reference a collection of resources of type LogEntry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxNumberOfRecords** | number<br><br>*read-only* | The value of this property shall be the maximum numbers of LogEntry resources in the Entries collection for this service. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OverWritePolicy** | string<br><br>*read-write* | The value of this property shall indicate the policy of the log service when the MaxNumberOfRecords has been reached. Unknown indicates the log overwrite policy is unknown. WrapsWhenFull indicates that the log overwrites its entries with new entries when the log has reached its maximum capacity. NeverOverwrites indicates that the log never overwrites its entries by the new entries and ceases logging when the limit has been reached. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object, null<br><br>*read-only* |  |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### OverWritePolicy:

| string | Description |
| --- | --- |
| NeverOverWrites | When full, new entries to the Log will be discarded |
| Unknown | The overwrite policy is not known or is undefined |
| WrapsWhenFull | When full, new entries to the Log will overwrite previous entries |


# Manager 1.1.0

This resource shall be used to represent a management subsystem for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ForceFailover** {} | object<br><br>*read-write* | This defines the name of the custom action supported when used in conjunction with a POST operation to this resource. When issued, this operation will perform a forced failover of the manager's redundancy to the manager supplied as a parameter. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ModifyRedundancySet** {} | object<br><br>*read-write* | This defines the name of the custom action for which the following properties are supported on this resource.  The ModifyRedundancySet operation shall be used to add or remove members to a redundant group of manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.Reset** {} | object<br><br>*read-write* | This defines the name of the custom action supported when used in conjunction with a POST operation to this resource. When issued, this operation will perform a reset of the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **CommandShell** { | object<br><br>*read-write* | The value of this property shall contain information about the Command Shell service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** [ {} ] | array<br><br>*read-only* | The value of ConnectTypesSupported shall be an array of the enumerations provided here.  SSH shall be included if the Secure Shell (SSH) protocol is supported.  Telnet shall be included if the Telnet protocol is supported.  IPMI shall be included if the IPMI (Serial-over-LAN) protocol is supported. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **DateTime** | string, null<br><br>*read-write* | The value of this property shall represent the current DateTime value for the manager, with offset from UTC, in Redfish Timestamp format. |
| **DateTimeLocalOffset** | string, null<br><br>*read-write* | The value is property shall represent the offset from UTC time that the current value of DataTime property contains. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EthernetInterfaces** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type EthernetInterfaceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **FirmwareVersion** | string, null<br><br>*read-only* | This property shall contain the firwmare version as defined by the manufacturer for the associated manager. |
| **GraphicalConsole** { | object<br><br>*read-write* | The value of this property shall contain the information about the Graphical Console (KVM-IP) service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** [ {} ] | array<br><br>*read-only* | The value of ConnectTypesSupported shall be an array of the enumerations provided here.  RDP shall be included if the Remote Desktop (RDP) protocol is supported.  KVMIP shall be included if a vendor-define KVM-IP protocol is supported. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis** [ {} ] | array<br><br>*read-only* | This property shall contain an array of references to Chassis resources of which this Manager instance has control. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers** [ {} ] | array<br><br>*read-only* | This property shall contain an array of references to ComputerSystem resources of which this Manager instance has control. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerInChassis** {} | object<br><br>*read-write* | This property shall contain a reference to the chassis that this manager is located in. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| } |   |   |
| **LogServices** { | object<br><br>*read-write* | The value of this property shall contain a reference to a collection of type LogServiceCollection which are for the use of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **ManagerType** | string<br><br>*read-write* | The value of this property shall describe the function of this manager.  The value EnclosureManager shall be used if this manager controls one or more services through aggregation.  The value BMC shall be used if this manager represents a traditional server management controller. The value ManagementController shall be used if none of the other enumerations apply. *See Property Details, below, for more information about this property.* |
| **Model** | string, null<br><br>*read-only* | The value of this property shall contain the information about how the manufacturer references this manager. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **NetworkProtocol** { | object<br><br>*read-write* | The value of this property shall contain a reference to a resource of type ManagerNetworkProtocol which represents the network services for this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FQDN** | string, null<br><br>*read-only* | The value of this property shall contain the fully qualified domain name for the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HTTP** {} | object<br><br>*read-write* | This object shall contain information for the HTTP protocol settings for the manager. The default value of the Port property should be 80 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HTTPS** {} | object<br><br>*read-write* | This object shall contain information for the HTTPS/SSL protocol settings for this manager. The default value of the Port property should be 443 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HostName** | string, null<br><br>*read-only* | The value of this property shall contain the host name without any domain information. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPMI** {} | object<br><br>*read-write* | This object shall contain information for the IPMI over LAN protocol settings for the manager. The default value of the Port property should be 623 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**KVMIP** {} | object<br><br>*read-write* | This object shall contain information for the KVM-IP (Keyboard, Video, Mouse) protocol settings for the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SNMP** {} | object<br><br>*read-write* | This object shall contain information for the SNMP protocol settings for this manager. The default value of the Port property should be 161 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SSDP** {} | object<br><br>*read-write* | This object shall contain information for the SSDP protocol settings for this manager.  Simple Service Discovery Protocol (SSDP) is for network discovery of devices supporting the Redfish service. The default value of the Port property should be 1900 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SSH** {} | object<br><br>*read-write* | This object shall contain information for the SSH protocol settings for the manager. The default value of the Port property should be 22 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Telnet** {} | object<br><br>*read-write* | This object shall contain information for the Telnet protocol settings for this manager. The default value of the Port property should be 23 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VirtualMedia** {} | object<br><br>*read-write* | This object shall contain information for the Virtual Media protocol settings for this manager. The value of the Port property shall contain the TCP port assigned for Virtual Media usage. |
| } |   |   |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Redundancy** [ { | array<br><br>*read-only* | Redundancy information for the managers of this system |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } ] |   |   |
| **Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| **SerialConsole** { | object<br><br>*read-write* | The value of this property shall contain information about the Serial Console service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** [ {} ] | array<br><br>*read-only* | The value of ConnectTypesSupported shall be an array of the enumerations provided here.  SSH shall be included if the Secure Shell (SSH) protocol is supported.  Telnet shall be included if the Telnet protocol is supported.  IPMI shall be included if the IPMI (Serial-over-LAN) protocol is supported. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **SerialInterfaces** { | object<br><br>*read-write* | The value of this property shall be a link to a collection of type SerialInterfaceCollection which are for the use of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **ServiceEntryPointUUID** | string<br><br>*read-write* | This property shall contain the UUID of the Redfish Service provided by this manager.  Each Manager providing an Entry Point to the same Redfish Service shall report the same UUID value (even though the name of the property may imply otherwise).  This property shall not be present if this manager does not provide a Redfish Service Entry Point. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **UUID** | string, null<br><br>*read-write* | The value of this property shall contain the universal unique identifier number for the manager. |
| **VirtualMedia** { | object<br><br>*read-write* | The value of this property shall contain a reference to a collection of type VirtualMediaCollection which are for the use of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### ManagerType:

| string | Description |
| --- | --- |
| AuxiliaryController | A controller which provides management functions for a particular subsystem or group of devices |
| BMC | A controller which provides management functions for a single computer system |
| EnclosureManager | A controller which provides management functions for a chassis or group of devices or systems |
| ManagementController | A controller used primarily to monitor or manage the operation of a device or system |
| RackManager | A controller which provides management functions for a whole or part of a rack |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# ManagerAccount 1.0.2


Stop juggling multiple applications while trying to run a productive meeting. Before, during, after: Lucid's all-in-one platform combines all the tools you need to run a successful meeting start to finish.




> Here is how to get a list of meetings. A meeting contains all the information necessary for scheduling and running an online meeting. Meetings are scheduled within a room, and each meeting includes its specific agenda, meeting state, list of attendees, notes, action items, and meeting record.

```json
[
  {
    "meeting_id": 1194,
    "name": "Review meeting",
    "start_time": {
      "value": 1431648000,
      "iso_8601": "2015-05-15T00:00:00Z"
    }
  },
  {
    "meeting_id": 1192,
    "name": "Status followup",
    "start_time": {
      "value": 1430956800,
      "iso_8601": "2015-05-07T00:00:00Z"
    }
  },
  {
    "meeting_id": 1199,
    "name": "Status update",
    "start_time": {
      "value": 1430872200,
      "iso_8601": "2015-05-06T00:30:00Z"
    }
  }
]
```


|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Enabled** | boolean<br><br>*read-write* | This property shall enable (if set to true) or disable (if set to false) the account for future logins. The value of Enable over-rides the locked property. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Role** {} | object<br><br>*read-write* | The value of this property shall be a link to a Role object instance, and should reference the object identified by property RoleId. |
| } |   |   |
| **Locked** | boolean<br><br>*read-write* | This property (when set to true) shall indicate that the account service has automatically locked the account due to the accountLockoutThreshold having been exceeded. If set to true, the account is locked.  If set to false, the account is not locked.  A user admin shall be able to write a false to the property to clear the lockout condition, prior to the lockout duration period. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Password** | string, null<br><br>*read-write* | The value of this property shall be the password for this account.  The value shall be null for GET requests. |
| **RoleId** | string<br><br>*read-write* | The value of this property shall be the ID of the Role resource that configured for this account. |
| **UserName** | string<br><br>*read-write* | The value of this property shall be the user name for this account. |

# ManagerAccountCollection

A Collection of ManagerAccount resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enabled** | boolean<br><br>*read-write* | This property shall enable (if set to true) or disable (if set to false) the account for future logins. The value of Enable over-rides the locked property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Locked** | boolean<br><br>*read-write* | This property (when set to true) shall indicate that the account service has automatically locked the account due to the accountLockoutThreshold having been exceeded. If set to true, the account is locked.  If set to false, the account is not locked.  A user admin shall be able to write a false to the property to clear the lockout condition, prior to the lockout duration period. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Password** | string, null<br><br>*read-write* | The value of this property shall be the password for this account.  The value shall be null for GET requests. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RoleId** | string<br><br>*read-write* | The value of this property shall be the ID of the Role resource that configured for this account. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UserName** | string<br><br>*read-write* | The value of this property shall be the user name for this account. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# ManagerCollection

A Collection of Manager resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CommandShell** {} | object<br><br>*read-write* | The value of this property shall contain information about the Command Shell service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTime** | string, null<br><br>*read-write* | The value of this property shall represent the current DateTime value for the manager, with offset from UTC, in Redfish Timestamp format. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTimeLocalOffset** | string, null<br><br>*read-write* | The value is property shall represent the offset from UTC time that the current value of DataTime property contains. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EthernetInterfaces** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type EthernetInterfaceCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FirmwareVersion** | string, null<br><br>*read-only* | This property shall contain the firwmare version as defined by the manufacturer for the associated manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**GraphicalConsole** {} | object<br><br>*read-write* | The value of this property shall contain the information about the Graphical Console (KVM-IP) service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LogServices** {} | object<br><br>*read-write* | The value of this property shall contain a reference to a collection of type LogServiceCollection which are for the use of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerType** | string<br><br>*read-write* | The value of this property shall describe the function of this manager.  The value EnclosureManager shall be used if this manager controls one or more services through aggregation.  The value BMC shall be used if this manager represents a traditional server management controller. The value ManagementController shall be used if none of the other enumerations apply. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | The value of this property shall contain the information about how the manufacturer references this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NetworkProtocol** {} | object<br><br>*read-write* | The value of this property shall contain a reference to a resource of type ManagerNetworkProtocol which represents the network services for this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | Redundancy information for the managers of this system |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialConsole** {} | object<br><br>*read-write* | The value of this property shall contain information about the Serial Console service of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialInterfaces** {} | object<br><br>*read-write* | The value of this property shall be a link to a collection of type SerialInterfaceCollection which are for the use of this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEntryPointUUID** | string<br><br>*read-write* | This property shall contain the UUID of the Redfish Service provided by this manager.  Each Manager providing an Entry Point to the same Redfish Service shall report the same UUID value (even though the name of the property may imply otherwise).  This property shall not be present if this manager does not provide a Redfish Service Entry Point. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UUID** | string, null<br><br>*read-write* | The value of this property shall contain the universal unique identifier number for the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VirtualMedia** {} | object<br><br>*read-write* | The value of this property shall contain a reference to a collection of type VirtualMediaCollection which are for the use of this manager. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### ManagerType:

| string | Description |
| --- | --- |
| AuxiliaryController | A controller which provides management functions for a particular subsystem or group of devices |
| BMC | A controller which provides management functions for a single computer system |
| EnclosureManager | A controller which provides management functions for a chassis or group of devices or systems |
| ManagementController | A controller used primarily to monitor or manage the operation of a device or system |
| RackManager | A controller which provides management functions for a whole or part of a rack |


# ManagerNetworkProtocol 1.0.2

This object shall be used to represent the network service settings for the manager.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **FQDN** | string, null<br><br>*read-only* | The value of this property shall contain the fully qualified domain name for the manager. |
| **HTTP** { | object<br><br>*read-write* | This object shall contain information for the HTTP protocol settings for the manager. The default value of the Port property should be 80 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **HTTPS** { | object<br><br>*read-write* | This object shall contain information for the HTTPS/SSL protocol settings for this manager. The default value of the Port property should be 443 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **HostName** | string, null<br><br>*read-only* | The value of this property shall contain the host name without any domain information. |
| **IPMI** { | object<br><br>*read-write* | This object shall contain information for the IPMI over LAN protocol settings for the manager. The default value of the Port property should be 623 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **KVMIP** { | object<br><br>*read-write* | This object shall contain information for the KVM-IP (Keyboard, Video, Mouse) protocol settings for the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **SNMP** { | object<br><br>*read-write* | This object shall contain information for the SNMP protocol settings for this manager. The default value of the Port property should be 161 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **SSDP** { | object<br><br>*read-write* | This object shall contain information for the SSDP protocol settings for this manager.  Simple Service Discovery Protocol (SSDP) is for network discovery of devices supporting the Redfish service. The default value of the Port property should be 1900 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyIPv6Scope** | string, null<br><br>*read-write* | The value of this property shall contain the IPv6 scope used for multicast NOTIFY messages.  The valid enumerations are a subset of the available IPv6 Scope types. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyMulticastIntervalSeconds** | number, null<br><br>*read-write* | The value of this property shall contain the time interval, in seconds, between transmissions of the multicast NOTIFY ALIVE message.  A setting of 0 seconds shall disable this functionality.  The recommended value is 600 seconds. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyTTL** | number, null<br><br>*read-write* | The value of this property shall contain the Time-To-Live hop count used for multicast NOTIFY messages.  The recommended value is 2. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **SSH** { | object<br><br>*read-write* | This object shall contain information for the SSH protocol settings for the manager. The default value of the Port property should be 22 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Telnet** { | object<br><br>*read-write* | This object shall contain information for the Telnet protocol settings for this manager. The default value of the Port property should be 23 for compatibility with established client implementations. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |
| **VirtualMedia** { | object<br><br>*read-write* | This object shall contain information for the Virtual Media protocol settings for this manager. The value of the Port property shall contain the TCP port assigned for Virtual Media usage. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | The value of this property shall contain the port assigned for the protocol. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled. |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### NotifyIPv6Scope:

| string | Description |
| --- | --- |
| Link | SSDP Notify messages are sent to addresses in the IPv6 Local Link scope |
| Organization | SSDP Notify messages are sent to addresses in the IPv6 Local Organization scope |
| Site | SSDP Notify messages are sent to addresses in the IPv6 Local Site scope |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# Memory 1.0.0

This resource shall be used to represent the Memory in a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.DisablePassphrase** {} | object<br><br>*read-write* | This action shall disaple the need for passphrases on the supplied region provided the supplied passphrase matches that of the region. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SecureEraseUnit** {} | object<br><br>*read-write* | This action shall securely erase the supplied region provided the supplied passphrase matches that of the given region. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SetPassphrase** {} | object<br><br>*read-write* | This action shall apply the supplied passphrase to the supplied region. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.UnlockUnit** {} | object<br><br>*read-write* | This action shall apply the supplied passphrase to the supplied region for the purpose of unlocking the given regions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AllowedSpeedsMHz** [ {} ] | array<br><br>*read-only* | The value of this property shall be the speed supported by this Memory. |
| **BaseModuleType** | string, null<br><br>*read-write* | The value of this property shall be the base module type of Memory *See Property Details, below, for more information about this property.* |
| **BusWidthBits** | number, null<br><br>*read-only* | The value of this property shall be the bus width in bits. |
| **CapacityMiB** | number, null<br><br>*read-only* | The value of this property shall be the Memory capacity in MiB. |
| **DataWidthBits** | number, null<br><br>*read-only* | The value of this property shall be the data width in bits. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **DeviceID** | string, null<br><br>*read-only* | The value of this property shall be the device ID of the Memory. |
| **DeviceLocator** | string, null<br><br>*read-only* | The value of this property shall be location of the Memory in the platform, typically marked in the silk screen. |
| **ErrorCorrection** | string, null<br><br>*read-write* | The value of this property shall be the error correction scheme supported for this memory. *See Property Details, below, for more information about this property.* |
| **FirmwareApiVersion** | string, null<br><br>*read-only* | The value of this property shall be the version of API supported by the firmware. |
| **FirmwareRevision** | string, null<br><br>*read-only* | The value of this property shall be the revision of firmware on the Memory controller. |
| **FunctionClasses** [ {} ] | array<br><br>*read-only* | The value of this property shall be the function classes by the Memory. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **IsRankSpareEnabled** | boolean, null<br><br>*read-only* | The value of this property shall be true if a rank spare is enabled for this Memory. |
| **IsSpareDeviceEnabled** | boolean, null<br><br>*read-only* | The value of this property shall be true if a spare device is enabled for this Memory. |
| **Manufacturer** | string, null<br><br>*read-only* | This property shall contain a string which identifies the manufacturer of the Memory. |
| **MaxTDPMilliWatts** [ {} ] | array<br><br>*read-only* | The value of this property shall be the maximum power budgets supported by the Memory in milli Watts. |
| **MemoryDeviceType** | string, null<br><br>*read-write* | The value of this property shall be the Memory Device Type as defined by SMBIOS. *See Property Details, below, for more information about this property.* |
| **MemoryLocation** { | object<br><br>*read-write* | This object shall contain properties which describe the Memory connection information to sockets and memory controllers. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Channel** | number, null<br><br>*read-only* | Channel number in which Memory is connected. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryController** | number, null<br><br>*read-only* | Memory controller number in which Memory is connected. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Slot** | number, null<br><br>*read-only* | Slot number in which Memory is connected. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Socket** | number, null<br><br>*read-only* | Socket number in which Memory is connected. |
| } |   |   |
| **MemoryMedia** [ {} ] | array<br><br>*read-only* | The value of this property shall be the media types of this Memory |
| **MemoryType** | string, null<br><br>*read-write* | The value of this property shall be the type of Memory represented by this resource. *See Property Details, below, for more information about this property.* |
| **Metrics** { | object<br><br>*read-write* | A reference to the Metrics associated with this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlockSizeBytes** | number, null<br><br>*read-only* | The value of this property shall be the block size in bytes of all stucture elements. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CurrentPeriod** {} | object<br><br>*read-write* | This object shall contain properties which describe the CurrentPeriod metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthData** {} | object<br><br>*read-write* | This object shall contain properties which describe the HealthData metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LifeTime** {} | object<br><br>*read-write* | This object shall contain properties which describe the LifeTime metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OperatingMemoryModes** [ {} ] | array<br><br>*read-only* | The value of this property shall be the memory modes supported by the Memory. |
| **OperatingSpeedMhz** | number, null<br><br>*read-only* | The value of this property shall be the operating speed of Memory in MHz. |
| **PartNumber** | string, null<br><br>*read-only* | This property shall indicate the part number as provided by the manufacturer of this Memory. |
| **PersistentRegionSizeLimitMiB** | number, null<br><br>*read-only* | The value of this property shall be the total size of persistent regions in MiB. |
| **PowerManagementPolicy** { | object<br><br>*read-write* | This object shall contain properties which describe the power management policy for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AveragePowerBudgetMilliWatts** | number, null<br><br>*read-only* | Average power budget in milli watts. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxTDPMilliWatts** | number, null<br><br>*read-only* | Maximum TDP in milli watts. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PeakPowerBudgetMilliWatts** | number, null<br><br>*read-only* | Peak power budget in milli watts. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PolicyEnabled** | boolean, null<br><br>*read-only* | Power management policy enabled status. |
| } |   |   |
| **RankCount** | number, null<br><br>*read-only* | The value of this property shall be number of ranks available in the Memory. The ranks could be used for spare or interleave. |
| **Regions** [ { | array<br><br>*read-only* | The value of this property shall be the memory region information within the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryClassification** | string, null<br><br>*read-write* | Classification of memory occupied by the given memory region. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OffsetMiB** | number, null<br><br>*read-only* | Offset with in the Memory that corresponds to the starting of this memory region in MiB. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PassphraseState** | boolean, null<br><br>*read-only* | State of the passphrase for this region. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RegionId** | string, null<br><br>*read-only* | Unique region ID representing a specific region within the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SizeMiB** | number, null<br><br>*read-only* | Size of this memory region in MiB. |
| } ] |   |   |
| **SecurityCapabilities** { | object<br><br>*read-write* | This object shall contain properties which describe the security capabilities of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPassphraseCount** | number, null<br><br>*read-only* | Maximum number of passphrases supported for this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PassphraseCapable** | boolean, null<br><br>*read-only* | Memory passphrase set capability. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecurityStates** [ {} ] | array<br><br>*read-only* | Security states supported by the Memory. |
| } |   |   |
| **SerialNumber** | string, null<br><br>*read-only* | This property shall indicate the serial number as provided by the manufacturer of this Memory. |
| **SpareDeviceCount** | number, null<br><br>*read-only* | The value of this property shall be the number of unused spare devices available in the Memory. If memory devices fails, the spare device could be used. |
| **SubsystemDeviceID** | string, null<br><br>*read-only* | The value of this property shall be the subsystem Device ID of the Memory. |
| **SubsystemVendorID** | string, null<br><br>*read-only* | The value of this property shall be the subsystem Vendor ID of the Memory. |
| **VendorID** | string, null<br><br>*read-only* | The value of this property shall be the vendor ID of the Memory. |
| **VolatileRegionSizeLimitMiB** | number, null<br><br>*read-only* | The value of this property shall be the total size of volatile regions in MiB. |

## Property Details

### BaseModuleType:

| string | Description |
| --- | --- |
| LRDIMM | Load Reduced |
| Mini_RDIMM | Mini_RDIMM |
| Mini_UDIMM | Mini_UDIMM |
| RDIMM | Registered DIMM |
| SO_DIMM | SO_DIMM |
| SO_DIMM_16b | SO_DIMM_16b |
| SO_DIMM_32b | SO_DIMM_32b |
| SO_RDIMM_72b | SO_RDIMM_72b |
| SO_UDIMM_72b | SO_UDIMM_72b |
| UDIMM | UDIMM |

### ErrorCorrection:

| string | Description |
| --- | --- |
| AddressParity | Address Parity errors can be corrected |
| MultiBitECC | Multi-bit Data errors can be corrected by ECC |
| NoECC | No ECC available |
| SingleBitECC | Single bit Data error can be corrected by ECC |

### MemoryClassification:

| string | Description |
| --- | --- |
| Block | Block accesible memory |
| ByteAccessiblePersistent | Byte accessible persistent memory |
| Volatile | Volatile memory |

### MemoryDeviceType:

| string | Description |
| --- | --- |
| DDR | DDR |
| DDR2 | DDR2 |
| DDR2_SDRAM | DDR2 SDRAM |
| DDR2_SDRAM_FB_DIMM | DDR2 SDRAM FB_DIMM |
| DDR2_SDRAM_FB_DIMM_PROBE | DDR2 SDRAM FB_DIMM PROBE |
| DDR3 | DDR3 |
| DDR3_SDRAM | DDR3 SDRAM |
| DDR4 | DDR4 |
| DDR4E_SDRAM | DDR4E SDRAM |
| DDR4_SDRAM | DDR4 SDRAM |
| DDR_SDRAM | DDR SDRAM |
| DDR_SGRAM | DDR SGRAM |
| EDO | EDO |
| FastPageMode | Fast Page Mode |
| LPDDR3_SDRAM | LPDDR3 SDRAM |
| LPDDR4_SDRAM | LPDDR4 SDRAM |
| PipelinedNibble | Pipelined Nibble |
| ROM | ROM |
| SDRAM | SDRAM |

### MemoryType:

| string | Description |
| --- | --- |
| DRAM | DRAM |
| NVDIMM_F | NVDIMM_F as defined by JEDEC. |
| NVDIMM_N | NVDIMM_N as defined by JEDEC. |
| NVDIMM_P | NVDIMM_P as defined by JEDEC. |


# MemoryCollection

A Collection of Memory resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AllowedSpeedsMHz** [ {} ] | array<br><br>*read-only* | The value of this property shall be the speed supported by this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BaseModuleType** | string, null<br><br>*read-write* | The value of this property shall be the base module type of Memory *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BusWidthBits** | number, null<br><br>*read-only* | The value of this property shall be the bus width in bits. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CapacityMiB** | number, null<br><br>*read-only* | The value of this property shall be the Memory capacity in MiB. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DataWidthBits** | number, null<br><br>*read-only* | The value of this property shall be the data width in bits. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeviceID** | string, null<br><br>*read-only* | The value of this property shall be the device ID of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeviceLocator** | string, null<br><br>*read-only* | The value of this property shall be location of the Memory in the platform, typically marked in the silk screen. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ErrorCorrection** | string, null<br><br>*read-write* | The value of this property shall be the error correction scheme supported for this memory. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FirmwareApiVersion** | string, null<br><br>*read-only* | The value of this property shall be the version of API supported by the firmware. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FirmwareRevision** | string, null<br><br>*read-only* | The value of this property shall be the revision of firmware on the Memory controller. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FunctionClasses** [ {} ] | array<br><br>*read-only* | The value of this property shall be the function classes by the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IsRankSpareEnabled** | boolean, null<br><br>*read-only* | The value of this property shall be true if a rank spare is enabled for this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IsSpareDeviceEnabled** | boolean, null<br><br>*read-only* | The value of this property shall be true if a spare device is enabled for this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | This property shall contain a string which identifies the manufacturer of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxTDPMilliWatts** [ {} ] | array<br><br>*read-only* | The value of this property shall be the maximum power budgets supported by the Memory in milli Watts. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryDeviceType** | string, null<br><br>*read-write* | The value of this property shall be the Memory Device Type as defined by SMBIOS. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryLocation** {} | object<br><br>*read-write* | This object shall contain properties which describe the Memory connection information to sockets and memory controllers. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryMedia** [ {} ] | array<br><br>*read-only* | The value of this property shall be the media types of this Memory |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryType** | string, null<br><br>*read-write* | The value of this property shall be the type of Memory represented by this resource. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Metrics** {} | object<br><br>*read-write* | A reference to the Metrics associated with this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OperatingMemoryModes** [ {} ] | array<br><br>*read-only* | The value of this property shall be the memory modes supported by the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OperatingSpeedMhz** | number, null<br><br>*read-only* | The value of this property shall be the operating speed of Memory in MHz. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | This property shall indicate the part number as provided by the manufacturer of this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PersistentRegionSizeLimitMiB** | number, null<br><br>*read-only* | The value of this property shall be the total size of persistent regions in MiB. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerManagementPolicy** {} | object<br><br>*read-write* | This object shall contain properties which describe the power management policy for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RankCount** | number, null<br><br>*read-only* | The value of this property shall be number of ranks available in the Memory. The ranks could be used for spare or interleave. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Regions** [ {} ] | array<br><br>*read-only* | The value of this property shall be the memory region information within the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecurityCapabilities** {} | object<br><br>*read-write* | This object shall contain properties which describe the security capabilities of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | This property shall indicate the serial number as provided by the manufacturer of this Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SpareDeviceCount** | number, null<br><br>*read-only* | The value of this property shall be the number of unused spare devices available in the Memory. If memory devices fails, the spare device could be used. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SubsystemDeviceID** | string, null<br><br>*read-only* | The value of this property shall be the subsystem Device ID of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SubsystemVendorID** | string, null<br><br>*read-only* | The value of this property shall be the subsystem Vendor ID of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VendorID** | string, null<br><br>*read-only* | The value of this property shall be the vendor ID of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VolatileRegionSizeLimitMiB** | number, null<br><br>*read-only* | The value of this property shall be the total size of volatile regions in MiB. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### BaseModuleType:

| string | Description |
| --- | --- |
| LRDIMM | Load Reduced |
| Mini_RDIMM | Mini_RDIMM |
| Mini_UDIMM | Mini_UDIMM |
| RDIMM | Registered DIMM |
| SO_DIMM | SO_DIMM |
| SO_DIMM_16b | SO_DIMM_16b |
| SO_DIMM_32b | SO_DIMM_32b |
| SO_RDIMM_72b | SO_RDIMM_72b |
| SO_UDIMM_72b | SO_UDIMM_72b |
| UDIMM | UDIMM |

### ErrorCorrection:

| string | Description |
| --- | --- |
| AddressParity | Address Parity errors can be corrected |
| MultiBitECC | Multi-bit Data errors can be corrected by ECC |
| NoECC | No ECC available |
| SingleBitECC | Single bit Data error can be corrected by ECC |

### MemoryDeviceType:

| string | Description |
| --- | --- |
| DDR | DDR |
| DDR2 | DDR2 |
| DDR2_SDRAM | DDR2 SDRAM |
| DDR2_SDRAM_FB_DIMM | DDR2 SDRAM FB_DIMM |
| DDR2_SDRAM_FB_DIMM_PROBE | DDR2 SDRAM FB_DIMM PROBE |
| DDR3 | DDR3 |
| DDR3_SDRAM | DDR3 SDRAM |
| DDR4 | DDR4 |
| DDR4E_SDRAM | DDR4E SDRAM |
| DDR4_SDRAM | DDR4 SDRAM |
| DDR_SDRAM | DDR SDRAM |
| DDR_SGRAM | DDR SGRAM |
| EDO | EDO |
| FastPageMode | Fast Page Mode |
| LPDDR3_SDRAM | LPDDR3 SDRAM |
| LPDDR4_SDRAM | LPDDR4 SDRAM |
| PipelinedNibble | Pipelined Nibble |
| ROM | ROM |
| SDRAM | SDRAM |

### MemoryType:

| string | Description |
| --- | --- |
| DRAM | DRAM |
| NVDIMM_F | NVDIMM_F as defined by JEDEC. |
| NVDIMM_N | NVDIMM_N as defined by JEDEC. |
| NVDIMM_P | NVDIMM_P as defined by JEDEC. |


# MemoryMetrics 1.0.0

This resource shall be used to represent the Memory Metrics for a single Memory device in a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#MemoryMetrics.ClearCurrentPeriod** {} | object<br><br>*read-write* | This action shall set the CurrentPeriod object property values to zero. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **BlockSizeBytes** | number, null<br><br>*read-only* | The value of this property shall be the block size in bytes of all stucture elements. |
| **CurrentPeriod** { | object<br><br>*read-write* | This object shall contain properties which describe the CurrentPeriod metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** | number, null<br><br>*read-only* | The value of this property shall be number of blocks read since reset. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** | string, null<br><br>*read-only* | The value of this property shall be mumber of blocks written since reset. |
| } |   |   |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **HealthData** { | object<br><br>*read-write* | This object shall contain properties which describe the HealthData metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AlarmTrips** {} | object<br><br>*read-write* | This object shall contain properties describe the types of alarms that have been raised by the memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DataLossDetected** | boolean, null<br><br>*read-only* | The value of this property shall be data loss detection status, with true indicating data loss detected. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LastShutdownSuccess** | boolean, null<br><br>*read-only* | The value of this property shall be the status ofthe  last shutdown, with true indicating success. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PerformanceDegraded** | boolean, null<br><br>*read-only* | The value of this property shall be verformance degraded mode status, with true indicating perfomance degraded. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RemainingSpareBlockPercentage** | number, null<br><br>*read-only* | The value of this property shall be the remaining spare blocks in percentage. |
| } |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **LifeTime** { | object<br><br>*read-write* | This object shall contain properties which describe the LifeTime metrics for the current resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** | number, null<br><br>*read-only* | The value of this property shall be number of blocks read for the lifetime of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** | string, null<br><br>*read-only* | The value of this property shall be number of blocks written for the lifetime of the Memory. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# MessageRegistry 1.0.2

This resource shall be used to represent a message registry for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Language** | string<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code |
| **Messages** {} | object<br><br>*read-write* | The pattern property shall represent the suffix to be used in the MessageId and shall be unique within this message registry. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OwningEntity** | string<br><br>*read-only* | The value of this property shall be a string that represents the publisher of this registry. |
| **RegistryPrefix** | string<br><br>*read-only* | The value of this property shall be the prefix used in messageIDs which uniquely identifies all of the messages in this registry as belonging to this registry. |
| **RegistryVersion** | string<br><br>*read-only* | The value of this property shall be the version of this message registry.   The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification |

# MessageRegistryCollection

A Collection of MessageRegistry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Language** | string<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Messages** {} | object<br><br>*read-write* | The pattern property shall represent the suffix to be used in the MessageId and shall be unique within this message registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OwningEntity** | string<br><br>*read-only* | The value of this property shall be a string that represents the publisher of this registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RegistryPrefix** | string<br><br>*read-only* | The value of this property shall be the prefix used in messageIDs which uniquely identifies all of the messages in this registry as belonging to this registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RegistryVersion** | string<br><br>*read-only* | The value of this property shall be the version of this message registry.   The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# MessageRegistryFile 1.0.2

This resource shall be used to represent the Schema File locator resource for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Languages** [ {} ] | array<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code. |
| **Location** [ { | array<br><br>*read-only* | Location information for this schema file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ArchiveFile** | string<br><br>*read-only* | The value of this property shall be the file name of the individual schema file within the archive file specified by the ArchiveUri property. The file name shall conform to the syntax specified in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ArchiveUri** | string<br><br>*read-only* | The value of this property shall be a URI co-located with the Redfish service that specifies the location of the schema file.  This property shall only be used for archive files (zip or other formats).  The value of ArchiveFile shall have the file name of the individual schema file within the archive file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Language** | string<br><br>*read-only* | The value of this property shall be a string consisting of an RFC5646 language code or the string 'default'. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PublicationUri** | string<br><br>*read-only* | The value of this property shall be a URI not co-located with the Redfish service that specifies the canonical location of the schema file.  This property shall only be used for individual schema files. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Uri** | string<br><br>*read-only* | The value of this property shall be a URI co-located with the Redfish service that specifies the location of the schema file.  This property shall only be used for individual schema files.  The file name portion of the URI shall conform to the syntax specified in the Redfish specification. |
| } ] |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Registry** | string<br><br>*read-only* | The value of this property shall be the value of the Registry Name, Major and Minor version and shall conform to the syntax specified in the Redfish specification for the MessageId property without the MessageKey. |

# MessageRegistryFileCollection

A Collection of MessageRegistryFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Languages** [ {} ] | array<br><br>*read-only* | The value of this property shall be a string consisting of an RFC 5646 language code. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** [ {} ] | array<br><br>*read-only* | Location information for this schema file. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Registry** | string<br><br>*read-only* | The value of this property shall be the value of the Registry Name, Major and Minor version and shall conform to the syntax specified in the Redfish specification for the MessageId property without the MessageKey. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# Power 1.1.0

This resource shall be used to represent a power metrics resource for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **PowerControl** [ { | array<br><br>*read-write* | These properties shall be the definition for power control (power reading and limiting) for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string, null<br><br>*read-only* | The value of this property shall be the name of the Voltage sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerAllocatedWatts** | number, null<br><br>*read-only* | The value of this property shall represent the total power currently allocated to chassis resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerAvailableWatts** | number, null<br><br>*read-only* | The value of this property shall represent the amount of power capacity (in Watts) not already allocated and shall equal PowerCapacityWatts - PowerAllocatedWatts. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerCapacityWatts** | number, null<br><br>*read-only* | The value of this property shall represent the total power capacity that is available for allocation to the chassis resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerConsumedWatts** | number, null<br><br>*read-only* | The value of this property shall represent the actual power being consumed (in Watts) by the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerLimit** {} | object<br><br>*read-write* | This object shall contain power limit status and configuration information for this chassis |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerMetrics** {} | object<br><br>*read-write* | This object shall contain power metrics for power readings (interval, min/max/ave power consumption) for the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerRequestedWatts** | number, null<br><br>*read-only* | The value of this property shall represent the amount of power (in Watts) that the chassis resource is currently requesting be budgeted to it for future use. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem** [ {} ] | array<br><br>*read-write* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that is being limited. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } ] |   |   |
| **PowerControl\@odata.navigationLink** | string<br><br>*read-write* |  |
| **PowerSupplies** [ { | array<br><br>*read-write* | This object shall contain details of the power supplies associated with this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FirmwareVersion** | string, null<br><br>*read-only* | This property shall contain the firwmare version as defined by the manufacturer for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InputRanges** [ {} ] | array<br><br>*read-only* | The value of this property shall be a collection of ranges usable by the power supply unit. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LastPowerOutputWatts** | number, null<br><br>*read-only* | This property shall contain the average power output, measured in Watts, of the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LineInputVoltage** | number, null<br><br>*read-only* | This property shall contain the value in Volts of the line input voltage (measured or configured for) that the power supply has been configured to operate with or is currently receiving. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LineInputVoltageType** | string, null<br><br>*read-write* | This property shall contain the type of input line voltage supported by the associated power supply *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | The value of this property shall be the name of the organization responsible for producing the power supply. This organization might be the entity from whom the power supply is purchased, but this is not necessarily true. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This property shall contain the model information as defined by the manufacturer for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string, null<br><br>*read-only* | This property shall contain a descriptive name for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | This property shall contain the part number as defined by the manufacturer for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerCapacityWatts** | number, null<br><br>*read-only* | This property shall contiain the maximum amount of power, in Watts, that the associated power supply is rated to deliver. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplyType** | string, null<br><br>*read-write* | This property shall contain the input power type (AC or DC) of the associated power supply. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | The values of the properties in this array shall be used to show redundancy for power supplies and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem** [ {} ] | array<br><br>*read-write* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that is being limited. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | This property shall contain the serial number as defined by the manufacturer for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SparePartNumber** | string, null<br><br>*read-only* | This property shall contain the spare or replacement part number as defined by the manufacturer for the associated power supply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } ] |   |   |
| **PowerSupplies\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Redundancy** [ { | array<br><br>*read-only* | Redundancy information for the power subsystem of this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } ] |   |   |
| **Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Voltages** [ { | array<br><br>*read-write* | These properties shall be the definition for voltage sensors for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is below the normal range but is not yet fatal. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is below the normal range and is fatal. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is below the normal range but is not critical. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxReadingRange** | number, null<br><br>*read-only* | The value of this property shall indicate the highest possible value for CurrentReading. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinReadingRange** | number, null<br><br>*read-only* | The value of this property shall indicate the lowest possible value for CurrentReading. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string, null<br><br>*read-only* | The value of this property shall be the name of the Voltage sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PhysicalContext** | string<br><br>*read-write* | The value of this property shall be a description of the affected device or region within the chassis to which this voltage measurement applies. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ReadingVolts** | number, null<br><br>*read-only* | The value of this property shall be the current value of the voltage sensor's reading. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the areas or devices to which this voltage measurement applies. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SensorNumber** | number, null<br><br>*read-only* | The value of this property shall be a numerical identifier for this voltage sensor that is unique within this resource.  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is above the normal range but is not yet fatal. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is above the normal range and is fatal. Units shall use the same units as the related ReadingVolts propoerty. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the CurrentReading is above the normal range but is not critical. Units shall use the same units as the related ReadingVolts propoerty. |
| } ] |   |   |
| **Voltages\@odata.navigationLink** | string<br><br>*read-write* |  |

## Property Details

### LineInputVoltageType:

| string | Description |
| --- | --- |
| AC120V | AC 120V nominal input |
| AC240V | AC 240V nominal input |
| AC277V | AC 277V nominal input |
| ACHighLine | 277V AC input. Deprecated: Use AC277V |
| ACLowLine | 100-127V AC input. Deprecated: Use AC120V |
| ACMidLine | 200-240V AC input. Deprecated: Use AC240V |
| ACWideRange | Wide range AC input |
| ACandDCWideRange | Wide range AC or DC input |
| DC240V | DC 240V nominal input |
| DC380V | High Voltage DC input (380V) |
| DCNeg48V | -48V DC input |
| Unknown | The power supply line input voltage type cannot be determined |

### PhysicalContext:

| string | Description |
| --- | --- |
| Back | The back of the chassis |
| Backplane | A backplane within the chassis |
| CPU | A Processor (CPU) |
| ComputeBay | Within a compute bay |
| Exhaust | The exhaust point of the chassis |
| ExpansionBay | Within an expansion bay |
| Front | The front of the chassis |
| GPU | A Graphics Processor (GPU) |
| Intake | The intake point of the chassis |
| Lower | The lower portion of the chassis |
| NetworkBay | Within a networking bay |
| NetworkingDevice | A networking device |
| PowerSupply | A power supply |
| PowerSupplyBay | Within a power supply bay |
| Room | The room |
| StorageBay | Within a storage bay |
| StorageDevice | A storage device |
| SystemBoard | The system board (PCB) |
| Upper | The upper portion of the chassis |
| VoltageRegulator | A voltage regulator device |

### PowerSupplyType:

| string | Description |
| --- | --- |
| AC | Alternating Current (AC) power supply |
| ACorDC | Power Supply supports both DC or AC |
| DC | Direct Current (DC) power supply |
| Unknown | The power supply type cannot be determined |


# Processor 1.0.2


### ProcessorID

This object's properties shall contain values dependent on the value of the ProcessorArchitecture property, as listed in the sections below:

#### ProcessorArchitecture: x86

##### VendorId

This property shall contain a 12 byte, little-endian ASCII string derived from register values resulting from the execution of the CPUID instruction.  The value shall be constructed using the following algorithm:

~~~
k=0;
foreach reg (cpuid.0.ebx, cpuid.0.edx, cpuid.0.ecx){ ##NB: order must be ebx, edx, ecx
  for (i=0; i<=3; i++) { vendorID[ byte(k*4 + i) ] = reg[byte(i)]; }
  k++;
  }
~~~


##### IdentificationRegisters

This property shall contain the register contents resulting from the exeuction of the CPUID instruction.

##### EffectiveFamily

This property shall contain a value derived from register values resulting from the execution of the CPUID instruction.  The value shall use the following forumula:
~~~
((cpuid.1.eax & 0x0ff00000) >> 20) + ((cpuid.1.eax & 0x00000f00) >> 8)
~~~

##### EffectiveModel

This property shall contain a value derived from register values resulting from the execution of the CPUID instruction.  The value shall use the following forumula:
~~~
((cpuid.1.eax & 0x000f0000) >> 12) + ((cpuid.1.eax & 0x000000f0) >> 4)
~~~

##### Step

This property shall contain a value derived from register values resulting from the execution of the CPUID instruction.  The value shall use the following forumula:
~~~
(cpuid->eax & 0xf)
~~~

##### MicrocodeInfo

This property shall contain the 64-bit value contained in MSR 0x8B.

#### ProcessorArchitecture: All Others

The contents of this object are not specified.




|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **InstructionSet** | string, null<br><br>*read-write* | This property shall contain the string which identifies the instruction set of the processor contained in this socket. *See Property Details, below, for more information about this property.* |
| **Manufacturer** | string, null<br><br>*read-only* | This property shall contain a string which identifies the manufacturer of the processor. |
| **MaxSpeedMHz** | number, null<br><br>*read-only* | This property shall indicate the maximum rated clock speed of the processor in MHz. |
| **Model** | string, null<br><br>*read-only* | This property shall indicate the model information as provided by the manufacturer of this processor. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **ProcessorArchitecture** | string, null<br><br>*read-write* | This property shall contain the string which identifies the architecture of the processor contained in this Socket. *See Property Details, below, for more information about this property.* |
| **ProcessorId** { | object<br><br>*read-write* | This object shall contain identification information for this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveFamily** | string, null<br><br>*read-only* | This property shall indicate the effective Family information as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveModel** | string, null<br><br>*read-only* | This property shall indicate the effective Model information as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IdentificationRegisters** | string, null<br><br>*read-only* | This property shall include the raw CPUID instruction output as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MicrocodeInfo** | string, null<br><br>*read-only* | This property shall indicate the Microcode Information as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Step** | string, null<br><br>*read-only* | This property shall indicate the Step or revision string information as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VendorId** | string, null<br><br>*read-only* | This property shall indicate the Vendor Identification string information as provided by the manufacturer of this processor. |
| } |   |   |
| **ProcessorType** | string, null<br><br>*read-write* | This property shall contain the string which identifies the type of processor contained in this Socket. *See Property Details, below, for more information about this property.* |
| **Socket** | string, null<br><br>*read-only* | This property shall contain the string which identifies the physical location or socket of the processor. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **TotalCores** | number, null<br><br>*read-only* | This property shall indicate the total count of independent processor cores contained within this processor. |
| **TotalThreads** | number, null<br><br>*read-only* | This property shall indicate the total count of independent execution threads supported by this processor. |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### InstructionSet:

| string | Description |
| --- | --- |
| ARM-A32 | ARM 32-bit |
| ARM-A64 | ARM 64-bit |
| IA-64 | Intel IA-64 |
| MIPS32 | MIPS 32-bit |
| MIPS64 | MIPS 64-bit |
| OEM | OEM-defined |
| x86 | x86 32-bit |
| x86-64 | x86 64-bit |

### ProcessorArchitecture:

| string | Description |
| --- | --- |
| ARM | ARM |
| IA-64 | Intel Itanium |
| MIPS | MIPS |
| OEM | OEM-defined |
| x86 | x86 or x86-64 |

### ProcessorType:

| string | Description |
| --- | --- |
| Accelerator | An Accelerator |
| CPU | A Central Processing Unit |
| DSP | A Digital Signal Processor |
| FPGA | A Field Programmable Gate Array |
| GPU | A Graphics Processing Unit |
| OEM | An OEM-defined Processing Unit |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# ProcessorCollection

A Collection of Processor resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InstructionSet** | string, null<br><br>*read-write* | This property shall contain the string which identifies the instruction set of the processor contained in this socket. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | This property shall contain a string which identifies the manufacturer of the processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxSpeedMHz** | number, null<br><br>*read-only* | This property shall indicate the maximum rated clock speed of the processor in MHz. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This property shall indicate the model information as provided by the manufacturer of this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProcessorArchitecture** | string, null<br><br>*read-write* | This property shall contain the string which identifies the architecture of the processor contained in this Socket. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProcessorId** {} | object<br><br>*read-write* | This object shall contain identification information for this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProcessorType** | string, null<br><br>*read-write* | This property shall contain the string which identifies the type of processor contained in this Socket. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Socket** | string, null<br><br>*read-only* | This property shall contain the string which identifies the physical location or socket of the processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TotalCores** | number, null<br><br>*read-only* | This property shall indicate the total count of independent processor cores contained within this processor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TotalThreads** | number, null<br><br>*read-only* | This property shall indicate the total count of independent execution threads supported by this processor. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### InstructionSet:

| string | Description |
| --- | --- |
| ARM-A32 | ARM 32-bit |
| ARM-A64 | ARM 64-bit |
| IA-64 | Intel IA-64 |
| MIPS32 | MIPS 32-bit |
| MIPS64 | MIPS 64-bit |
| OEM | OEM-defined |
| x86 | x86 32-bit |
| x86-64 | x86 64-bit |

### ProcessorArchitecture:

| string | Description |
| --- | --- |
| ARM | ARM |
| IA-64 | Intel Itanium |
| MIPS | MIPS |
| OEM | OEM-defined |
| x86 | x86 or x86-64 |

### ProcessorType:

| string | Description |
| --- | --- |
| Accelerator | An Accelerator |
| CPU | A Central Processing Unit |
| DSP | A Digital Signal Processor |
| FPGA | A Field Programmable Gate Array |
| GPU | A Graphics Processing Unit |
| OEM | An OEM-defined Processing Unit |


# Role 1.0.2

This resource shall be used to represent resources that represent the user role for the user account.

|     |     |     |
| --- | --- | --- |
| **AssignedPrivileges** [ {} ] | array<br><br>*read-write* | The value of this property shall be the redfish privileges that the role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **IsPredefined** | boolean<br><br>*read-only* | The value of this property shall indicate if the role is a predefined role. . *See Property Details, below, for more information about this property.* |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **OemPrivileges** [ {} ] | array<br><br>*read-write* | The value of this property shall be the OEM privileges that this role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property. |

## Property Details

### IsPredefined:



Lucid ipsum there's no special reason to have property details for IsPredefined, but here is an example nonetheless.



# RoleCollection

A Collection of Role resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssignedPrivileges** [ {} ] | array<br><br>*read-write* | The value of this property shall be the redfish privileges that the role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IsPredefined** | boolean<br><br>*read-only* | The value of this property shall indicate if the role is a predefined role. . *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OemPrivileges** [ {} ] | array<br><br>*read-write* | The value of this property shall be the OEM privileges that this role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### IsPredefined:



Lucid ipsum there's no special reason to have property details for IsPredefined, but here is an example nonetheless.



# SecureBoot 1.0.0

This resource shall be used to represent a UEFI Secure Boot resource for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#SecureBoot.ResetKeys** {} | object<br><br>*read-write* | This action shall perform a reset of the Secure Boot key databases. The ResetAllKeysToDefault value shall reset the UEFI Secure Boot key databases to their default values. The DeleteAllKeys value shall delete the content of the UEFI Secure Boot key databases. The DeletePK value shall delete the content of the PK Secure boot key. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **SecureBootCurrentBoot** | string, null<br><br>*read-write* | The value of this property shall indicate the UEFI Secure Boot state during the current boot cycle. *See Property Details, below, for more information about this property.* |
| **SecureBootEnable** | boolean, null<br><br>*read-write* | Setting this property to true enables UEFI Secure Boot, and setting it to false disables it. This property can be enabled only in UEFI boot mode. |
| **SecureBootMode** | string, null<br><br>*read-write* | This property shall contain the current Secure Boot mode, as defined in the UEFI Specification. *See Property Details, below, for more information about this property.* |

## Property Details

### SecureBootCurrentBoot:

| string | Description |
| --- | --- |
| Disabled | Secure Boot is currently disabled. |
| Enabled | Secure Boot is currently enabled. |

### SecureBootMode:

| string | Description |
| --- | --- |
| AuditMode | Secure Boot is currently in Audit Mode. |
| DeployedMode | Secure Boot is currently in Deployed Mode. |
| SetupMode | Secure Boot is currently in Setup Mode. |
| UserMode | Secure Boot is currently in User Mode. |


# SerialInterface 1.0.2

This resource shall be used to represent serial resources as part of the Redfish specification.

|     |     |     |
| --- | --- | --- |
| **BitRate** | string<br><br>*read-write* | This property shall indicate the transmit and receive speed of the serial connection. *See Property Details, below, for more information about this property.* |
| **ConnectorType** | string<br><br>*read-write* | This property shall indicate the type of phyiscal connector used for this serial connection. *See Property Details, below, for more information about this property.* |
| **DataBits** | string<br><br>*read-write* | This property shall indicate number of data bits for the serial connection. *See Property Details, below, for more information about this property.* |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **FlowControl** | string<br><br>*read-write* | This property shall indicate the flow control mechanism for the serial connection. *See Property Details, below, for more information about this property.* |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **InterfaceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this interface is enabled. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Parity** | string<br><br>*read-write* | This property shall indicate parity information for a serial connection. *See Property Details, below, for more information about this property.* |
| **PinOut** | string, null<br><br>*read-write* | This property shall indicate the physical pin out for the serial connection. *See Property Details, below, for more information about this property.* |
| **SignalType** | string<br><br>*read-write* | This property shall indicate the type of serial signalling that will be utilized for the serial connection. *See Property Details, below, for more information about this property.* |
| **StopBits** | string<br><br>*read-write* | This property shall indicate the stop bits for the serial connection. *See Property Details, below, for more information about this property.* |

## Property Details

### BitRate:

| string |
| --- |
| 1200 | 
| 2400 | 
| 4800 | 
| 9600 | 
| 19200 | 
| 38400 | 
| 57600 | 
| 115200 | 
| 230400 | 

### ConnectorType:

| string |
| --- |
| RJ45 | 
| RJ11 | 
| DB9 Female | 
| DB9 Male | 
| DB25 Female | 
| DB25 Male | 
| USB | 
| mUSB | 
| uUSB | 

### DataBits:

| string |
| --- |
| 5 | 
| 6 | 
| 7 | 
| 8 | 

### FlowControl:

| string | Description |
| --- | --- |
| Hardware | Out of band flow control imposed |
| None | No flow control imposed |
| Software | XON/XOFF in-band flow control imposed |

### Parity:

| string |
| --- |
| None | 
| Even | 
| Odd | 
| Mark | 
| Space | 

### PinOut:

| string |
| --- |
| Cisco | 
| Cyclades | 
| Digi | 

### SignalType:

| string |
| --- |
| Rs232 | 
| Rs485 | 

### StopBits:

| string |
| --- |
| 1 | 
| 2 | 


# SerialInterfaceCollection

A Collection of SerialInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BitRate** | string<br><br>*read-write* | This property shall indicate the transmit and receive speed of the serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectorType** | string<br><br>*read-write* | This property shall indicate the type of phyiscal connector used for this serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DataBits** | string<br><br>*read-write* | This property shall indicate number of data bits for the serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FlowControl** | string<br><br>*read-write* | This property shall indicate the flow control mechanism for the serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InterfaceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this interface is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Parity** | string<br><br>*read-write* | This property shall indicate parity information for a serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PinOut** | string, null<br><br>*read-write* | This property shall indicate the physical pin out for the serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SignalType** | string<br><br>*read-write* | This property shall indicate the type of serial signalling that will be utilized for the serial connection. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**StopBits** | string<br><br>*read-write* | This property shall indicate the stop bits for the serial connection. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### BitRate:

| string |
| --- |
| 1200 | 
| 2400 | 
| 4800 | 
| 9600 | 
| 19200 | 
| 38400 | 
| 57600 | 
| 115200 | 
| 230400 | 

### ConnectorType:

| string |
| --- |
| RJ45 | 
| RJ11 | 
| DB9 Female | 
| DB9 Male | 
| DB25 Female | 
| DB25 Male | 
| USB | 
| mUSB | 
| uUSB | 

### DataBits:

| string |
| --- |
| 5 | 
| 6 | 
| 7 | 
| 8 | 

### FlowControl:

| string | Description |
| --- | --- |
| Hardware | Out of band flow control imposed |
| None | No flow control imposed |
| Software | XON/XOFF in-band flow control imposed |

### Parity:

| string |
| --- |
| None | 
| Even | 
| Odd | 
| Mark | 
| Space | 

### PinOut:

| string |
| --- |
| Cisco | 
| Cyclades | 
| Digi | 

### SignalType:

| string |
| --- |
| Rs232 | 
| Rs485 | 

### StopBits:

| string |
| --- |
| 1 | 
| 2 | 


# ServiceRoot 1.0.2

This object represents the root Redfish service.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.

|     |     |     |
| --- | --- | --- |
| **AccountService** { | object<br><br>*read-write* | The classes structure shall only contain a reference to a resource that complies to the AccountService schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutCounterResetAfter** | number<br><br>*read-write* | This property shall reference the threshold of time in seconds from the last failed login attempt at which point the AccountLockoutThreshold counter (that counts number of failed login attempts) is reset back to zero (at which point AccountLockoutThreshold failures would be required before the account is locked).  This value shall be less than or equal to AccountLockoutDuration. The threshold counter also resets to zero after each successful login. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutDuration** | number, null<br><br>*read-write* | This property shall reference the period of time in seconds that an account is locked after the number of failed login attempts reaches the threshold referenced by AccountLockoutThreshold, within the window of time referenced by AccountLockoutCounterResetAfter.  The value shall be greater than or equal to the value of AccountLockoutResetAfter.  If set to 0, no lockout shall occur. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutThreshold** | number, null<br><br>*read-write* | This property shall reference the threshold of failed login attempts at which point the user's account is locked.  If set to 0, no lockout shall ever occur. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Accounts** {} | object<br><br>*read-write* | This property shall contain the link to a collection of type ManagerAccountCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AuthFailureLoggingThreshold** | number<br><br>*read-write* | This property shall reference the threshold for when an authorization failure is logged.  This represents a modulo function value, thus the failure shall be logged every nth occurrence where n represents the value of this property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPasswordLength** | number<br><br>*read-only* | This property shall reference the maximum password length that the implementation will allow a password to be set to. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinPasswordLength** | number<br><br>*read-only* | This property shall reference the minimum password length that the implementation will allow a password to be set to. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Roles** {} | object<br><br>*read-write* | This property shall contain the link to a collection of type RoleCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } |   |   |
| **Chassis** { | object<br><br>*read-write* | This object shall only contain a reference to a collection of resources that comply to the Chassis schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EventService** { | object<br><br>*read-write* | The classes structure shall only contain a reference to a resource that complies to the EventService schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryAttempts** | number<br><br>*read-only* | The value of this property shall be the number of retrys attempted for any given event to the subscription destination before the subscription is terminated. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryIntervalSeconds** | number<br><br>*read-only* | The value of this property shall be the interval in seconds between the retry attempts for any given event to the subscription destination. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventTypesForSubscription** [ {} ] | array<br><br>*read-only* | The value of this property shall be the types of events that subscriptions can subscribe to.  The semantics associated with the enumerations values are defined in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Subscriptions** {} | object<br><br>*read-write* | The value of this property shall contain the link to a collection of type EventDestinationCollection. |
| } |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **JsonSchemas** { | object<br><br>*read-write* | This object shall only contain a reference to a collection of resources that comply to the SchemaFile schema where the files are Json-Schema files. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** {} | object<br><br>*read-write* | This property shall contain the link to a collection of Sessions. |
| } |   |   |
| **Managers** { | object<br><br>*read-write* | This object shall only contain a reference to a collection of resources that comply to the Managers schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **RedfishVersion** | string<br><br>*read-only* | The value of this string shall represent the version of the Redfish service.  The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification.  |
| **Registries** { | object<br><br>*read-write* | This object shall contain a reference to Message Registry. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **SessionService** { | object<br><br>*read-write* | The classes structure shall only contain a reference to a resource that complies to the SessionService schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SessionTimeout** | number<br><br>*read-write* | This property shall reference the threshold of time in seconds between requests on a specific session at which point the session service shall close the session due to inactivity. The session service shall support any value between the Validation.Minimum and Validation.Maximum. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** {} | object<br><br>*read-write* | This property shall contain the link to a collection of Sessions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } |   |   |
| **Systems** { | object<br><br>*read-write* | This object shall only contain a reference to a collection of resources that comply to the Systems schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Tasks** { | object<br><br>*read-write* | The classes structure shall only contain a reference to a resource that complies to the TaskService schema. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CompletedTaskOverWritePolicy** | string<br><br>*read-write* | The value of this property shall indicate how completed tasks are handled should the task service need to track more tasks. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTime** | string, null<br><br>*read-only* | The value of this property shall represent the current DateTime value for the TaskService, with offset from UTC, in Redfish Timestamp format. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LifeCycleEventOnTaskStateChange** | boolean<br><br>*read-only* | The value of this property, if set to true, shall indicate that the service shall send a LifeCycle event to ListenerDestinations registered for such events upon change of task state. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Tasks** {} | object<br><br>*read-write* | The value of this property shall be a link to a resource of type TaskCollection. |
| } |   |   |
| **UUID** | string, null<br><br>*read-write* | The value of this string shall represent the id of the Redfish service instance.  The format of this string shall be a 32-byte value in the form 8-4-4-4-12.  If SSDP is used, this value shall be an exact match of the UUID value returned in a 200OK from an SSDP M-SEARCH request during discovery. RFC4122 describes methods that can be used to create a UUID value. The value should be considered to be opaque. Client software should only treat the overall value as a universally unique identifier and should not interpret any sub-fields within the UUID. |

## Property Details

### CompletedTaskOverWritePolicy:

| string | Description |
| --- | --- |
| Manual | Completed tasks are not automatically overwritten |
| Oldest | Oldest completed tasks are overwritten |


# Session 1.0.2

This resource shall be used to represent a session for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Password** | string, null<br><br>*read-write* | The value of this property shall be the password for this session.  The value shall be null for GET requests. |
| **UserName** | string, null<br><br>*read-only* | The value of this property shall be the UserName that matches a registered account identified by a ManagerAccount resource registered with the Account Service. |

# SessionCollection

A Collection of Session resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Password** | string, null<br><br>*read-write* | The value of this property shall be the password for this session.  The value shall be null for GET requests. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UserName** | string, null<br><br>*read-only* | The value of this property shall be the UserName that matches a registered account identified by a ManagerAccount resource registered with the Account Service. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# SessionService 1.0.2

This resource shall be used to represent the Session Service Properties for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| **SessionTimeout** | number<br><br>*read-write* | This property shall reference the threshold of time in seconds between requests on a specific session at which point the session service shall close the session due to inactivity. The session service shall support any value between the Validation.Minimum and Validation.Maximum. |
| **Sessions** { | object<br><br>*read-write* | This property shall contain the link to a collection of Sessions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# SimpleStorage 1.1.0

This is the schema definition for the Simple Storage resource.  It represents the properties of a storage controller and its directly-attached devices.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Devices** [ { | array<br><br>*read-only* | This property shall contain a list of storage devices associated with this resource |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CapacityBytes** | number, null<br><br>*read-only* | The value of this property shall represent the size (in bytes) of the Storage Device. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | This property shall indicate the name of the manufacturer of this storage device. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This property shall indicate the model information as provided by the manufacturer of this storage device. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| } ] |   |   |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **UefiDevicePath** | string, null<br><br>*read-only* | This property shall contain the UEFI device path used to identify and locate the specific storage controller |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# SimpleStorageCollection

A Collection of SimpleStorage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Devices** [ {} ] | array<br><br>*read-only* | This property shall contain a list of storage devices associated with this resource |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UefiDevicePath** | string, null<br><br>*read-only* | This property shall contain the UEFI device path used to identify and locate the specific storage controller |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# Storage 1.0.0

This resource shall be used to represent resources that represent a storage subsystem in the Redfish specification.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Storage.SetEncryptionKey** {} | object<br><br>*read-write* | This defines the name of the custom action supported on this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Drives** [ { | array<br><br>*read-only* | A collection that indicates all the drives attached to the storage controllers that this resource represents. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssetTag** | string, null<br><br>*read-write* | The value of this property shall be an identifying string used to track the drive for inventory purposes. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlockSizeBytes** | number, null<br><br>*read-only* | This property shall contain size of the smallest addressible unit of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CapableSpeedGbs** | number, null<br><br>*read-only* | This property shall contain fastest capable bus speed of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CapacityBytes** | number, null<br><br>*read-only* | This property shall contain the raw size in bytes of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EncryptionAbility** | string, null<br><br>*read-write* | This property shall contain the encryption ability for the associated drive. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EncryptionStatus** | string, null<br><br>*read-write* | This property shall contain the encrytion status for the associated drive. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FailurePredicted** | boolean, null<br><br>*read-only* | This property shall contain failure information as defined by the manufacturer for the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HotspareType** | string, null<br><br>*read-write* | This property shall contain the hot spare type for the associated drive. If the drive is currently serving as a hot spare its Status.State field shall be 'StandbySpare' and 'Enabled' when it is being used as part of a Volume. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Identifiers** [ {} ] | array<br><br>*read-only* | This property shall contain a list of all known durable names for the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IndicatorLED** | string, null<br><br>*read-write* | This value of this property shall contain the indicator light state for the indicator light associated with this drive. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** [ {} ] | array<br><br>*read-only* | This property shall contain location information of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | The value of this property shall be the name of the organization responsible for producing the drive. This organization might be the entity from whom the drive is purchased, but this is not necessarily true. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MediaType** | string, null<br><br>*read-write* | This property shall contain the type of media contained in the associated drive. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | The value of this property shall be the name by which the manufacturer generally refers to the drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NegotiatedSpeedGbs** | number, null<br><br>*read-only* | This property shall contain current bus speed of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PredictedMediaLifeLeftPercent** | number, null<br><br>*read-only* | This property shall contain an indicator of the percentage of life remaining in the Drive's media. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Protocol** | , null<br><br>*read-write* | This property shall contain the protocol the associated drive is using to communicate to the storage controller for this system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Revision** | string, null<br><br>*read-only* | This property shall contain the revision as defined by the manufacturer for the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RotationSpeedRPM** | number, null<br><br>*read-only* | This property shall contain rotation speed of the associated drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SKU** | string, null<br><br>*read-only* | The value of this property shall be the stock-keeping unit number for this drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | The value of this property shall be a manufacturer-allocated number used to identify the drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**StatusIndicator** | string, null<br><br>*read-write* | The value of this property shall contain the status indicator state for the status indicator associated with this drive. The valid values for this property are specified through the Redfish.AllowableValues annotation. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Drives\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures** [ {} ] | array<br><br>*read-only* | The value of this property shall reference a resource of type Chassis that represents the physical containers attached to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Redundancy** [ { | array<br><br>*read-only* | Redundancy information for the storage subsystem |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } ] |   |   |
| **Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **StorageControllers** [ {} ] | array<br><br>*read-only* | A collection that indicates all the storage controllers that this resource represents. |
| **StorageControllers\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Volumes** [ { | array<br><br>*read-only* | A collection that indicates all the volumes produced by the storage controllers that this resource represents. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlockSizeBytes** | number, null<br><br>*read-only* | This property shall contain size of the smallest addressible unit of the associated volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CapacityBytes** | number, null<br><br>*read-only* | This property shall contain the size in bytes of the associated volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Encrypted** | boolean, null<br><br>*read-write* | This property shall contain a boolean indicator if the Volume is currently utilizing encryption or not. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EncryptionTypes** [ {} ] | array<br><br>*read-write* | This property shall contain the types of encryption used by this Volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Identifiers** [ {} ] | array<br><br>*read-only* | This property shall contain a list of all known durable names for the associated volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Operations** [ {} ] | array<br><br>*read-only* | This property shall contain a list of all currently running on the Volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OptimumIOSizeBytes** | number, null<br><br>*read-only* | This property shall contain the optimum IO size to use when performing IO on this volume. For logical disks, this is the stripe size. For physical disks, this describes the physical sector size. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VolumeType** | string, null<br><br>*read-write* | This property shall contain failure information as defined by the manufacturer for the associated drive. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Volumes\@odata.navigationLink** | string<br><br>*read-write* |  |

## Property Details

### EncryptionAbility:

| string | Description |
| --- | --- |
| None | The drive is not capable of self encryption |
| Other | The drive is capable of self encryption through some other means |
| SelfEncryptingDrive | The drive is capable of self encryption per the Trusted Computing Group's Self Encrypting Drive Standard |

### EncryptionStatus:

| string | Description |
| --- | --- |
| Foreign | The drive is currently encrypted, the data is not accessible to the user, and the system requires user intervention to expose the data |
| Locked | The drive is currently encrypted and the data is not accessible to the user, however the system has the ability to unlock the drive automatically |
| Unecrypted | The drive is not currently encrypted |
| Unlocked | The drive is currently encrypted but the data is accessible to the user unencrypted |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HotspareType:

| string | Description |
| --- | --- |
| Chassis | The drive is currently serving as a hotspare for all other drives in the chassis |
| Dedicated | The drive is currently serving as a hotspare for a user defined set of drives |
| Global | The drive is currently serving as a hotspare for all other drives in the storage system |
| None | The drive is not currently a hotspare |

### IndicatorLED:

| string | Description |
| --- | --- |
| Blinking | The Indicator LED is blinking. |
| Lit | The Indicator LED is lit. |
| Off | The Indicator LED is off. |

### MediaType:

| string | Description |
| --- | --- |
| HDD | The drive media type is traditional magnetic platters |
| SMR | The drive media type is shingled magnetic recording |
| SSD | The drive media type is solid state or flash memory |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |

### StatusIndicator:

| string | Description |
| --- | --- |
| Fail | The drive has failed. |
| Hotspare | The drive is marked to be automatically rebuilt and used as a replacement for a failed drive. |
| InACriticalArray | The array that this drive is a part of is degraded. |
| InAFailedArray | The array that this drive is a part of is failed. |
| OK | The drive is OK. |
| PredictiveFailureAnalysis | The drive is still working but predicted to fail soon. |
| Rebuild | The drive is being rebuilt. |

### VolumeType:

| string | Description |
| --- | --- |
| Mirrored | The volume is a mirrored device |
| NonRedundant | The volume is a non-redundant storage device |
| RawDevice | The volume is a raw physical device without any RAID or other virtualization applied |
| SpannedMirrors | The volume is a spanned set of mirrored devices |
| SpannedStripesWithParity | The volume is a spanned set of devices which uses parity to retain redundant information |
| StripedWithParity | The volume is a device which uses parity to retain redundant information |


# StorageCollection

A Collection of Storage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** [ {} ] | array<br><br>*read-only* | A collection that indicates all the drives attached to the storage controllers that this resource represents. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | Redundancy information for the storage subsystem |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**StorageControllers** [ {} ] | array<br><br>*read-only* | A collection that indicates all the storage controllers that this resource represents. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**StorageControllers\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes** [ {} ] | array<br><br>*read-only* | A collection that indicates all the volumes produced by the storage controllers that this resource represents. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes\@odata.navigationLink** | string<br><br>*read-write* |  |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# Task 1.0.2

This resource shall be used to represent a task for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **EndTime** | string<br><br>*read-only* | The value of this property shall indicate the time the task was completed. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Messages** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of messages associated with the task. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **StartTime** | string<br><br>*read-only* | The value of this property shall indicate the time the task was started. |
| **TaskState** | string<br><br>*read-write* | The value of this property shall indicate the state of the task.  New shall be used to indicate that the task is a new task which has just been instantiated and is in the initial state and indicates it has never been started.  Starting shall be used to indicate that the task is moving from the New, Suspended, or Service states into the Running state.  Running shall be used to indicate that the Task is running.  Suspended shall be used to indicate  that the Task is stopped (e.g., by a user), but can be restarted in a seamless manner.  Interrupted shall be used to indicate  that the Task was interrupted (e.g., by a server crash) in the middle of processing, and the user should either re-run/restart the Task.  Pending shall be used to indicate  that the Task has been queued and will be scheduled for processing as soon as resources are available to handle the request.  Stopping shall be used to indicate that the Task is in the process of moving to a Completed, Killed, or Exception state.  Completed shall be used to indicate that the task has completed normally.  Killed shall be used to indicate  that the task has been stopped by a Kill state change request (non-graceful shutdown).  Exception shall be used to indicate  that the Task is in an abnormal state that might be indicative of an error condition.  Service shall be used to indicate that the Task is in a state that supports problem discovery, or resolution, or both.  This state is used when a corrective action is possible.  *See Property Details, below, for more information about this property.* |
| **TaskStatus** | string<br><br>*read-write* | The value of this property shall be the completion status of the task, as defined in the Status section of the Redfish specification and shall not be set until the task has completed. *See Property Details, below, for more information about this property.* |

## Property Details

### TaskState:

| string | Description |
| --- | --- |
| Completed | Task has completed |
| Exception | Task has stopped due to an exception condition |
| Interrupted | Task has been interrupted |
| Killed | Task was terminated |
| New | A new task |
| Pending | Task is pending and has not started |
| Running | Task is running normally |
| Service | Task is running as a service |
| Starting | Task is starting |
| Stopping | Task is in the process of stopping |
| Suspended | Task has been suspended |

### TaskStatus:

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |


# TaskCollection

A Collection of Task resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EndTime** | string<br><br>*read-only* | The value of this property shall indicate the time the task was completed. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Messages** [ {} ] | array<br><br>*read-only* | The value of this property shall be an array of messages associated with the task. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**StartTime** | string<br><br>*read-only* | The value of this property shall indicate the time the task was started. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TaskState** | string<br><br>*read-write* | The value of this property shall indicate the state of the task.  New shall be used to indicate that the task is a new task which has just been instantiated and is in the initial state and indicates it has never been started.  Starting shall be used to indicate that the task is moving from the New, Suspended, or Service states into the Running state.  Running shall be used to indicate that the Task is running.  Suspended shall be used to indicate  that the Task is stopped (e.g., by a user), but can be restarted in a seamless manner.  Interrupted shall be used to indicate  that the Task was interrupted (e.g., by a server crash) in the middle of processing, and the user should either re-run/restart the Task.  Pending shall be used to indicate  that the Task has been queued and will be scheduled for processing as soon as resources are available to handle the request.  Stopping shall be used to indicate that the Task is in the process of moving to a Completed, Killed, or Exception state.  Completed shall be used to indicate that the task has completed normally.  Killed shall be used to indicate  that the task has been stopped by a Kill state change request (non-graceful shutdown).  Exception shall be used to indicate  that the Task is in an abnormal state that might be indicative of an error condition.  Service shall be used to indicate that the Task is in a state that supports problem discovery, or resolution, or both.  This state is used when a corrective action is possible.  *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**TaskStatus** | string<br><br>*read-write* | The value of this property shall be the completion status of the task, as defined in the Status section of the Redfish specification and shall not be set until the task has completed. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### TaskState:

| string | Description |
| --- | --- |
| Completed | Task has completed |
| Exception | Task has stopped due to an exception condition |
| Interrupted | Task has been interrupted |
| Killed | Task was terminated |
| New | A new task |
| Pending | Task is pending and has not started |
| Running | Task is running normally |
| Service | Task is running as a service |
| Starting | Task is starting |
| Stopping | Task is in the process of stopping |
| Suspended | Task has been suspended |

### TaskStatus:

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |


# TaskService 1.0.2

This resource shall be used to represent a task service for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **CompletedTaskOverWritePolicy** | string<br><br>*read-write* | The value of this property shall indicate how completed tasks are handled should the task service need to track more tasks. *See Property Details, below, for more information about this property.* |
| **DateTime** | string, null<br><br>*read-only* | The value of this property shall represent the current DateTime value for the TaskService, with offset from UTC, in Redfish Timestamp format. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **LifeCycleEventOnTaskStateChange** | boolean<br><br>*read-only* | The value of this property, if set to true, shall indicate that the service shall send a LifeCycle event to ListenerDestinations registered for such events upon change of task state. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | The value of this property shall be a boolean indicating whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Tasks** { | object<br><br>*read-write* | The value of this property shall be a link to a resource of type TaskCollection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** [ {} ] | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } |   |   |

## Property Details

### CompletedTaskOverWritePolicy:

| string | Description |
| --- | --- |
| Manual | Completed tasks are not automatically overwritten |
| Oldest | Oldest completed tasks are overwritten |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# Thermal 1.1.0

This resource shall be used to represent a thermal metrics resource for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Fans** [ { | array<br><br>*read-write* | These properties shall be the definition for fans for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FanName** | string, null<br><br>*read-only* | The value of this property shall be the name of the fan. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is below the normal range but is not yet fatal. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is below the normal range and is fatal. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is below the normal range but is not critical. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxReadingRange** | number, null<br><br>*read-only* | The value of this property shall indicate the highest possible value for Reading. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinReadingRange** | number, null<br><br>*read-only* | The value of this property shall indicate the lowest possible value for Reading. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string, null<br><br>*read-only* | The value of this property shall be the name of the fan. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PhysicalContext** | string<br><br>*read-write* | The value of this property shall be a description of the affected device or region within the chassis to which this fan is associated. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Reading** | number, null<br><br>*read-only* | The value of this property shall be the current value of the fan sensor's reading. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ReadingUnits** | string, null<br><br>*read-write* | The value of this property shall be the units in which the fan's reading and thresholds are measured. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** [ {} ] | array<br><br>*read-only* | The values of the properties in this array shall be used to show redundancy for fans and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem** [ {} ] | array<br><br>*read-write* | The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that are being serviced by this fan. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is above the normal range but is not yet fatal. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is above the normal range and is fatal. The units shall be the same units as the related Reading property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the Reading is above the normal range but is not critical. The units shall be the same units as the related Reading property. |
| } ] |   |   |
| **Fans\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Redundancy** [ { | array<br><br>*read-only* | The values of the properties in this array shall be used to show redundancy for fans and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| } ] |   |   |
| **Redundancy\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **Temperatures** [ { | array<br><br>*read-write* | These properties shall be the definition for temperature sensors for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is below the normal range but is not yet fatal. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is below the normal range and is fatal. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LowerThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is below the normal range but is not critical. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxReadingRangeTemp** | number, null<br><br>*read-only* | The value of this property shall indicate the highest possible value for ReadingCelsius. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemberId** | string<br><br>*read-write* | The value of this string shall uniquely identify the member within the collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinReadingRangeTemp** | number, null<br><br>*read-only* | The value of this property shall indicate the lowest possible value for ReadingCelsius. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string, null<br><br>*read-only* | The value of this property shall be the name of the temperature sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PhysicalContext** | string<br><br>*read-write* | The value of this property shall be a description of the affected device or region within the chassis to which this temperature measurement applies. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ReadingCelsius** | number, null<br><br>*read-only* | The value of this property shall be the current value of the temperature sensor's reading. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem** [ {} ] | array<br><br>*read-only* | The value of this property shall the array of IDs of areas or devices to which this temperature measurement applies. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RelatedItem\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SensorNumber** | number, null<br><br>*read-only* | The value of this property shall be a numerical identifier for this temperature sensor that is unique within this resource.  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is above the normal range but is not yet fatal. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdFatal** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is above the normal range and is fatal. The units shall be the same units as the related ReadingCelsius property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UpperThresholdNonCritical** | number, null<br><br>*read-only* | The value of this property shall indicate the ReadingCelsius is above the normal range but is not critical. The units shall be the same units as the related ReadingCelsius property. |
| } ] |   |   |
| **Temperatures\@odata.navigationLink** | string<br><br>*read-write* |  |

## Property Details

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### PhysicalContext:

| string | Description |
| --- | --- |
| Back | The back of the chassis |
| Backplane | A backplane within the chassis |
| CPU | A Processor (CPU) |
| ComputeBay | Within a compute bay |
| Exhaust | The exhaust point of the chassis |
| ExpansionBay | Within an expansion bay |
| Front | The front of the chassis |
| GPU | A Graphics Processor (GPU) |
| Intake | The intake point of the chassis |
| Lower | The lower portion of the chassis |
| NetworkBay | Within a networking bay |
| NetworkingDevice | A networking device |
| PowerSupply | A power supply |
| PowerSupplyBay | Within a power supply bay |
| Room | The room |
| StorageBay | Within a storage bay |
| StorageDevice | A storage device |
| SystemBoard | The system board (PCB) |
| Upper | The upper portion of the chassis |
| VoltageRegulator | A voltage regulator device |

### ReadingUnits:

| string | Description |
| --- | --- |
| Percent | Indicates that the fan reading and thresholds are measured in percentage. |
| RPM | Indicates that the fan reading and thresholds are measured in rotations per minute. |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |


# VLanNetworkInterface 1.0.2

This resource contains information for a Virtual LAN (VLAN) network instance available on a manager, system or other device.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **VLANEnable** | boolean, null<br><br>*read-write* | The value of this property shall be used to indicate if this VLAN is enabled for this interface. |
| **VLANId** | number, null<br><br>*read-write* | The value of this property shall be used to indicate the VLAN identifier for this VLAN. |

# VLanNetworkInterfaceCollection

A Collection of VLanNetworkInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VLANEnable** | boolean, null<br><br>*read-write* | The value of this property shall be used to indicate if this VLAN is enabled for this interface. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VLANId** | number, null<br><br>*read-write* | The value of this property shall be used to indicate the VLAN identifier for this VLAN. |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

# VirtualMedia 1.0.2

This resource shall be used to represent a virtual media service for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **ConnectedVia** | string, null<br><br>*read-write* | The value of this property shall indicate the current connection method from a client to the virtual media represented by this resource.  A value of NotConnected shall indicate no connection is present.  A value of URI shall indicate that a remote connection via a URI reference type is being used.  *See Property Details, below, for more information about this property.* |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Image** | string, null<br><br>*read-only* | The value of this string shall be an URI.  A null value indicated no image connection. |
| **ImageName** | string, null<br><br>*read-only* | The value of this property shall be the name of the image.  |
| **Inserted** | boolean, null<br><br>*read-only* | The value of this property shall be used to indicate if media is present in the virtual media device.  This is usually only applicable to remoting of devices and not for image virtual media usage.  |
| **MediaTypes** [ {} ] | array<br><br>*read-only* | The values of this array shall be the supported media types for this connection. |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **WriteProtected** | boolean, null<br><br>*read-only* | The value of this property shall be used to indicate if the remote device media prevents writing to that media.  |

## Property Details

### ConnectedVia:

| string | Description |
| --- | --- |
| Applet | Connected to a client application |
| NotConnected | No current connection |
| Oem | Connected via an OEM-defined method |
| URI | Connected to a URI location |


# VirtualMediaCollection

A Collection of VirtualMedia resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Members** [ { | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectedVia** | string, null<br><br>*read-write* | The value of this property shall indicate the current connection method from a client to the virtual media represented by this resource.  A value of NotConnected shall indicate no connection is present.  A value of URI shall indicate that a remote connection via a URI reference type is being used.  *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Image** | string, null<br><br>*read-only* | The value of this string shall be an URI.  A null value indicated no image connection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ImageName** | string, null<br><br>*read-only* | The value of this property shall be the name of the image.  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Inserted** | boolean, null<br><br>*read-only* | The value of this property shall be used to indicate if media is present in the virtual media device.  This is usually only applicable to remoting of devices and not for image virtual media usage.  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MediaTypes** [ {} ] | array<br><br>*read-only* | The values of this array shall be the supported media types for this connection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**WriteProtected** | boolean, null<br><br>*read-only* | The value of this property shall be used to indicate if the remote device media prevents writing to that media.  |
| } ] |   |   |
| **Members\@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |

## Property Details

### ConnectedVia:

| string | Description |
| --- | --- |
| Applet | Connected to a client application |
| NotConnected | No current connection |
| Oem | Connected via an OEM-defined method |
| URI | Connected to a URI location |


# Volume 1.0.0

This resource shall be used to represent a volume, virtual disk, logical disk, LUN, or other logical storage for a Redfish implementation.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The Actions property shall contain the available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Volume.Initialize** {} | object<br><br>*read-write* | This defines the name of the custom action supported on this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **BlockSizeBytes** | number, null<br><br>*read-only* | This property shall contain size of the smallest addressible unit of the associated volume. |
| **CapacityBytes** | number, null<br><br>*read-only* | This property shall contain the size in bytes of the associated volume. |
| **Description** | string, null<br><br>*read-only* | This object represents the Description property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Encrypted** | boolean, null<br><br>*read-write* | This property shall contain a boolean indicator if the Volume is currently utilizing encryption or not. |
| **EncryptionTypes** [ {} ] | array<br><br>*read-write* | This property shall contain the types of encryption used by this Volume. |
| **Id** | string<br><br>*read-only* | This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| **Identifiers** [ { | array<br><br>*read-only* | This property shall contain a list of all known durable names for the associated volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DurableName** | string, null<br><br>*read-only* | This property shall contain the world wide unique identifier for the resource. The string shall be in the format described by the value of the Identifier.DurableNameFormat property |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DurableNameFormat** | string, null<br><br>*read-write* | This property shall represent the format of the DurableName property. *See Property Details, below, for more information about this property.* |
| } ] |   |   |
| **Links** { | object<br><br>*read-only* | The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** [ {} ] | array<br><br>*read-only* | The value of this property shall be a reference to the resources that this volume is associated with and shall reference resources of type Drive. This property shall only contain references to Drive entities which are currently members of the Volume, not hot spare Drives which are not currently a member of the volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives\@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. |
| } |   |   |
| **Name** | string<br><br>*read-only* | This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*. |
| **Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| **Operations** [ { | array<br><br>*read-only* | This property shall contain a list of all currently running on the Volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssociatedTask** {} | object<br><br>*read-write* | This resource shall be used to represent a task for a Redfish implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OperationName** | string, null<br><br>*read-only* | The name of the operation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PercentageComplete** | number, null<br><br>*read-only* | The percentage of the operation that has been completed. |
| } ] |   |   |
| **OptimumIOSizeBytes** | number, null<br><br>*read-only* | This property shall contain the optimum IO size to use when performing IO on this volume. For logical disks, this is the stripe size. For physical disks, this describes the physical sector size. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | string, null<br><br>*read-write* | This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | The value of this string shall be of the format for the reserved word *Oem*. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | string, null<br><br>*read-write* | This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable. *See Property Details, below, for more information about this property.* |
| } |   |   |
| **VolumeType** | string, null<br><br>*read-write* | This property shall contain failure information as defined by the manufacturer for the associated drive. *See Property Details, below, for more information about this property.* |

## Property Details

### DurableNameFormat:

| string | Description |
| --- | --- |
| EUI | IEEE-defined 64-bit Extended Unique Identifier |
| FC_WWN | Fibre Channel World Wide Name |
| NAA | Name Address Authority Format |
| UUID | Universally Unique Identifier |
| iQN | iSCSI Qualified Name |

### Health:



Automatically create & reinforce good meeting habits


| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### HealthRollup:



LOVE LOVE LOVE the Basecamp integration! It changed the way I prepare for, take notes, and handle to-dos in my meetings – all for the good!

| string | Description |
| --- | --- |
| Critical | A critical condition exists that requires immediate attention |
| OK | Normal |
| Warning | A condition exists that requires attention |

### State:

| string | Description |
| --- | --- |
| Absent | This function or resource is not present or not detected |
| Disabled | This function or resource has been disabled |
| Enabled | This function or resource has been enabled |
| InTest | This function or resource is undergoing testing |
| StandbyOffline | This function or resource is enabled, but awaiting an external action to activate it |
| StandbySpare | This function or resource is part of a redundancy set and is awaiting a failover or other external action to activate it. |
| Starting | This function or resource is starting |
| UnavailableOffline | This function or resource is present but cannot be used |

### VolumeType:

| string | Description |
| --- | --- |
| Mirrored | The volume is a mirrored device |
| NonRedundant | The volume is a non-redundant storage device |
| RawDevice | The volume is a raw physical device without any RAID or other virtualization applied |
| SpannedMirrors | The volume is a spanned set of mirrored devices |
| SpannedStripesWithParity | The volume is a spanned set of devices which uses parity to retain redundant information |
| StripedWithParity | The volume is a device which uses parity to retain redundant information |



# This is an example Postscript

## What Lucid does for you

 * Sends out a scheduling poll to find the best time for everyone
 * Translates meeting times into each person’s time zone
 * Formats a professional meeting invitation email
 * Makes sure people get the meeting on their calendar
 * Sends meeting reminders on the day of the meeting
 * Saves your contacts so you can easily select the people to invite for the next meeting



Lucid brings clarity to your meetings by making it easy for everyone in an organization to run consistently successful meetings using your chosen process.


