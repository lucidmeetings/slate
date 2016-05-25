---
title: Redfish Schema

language tabs:
  - shell

search: true
---


# AccountService 1.0.2




Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.

|     |     |     |
| --- | --- | --- |
| **AccountLockoutCounterResetAfter** | number<br><br>*read-write* | The interval of time in seconds since the last failed login attempt at which point the lockout threshold counter for the account is reset to zero. Must be less than or equal to AccountLockoutDuration |
| **AccountLockoutDuration** | number, null<br><br>*read-write* | The time in seconds an account is locked after the account lockout threshold is met. Must be >= AccountLockoutResetAfter. If set to 0, no lockout will occur. |
| **AccountLockoutThreshold** | number, null<br><br>*read-write* | The number of failed login attempts before a user account is locked for a specified duration. (0=never locked) |
| **Accounts** { | object<br><br>*read-write* | A Collection of ManagerAccount resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **AuthFailureLoggingThreshold** | number<br><br>*read-write* | This is the number of authorization failures that need to occur before the failure attempt is logged to the manager log. |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **MaxPasswordLength** | number<br><br>*read-only* | This is the maximum password length for this service. |
| **MinPasswordLength** | number<br><br>*read-only* | This is the minimum password length for this service. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Roles** { | object<br><br>*read-write* | A Collection of Role resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |

# AttributeRegistry 1.0.0




An Attribute Registry is a set of key-value pairs which are specific to a particular implementation or product, such that creating standardized property names would be impractical.  This schema describes the structure of a Registry, and also includes mechanisms for building user interfaces (menus) allowing consistent navigation of the contents.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Language** | string<br><br>*read-only* | This is the RFC 5646 compliant language code for the registry. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **OwningEntity** | string<br><br>*read-only* | This is the organization or company that publishes this registry. |
| **RegistryEntries** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Menus** | array<br><br>*read-only* | The array containing the attributes menus and their hierarchy. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Attributes** | array<br><br>*read-only* | The array containing the attributes and their possible values. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Dependencies** | array<br><br>*read-only* | The array containing a list of dependencies of attributes on this component. |
| } |   |   |
| **RegistryVersion** | string<br><br>*read-only* | This is the attribute registry version which is used in the middle portion of a AttributeRegistry. |
| **SupportedSystems** | array<br><br>*read-write* | Array of systems supported by this attribute registry. |

# Bios 1.0.0




Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ResetBios** { | object<br><br>*read-write* | This action is used to reset the BIOS attributes to default. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ChangePassword** { | object<br><br>*read-write* | This action is used to change the BIOS passwords. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **AttributeRegistry** | string, null<br><br>*read-write* | The Resource ID of the Attribute Registry for the BIOS Attributes resource. |
| **Attributes** {} | object<br><br>*read-write* |  |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Chassis 1.2.0




A Chassis represents the physical components for any system.  This resource represents the sheet-metal confined spaces and logical zones like racks, enclosures, chassis and all other containers. Subsystems (like sensors), which operate outside of a system's data plane (meaning the resources are not accessible to software running on the system) are linked either directly or indirectly through this resource.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Chassis.Reset** { | object<br><br>*read-write* | This action is used to reset the chassis. This action resets the chassis, not Systems or other contained resources, although side effects may occur which affect those resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The user assigned asset tag for this chassis. |
| **ChassisType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **IndicatorLED** | <br><br>*read-write* | The state of the indicator LED, used to identify the chassis. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ContainedBy** { | object<br><br>*read-only* | A reference to the chassis that this chassis is contained by. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PhysicalSecurity** {} | object<br><br>*read-write* | The state of the physical security sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IndicatorLED** | <br><br>*read-write* | The state of the indicator LED, used to identify the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ChassisType** | string<br><br>*read-only* | This property indicates the type of physical form factor of this resource. *See Property Details, below, for more information about this property.* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LogServices** {} | object<br><br>*read-only* | A reference to the logs for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Thermal** {} | object<br><br>*read-only* | A reference to the thermal properties (fans, cooling, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | This is the manufacturer of this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | The part number for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerState** | <br><br>*read-only* | This is the current power state of the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This is the model number for the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssetTag** | string, null<br><br>*read-write* | The user assigned asset tag for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SKU** | string, null<br><br>*read-only* | This is the SKU for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | The serial number for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Power** {} | object<br><br>*read-only* | A reference to the power properties (power supplies, power policies, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** | array<br><br>*read-only* | An array of references to the disk drives located in this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** | array<br><br>*read-only* | An array of ID[s] of resources that power this chassis. Normally the ID will be a chassis or a specific set of powerSupplies |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** | array<br><br>*read-only* | An array of ID[s] of resources that cool this chassis. Normally the ID will be a chassis or a specific set of fans. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains** | array<br><br>*read-only* | An array of references to any other chassis that this chassis has in it. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** | array<br><br>*read-only* | An array of references to the Managers responsible for managing this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis** | array<br><br>*read-only* | An array of references to the managers located in this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage** | array<br><br>*read-only* | An array of references to the storage subsystems connected to or inside this Chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems** | array<br><br>*read-only* | An array of references to the computer systems contained in this chassis.  This will only reference ComputerSystems that are directly and wholly contained in this chassis. |
| } |   |   |
| **Location** *(v1.2.0)* { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Info** | string, null<br><br>*read-only* | This indicates the location of the resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InfoFormat** | string, null<br><br>*read-only* | This represents the format of the Info property. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| } |   |   |
| **LogServices** { | object<br><br>*read-only* | A reference to the logs for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Manufacturer** | string, null<br><br>*read-only* | This is the manufacturer of this chassis. |
| **Model** | string, null<br><br>*read-only* | This is the model number for the chassis. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **PartNumber** | string, null<br><br>*read-only* | The part number for this chassis. |
| **PhysicalSecurity** *(v1.1.0)* { | object<br><br>*read-write* | The state of the physical security sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorReArm** | <br><br>*read-only* | This indicates how the Normal state to be restored. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorNumber** | number, null<br><br>*read-only* | A numerical identifier to represent the physical security sensor. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensor** | <br><br>*read-write* | This indicates the known state of the physical security sensor, such as if it is hardware intrusion detected. |
| } |   |   |
| **Power** { | object<br><br>*read-only* | A reference to the power properties (power supplies, power policies, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** | array<br><br>*read-only* | Redundancy information for the power subsystem of this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl** | array<br><br>*read-write* | This is the definition for power control function (power reading/limiting). |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages** | array<br><br>*read-write* | This is the definition for voltage sensors. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies** | array<br><br>*read-write* | Details of the power supplies associated with this system or device |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **PowerState** *(v1.0.1)* | <br><br>*read-only* | This is the current power state of the chassis. |
| **SKU** | string, null<br><br>*read-only* | This is the SKU for this chassis. |
| **SerialNumber** | string, null<br><br>*read-only* | The serial number for this chassis. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Thermal** { | object<br><br>*read-only* | A reference to the thermal properties (fans, cooling, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures** | array<br><br>*read-write* | This is the definition for temperature sensors. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** | array<br><br>*read-only* | This structure is used to show redundancy for fans.  The Component ids will reference the members of the redundancy groups. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans** | array<br><br>*read-write* | This is the definition for fans. |
| } |   |   |

## Property Details

### ChassisType:

| string | Description |
| --- | --- |
| Rack | An equipment rack, typically a 19-inch wide freestanding unit |
| Blade | An enclosed or semi-enclosed, typically vertically-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Enclosure | A generic term for a chassis that does not fit any other description |
| StandAlone | A single, free-standing system, commonly called a tower or desktop chassis |
| RackMount | A single system chassis designed specifically for mounting in an equipment rack |
| Card | A loose device or circuit board intended to be installed in a system or other enclosure |
| Cartridge | A small self-contained system intended to be plugged into a multi-system chassis |
| Row | A collection of equipment racks |
| Pod | A collection of equipment racks in a large, likely transportable, container |
| Expansion | A chassis which expands the capabilities or capacity of another chassis |
| Sidecar | A chassis that mates mechanically with another chassis to expand its capabilities or capacity |
| Zone | A logical division or portion of a physical chassis that contains multiple devices or systems that cannot be physically separated |
| Sled | An enclosed or semi-enclosed, system chassis which must be plugged into a multi-system chassis to function normally similar to a blade type chassis. |
| Shelf | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Drawer | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which may be slid into a multi-system chassis. |
| Module | A small, typically removable, chassis or card which contains devices for a particular subsystem or function |
| Component | A small chassis, card, or device which contains devices for a particular subsystem or function |
| Other | A chassis that does not fit any of these definitions |

### ChassisType:

| string | Description |
| --- | --- |
| Rack | An equipment rack, typically a 19-inch wide freestanding unit |
| Blade | An enclosed or semi-enclosed, typically vertically-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Enclosure | A generic term for a chassis that does not fit any other description |
| StandAlone | A single, free-standing system, commonly called a tower or desktop chassis |
| RackMount | A single system chassis designed specifically for mounting in an equipment rack |
| Card | A loose device or circuit board intended to be installed in a system or other enclosure |
| Cartridge | A small self-contained system intended to be plugged into a multi-system chassis |
| Row | A collection of equipment racks |
| Pod | A collection of equipment racks in a large, likely transportable, container |
| Expansion | A chassis which expands the capabilities or capacity of another chassis |
| Sidecar | A chassis that mates mechanically with another chassis to expand its capabilities or capacity |
| Zone | A logical division or portion of a physical chassis that contains multiple devices or systems that cannot be physically separated |
| Sled | An enclosed or semi-enclosed, system chassis which must be plugged into a multi-system chassis to function normally similar to a blade type chassis. |
| Shelf | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which must be plugged into a multi-system chassis to function normally |
| Drawer | An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which may be slid into a multi-system chassis. |
| Module | A small, typically removable, chassis or card which contains devices for a particular subsystem or function |
| Component | A small chassis, card, or device which contains devices for a particular subsystem or function |
| Other | A chassis that does not fit any of these definitions |


# ChassisCollection




A Collection of Chassis resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# ComputerSystem 1.1.0




This schema defines a computer system and its respective properties.  A computer system represents a machine (physical or virtual) and the local resources such as memory, cpu and other devices that can be accessed from that machine.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#ComputerSystem.Reset** { | object<br><br>*read-write* | This action is used to reset the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The user definable tag that can be used to track this computer system for inventory or other client purposes |
| **Bios** *(v1.1.0)* { | object<br><br>*read-write* | Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AttributeRegistry** | string, null<br><br>*read-write* | The Resource ID of the Attribute Registry for the BIOS Attributes resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **BiosVersion** | string, null<br><br>*read-write* | The version of the system BIOS or primary system firmware. |
| **Description** | <br><br>*read-write* |  |
| **EthernetInterfaces** { | object<br><br>*read-write* | A Collection of EthernetInterface resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **HostName** | string, null<br><br>*read-write* | The DNS Host Name, without any domain information |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **IndicatorLED** | <br><br>*read-write* | The state of the indicator LED, used to identify the system |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** | array<br><br>*read-only* | An array of references to the Managers responsible for this system |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis** | array<br><br>*read-only* | An array of references to the chassis in which this system is contained |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** | array<br><br>*read-only* | An array of ID[s] of resources that power this computer system. Normally the ID will be a chassis or a specific set of powerSupplies |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** | array<br><br>*read-only* | An array of ID[s] of resources that cool this computer system. Normally the ID will be a chassis or a specific set of fans. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| } |   |   |
| **LogServices** { | object<br><br>*read-only* | A reference to the logs for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Manufacturer** | string, null<br><br>*read-only* | The manufacturer or OEM of this system. |
| **Memory** *(v1.1.0)* { | object<br><br>*read-write* | A Collection of Memory resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Model** | string, null<br><br>*read-only* | The model number for this system |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **PartNumber** | string, null<br><br>*read-only* | The part number for this system |
| **PowerState** | <br><br>*read-only* | This is the current power state of the system |
| **ProcessorSummary** { | object<br><br>*read-write* | This object describes the central processors of the system in general detail. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Count** | number, null<br><br>*read-only* | The number of processors in the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | The processor model for the primary or majority of processors in this system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **Processors** { | object<br><br>*read-write* | A Collection of Processor resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **SKU** | string, null<br><br>*read-only* | The manufacturer SKU for this system |
| **SecureBoot** *(v1.1.0)* { | object<br><br>*read-write* | This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootCurrentBoot** | <br><br>*read-only* | Secure Boot state during the current boot cycle. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootEnable** | boolean, null<br><br>*read-write* | Enable or disable UEFI Secure Boot (takes effect on next boot). |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootMode** | <br><br>*read-only* | Current Secure Boot Mode. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **SerialNumber** | string, null<br><br>*read-only* | The serial number for this system |
| **SimpleStorage** { | object<br><br>*read-write* | A Collection of SimpleStorage resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Storage** *(v1.1.0)* { | object<br><br>*read-write* | A Collection of Storage resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **SystemType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **TrustedModules** *(v1.1.0)* | array<br><br>*read-write* | This object describes the array of Trusted Modules in the system. |
| **UUID** | <br><br>*read-only* | The universal unique identifier (UUID) for this system |

## Property Details

### SystemType:

| string | Description |
| --- | --- |
| Physical | A computer system |
| Virtual | A virtual machine instance running on this system |
| OS | An operating system instance |
| PhysicallyPartitioned | A hardware-based partition of a computer system |
| VirtuallyPartitioned | A virtual or software-based partition of a computer system |


# ComputerSystemCollection




A Collection of ComputerSystem resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Drive 1.0.0




Drive contains properties describing a single physical disk drive for any system, along with links to associated Volumes.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Drive.SecureErase** { | object<br><br>*read-write* | This action is used to securely erase the contents of the drive. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **AssetTag** | string, null<br><br>*read-write* | The user assigned asset tag for this drive. |
| **BlockSizeBytes** | number, null<br><br>*read-only* | The size of the smallest addressible unit (Block) of this drive in bytes |
| **CapableSpeedGbs** | number, null<br><br>*read-only* | The speed which this drive can communicate to a storage controller in ideal conditions in Gigabits per second |
| **CapacityBytes** | number, null<br><br>*read-only* | The size in bytes of this Drive |
| **Description** | <br><br>*read-write* |  |
| **EncryptionAbility** | <br><br>*read-only* | The encryption abilities of this drive |
| **EncryptionStatus** | <br><br>*read-only* | The status of the encrytion of this drive |
| **FailurePredicted** | boolean, null<br><br>*read-only* | Is this drive currently predicting a failure in the near future |
| **HotspareType** | <br><br>*read-only* | The type of hotspare this drive is currently serving as |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Identifiers** | array<br><br>*read-only* | The Durable names for the drive |
| **IndicatorLED** | <br><br>*read-write* | The state of the indicator LED, used to identify the drive. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes** | array<br><br>*read-only* | An array of references to the volumes contained in this drive. This will reference Volumes that are either wholly or only partly contained by this drive. |
| } |   |   |
| **Location** | array<br><br>*read-only* | The Location of the drive |
| **Manufacturer** | string, null<br><br>*read-only* | This is the manufacturer of this drive. |
| **MediaType** | <br><br>*read-only* | The type of media contained in this drive |
| **Model** | string, null<br><br>*read-only* | This is the model number for the drive. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **NegotiatedSpeedGbs** | number, null<br><br>*read-only* | The speed which this drive is currently communicating to the storage controller in Gigabits per second |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **PartNumber** | string, null<br><br>*read-only* | The part number for this drive. |
| **PredictedMediaLifeLeftPercent** | number, null<br><br>*read-only* | The percentage of reads and writes that are predicted to still be available for the media |
| **Protocol** | <br><br>*read-only* | The protocol this drive is using to communicate to the storage controller |
| **Revision** | string, null<br><br>*read-only* | The revision of this Drive |
| **RotationSpeedRPM** | number, null<br><br>*read-only* | The rotation speed of this Drive in Revolutions per Minute (RPM) |
| **SKU** | string, null<br><br>*read-only* | This is the SKU for this drive. |
| **SerialNumber** | string, null<br><br>*read-only* | The serial number for this drive. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **StatusIndicator** | <br><br>*read-write* | The state of the status indicator, used to communicate status information about this drive. |

# EthernetInterface 1.0.2




This schema defines a simple ethernet NIC resource.

|     |     |     |
| --- | --- | --- |
| **AutoNeg** | boolean, null<br><br>*read-write* | This indicates if the speed and duplex are automatically negotiated and configured on this interface. |
| **Description** | <br><br>*read-write* |  |
| **FQDN** | string, null<br><br>*read-write* | This is the complete, fully qualified domain name obtained by DNS for this interface. |
| **FullDuplex** | boolean, null<br><br>*read-write* | This indicates if the interface is in Full Duplex mode or not. |
| **HostName** | string, null<br><br>*read-write* | The DNS Host Name, without any domain information |
| **IPv4Addresses** | array<br><br>*read-only* | The IPv4 addresses assigned to this interface |
| **IPv6AddressPolicyTable** | array<br><br>*read-write* | An array representing the RFC 6724 Address Selection Policy Table. |
| **IPv6Addresses** | array<br><br>*read-only* | This array of objects enumerates all of the currently assigned IPv6 addresses on this interface. |
| **IPv6DefaultGateway** | string, null<br><br>*read-only* | This is the IPv6 default gateway address that is currently in use on this interface. |
| **IPv6StaticAddresses** | array<br><br>*read-only* | This array of objects represents all of the IPv6 static addresses to be assigned on this interface. |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **InterfaceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this interface is enabled. |
| **MACAddress** | <br><br>*read-write* | This is the currently configured MAC address of the (logical port) interface. |
| **MTUSize** | number, null<br><br>*read-write* | This is the currently configured Maximum Transmission Unit (MTU) in bytes on this interface. |
| **MaxIPv6StaticAddresses** | number, null<br><br>*read-only* | This indicates the maximum number of Static IPv6 addresses that can be configured on this interface. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **NameServers** | array<br><br>*read-only* | This represents DNS name servers that are currently in use on this interface. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **PermanentMACAddress** | <br><br>*read-only* | This is the permanent MAC address assigned to this interface (port) |
| **SpeedMbps** | number, null<br><br>*read-write* | This is the current speed in Mbps of this interface. |
| **Status** | <br><br>*read-write* |  |
| **UefiDevicePath** | string, null<br><br>*read-only* | The UEFI device path for this interface |
| **VLAN** | <br><br>*read-write* | If this Network Interface supports more than one VLAN, this property will not be present and the client should look for VLANs collection in the link section of this resource. |
| **VLANs** { | object<br><br>*read-write* | A Collection of VLanNetworkInterface resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |

# EthernetInterfaceCollection




A Collection of EthernetInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Event 1.1.0




The Event schema describes the JSON payload received by an Event Destination (which has subscribed to event notification) when events occurs.  This resource contains data about event(s), including descriptions, severity and MessageId reference to a Message Registry that can be accessed for further information. 

|     |     |     |
| --- | --- | --- |
| **Context** *(v1.1.0)* | string<br><br>*read-only* | A context can be supplied at subscription time.  This property is the context value supplied by the subscriber. |
| **Description** | <br><br>*read-write* |  |
| **Events** | array<br><br>*read-write* | Each event in this array has a set of properties that describe the event.  Since this is an array, more than one event can be sent simultaneously. |
| **Events@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# EventDestination 1.0.2




An Event Destination desribes the target of an event subscription, including the types of events subscribed and context to provide to the target in the Event payload.

|     |     |     |
| --- | --- | --- |
| **Context** | string<br><br>*read-write* | A client-supplied string that is stored with the event destination subscription. |
| **Description** | <br><br>*read-write* |  |
| **Destination** | string<br><br>*read-only* | The URI of the destination Event Service. |
| **EventTypes** | array<br><br>*read-only* | This property shall contain the types of events that shall be sent to the desination. |
| **HttpHeaders** | array<br><br>*read-write* | This is for setting HTTP headers, such as authorization information.  This object will be null on a GET. |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Protocol** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |

## Property Details

### Protocol:

| string |
| --- |
| Redfish | 


# EventDestinationCollection




A Collection of EventDestination resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# EventService 1.0.2




The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#EventService.SubmitTestEvent** { | object<br><br>*read-write* | This action is used to generate a test event. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **DeliveryRetryAttempts** | number<br><br>*read-only* | This is the number of attempts an event posting is retried before the subscription is terminated. |
| **DeliveryRetryIntervalSeconds** | number<br><br>*read-only* | This represents the number of seconds between retry attempts for sending any given Event |
| **Description** | <br><br>*read-write* |  |
| **EventTypesForSubscription** | array<br><br>*read-only* | This is the types of Events that can be subscribed to. |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Subscriptions** { | object<br><br>*read-write* | A Collection of EventDestination resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |

# JsonSchemaFile 1.0.2




This is the schema definition for the Schema File locator resource.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Languages** | array<br><br>*read-only* | Language codes for the schemas available. |
| **Location** | array<br><br>*read-only* | Location information for this schema file. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Schema** | string<br><br>*read-only* | The @odata.type name this schema describes. |

# JsonSchemaFileCollection




A Collection of JsonSchemaFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# LogEntry 1.0.2




This resource defines the record format for a log.  It is designed to be used for SEL logs (from IPMI) as well as Event Logs and OEM-specific log formats.  The EntryType field indicates the type of log and the resource includes several additional properties dependent on the EntryType.

|     |     |     |
| --- | --- | --- |
| **Created** | string<br><br>*read-only* | The time the log entry was created. |
| **Description** | <br><br>*read-write* |  |
| **EntryCode** | <br><br>*read-only* | If the EntryType is SEL, this will have the entry code for the log entry. |
| **EntryType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| } |   |   |
| **Message** | string, null<br><br>*read-only* | This property decodes from EntryType:  If it is Event then it is a message string.  Otherwise, it is SEL or Oem specific.  In most cases, this will be the actual Log Entry. |
| **MessageArgs** | array<br><br>*read-only* | The values of this property shall be any arguments for the message. |
| **MessageId** | string<br><br>*read-only* | This property decodes from EntryType:  If it is Event then it is a message id.  Otherwise, it is SEL or Oem specific.  This value is only used for registries - for more information, see the specification. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **OemRecordFormat** | string, null<br><br>*read-only* | If the entry type is Oem, this will contain more information about the record format from the Oem. |
| **SensorNumber** | number, null<br><br>*read-only* | This property decodes from EntryType:  If it is SEL, it is the sensor number; if Event then the count of events.  Otherwise, it is Oem specific. |
| **SensorType** | <br><br>*read-only* | If the EntryType is SEL, this will have the sensor type that the log entry pertains to. |
| **Severity** | <br><br>*read-only* | This is the severity of the log entry. |

## Property Details

### EntryType:

| string |
| --- |
| Event | 
| SEL | 
| Oem | 


# LogEntryCollection




A Collection of LogEntry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |

# LogService 1.0.2




This resource represents the log service for the resource or service to which it is associated.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#LogService.ClearLog** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **DateTime** | string, null<br><br>*read-write* | The current DateTime (with offset) for the log service, used to set or read time. |
| **DateTimeLocalOffset** | string, null<br><br>*read-write* | The time offset from UTC that the DateTime property is set to in format: +06:00 . |
| **Description** | <br><br>*read-write* |  |
| **Entries** { | object<br><br>*read-write* | A Collection of LogEntry resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **MaxNumberOfRecords** | number<br><br>*read-only* | The maximum number of log entries this service can have. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **OverWritePolicy** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| **Status** | <br><br>*read-write* |  |

## Property Details

### OverWritePolicy:

| string | Description |
| --- | --- |
| Unknown | The overwrite policy is not known or is undefined |
| WrapsWhenFull | When full, new entries to the Log will overwrite previous entries |
| NeverOverWrites | When full, new entries to the Log will be discarded |


# LogServiceCollection




A Collection of LogService resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Manager 1.1.0




This is the schema definition for a Manager.  Examples of managers are BMCs, Enclosure Managers, Management Controllers and other subsystems assigned managability functions.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ForceFailover** { | object<br><br>*read-write* | The ForceFailover action forces a failover of this manager to the manager used in the parameter |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ModifyRedundancySet** { | object<br><br>*read-write* | The ModifyRedundancySet operation is used to add or remove members to a redundant group of manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.Reset** { | object<br><br>*read-write* | The reset action resets/reboots the manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **CommandShell** { | object<br><br>*read-write* | Used for describing services like Serial Console, Command Shell or Graphical Console |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | Indicates if the service is enabled for this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** | array<br><br>*read-only* | This object is used to enumerate the Command Shell connection types allowed by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support. |
| } |   |   |
| **DateTime** | string, null<br><br>*read-write* | The current DateTime (with offset) for the manager, used to set or read time. |
| **DateTimeLocalOffset** | string, null<br><br>*read-write* | The time offset from UTC that the DateTime property is set to in format: +06:00 . |
| **Description** | <br><br>*read-write* |  |
| **EthernetInterfaces** { | object<br><br>*read-write* | A Collection of EthernetInterface resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **FirmwareVersion** | string, null<br><br>*read-only* | The firmware version of this Manager |
| **GraphicalConsole** { | object<br><br>*read-write* | Used for describing services like Serial Console, Command Shell or Graphical Console |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | Indicates if the service is enabled for this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** | array<br><br>*read-only* | This object is used to enumerate the Graphical Console connection types allowed by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support. |
| } |   |   |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers** | array<br><br>*read-only* | This property is an array of references to the systems that this manager has control over. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis** | array<br><br>*read-only* | This property is an array of references to the chassis that this manager has control over. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerInChassis** { | object<br><br>*read-only* | This property is a reference to the chassis that this manager is located in. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IndicatorLED** | <br><br>*read-write* | The state of the indicator LED, used to identify the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** {} | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LogServices** {} | object<br><br>*read-only* | A reference to the logs for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Thermal** {} | object<br><br>*read-only* | A reference to the thermal properties (fans, cooling, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Manufacturer** | string, null<br><br>*read-only* | This is the manufacturer of this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Location** {} | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PartNumber** | string, null<br><br>*read-only* | The part number for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerState** | <br><br>*read-only* | This is the current power state of the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** | string, null<br><br>*read-only* | This is the model number for the chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssetTag** | string, null<br><br>*read-write* | The user assigned asset tag for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SKU** | string, null<br><br>*read-only* | This is the SKU for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SerialNumber** | string, null<br><br>*read-only* | The serial number for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Links** {} | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Power** {} | object<br><br>*read-only* | A reference to the power properties (power supplies, power policies, sensors) for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **LogServices** { | object<br><br>*read-only* | A reference to the logs for this chassis. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **ManagerType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **Model** | string, null<br><br>*read-only* | The model information of this Manager as defined by the manufacturer |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **NetworkProtocol** { | object<br><br>*read-write* | This resource is used to obtain or modify the network services managed by a given manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HostName** | string, null<br><br>*read-only* | The DNS Host Name of this manager, without any domain information |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FQDN** | string, null<br><br>*read-only* | This is the fully qualified domain name for the manager obtained by DNS including the host name and top-level domain name. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Redundancy** | array<br><br>*read-only* | Redundancy information for the managers of this system |
| **Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| **SerialConsole** { | object<br><br>*read-write* | Used for describing services like Serial Console, Command Shell or Graphical Console |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean<br><br>*read-write* | Indicates if the service is enabled for this manager. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** | array<br><br>*read-only* | This object is used to enumerate the Serial Console connection types allowed by the implementation. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** | number<br><br>*read-only* | Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support. |
| } |   |   |
| **SerialInterfaces** { | object<br><br>*read-write* | A Collection of SerialInterface resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **ServiceEntryPointUUID** | string<br><br>*read-write* |  |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **UUID** | <br><br>*read-only* | The Universal Unique Identifier (UUID) for this Manager |
| **VirtualMedia** { | object<br><br>*read-write* | A Collection of VirtualMedia resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |

## Property Details

### ManagerType:

| string | Description |
| --- | --- |
| ManagementController | A controller used primarily to monitor or manage the operation of a device or system |
| EnclosureManager | A controller which provides management functions for a chassis or group of devices or systems |
| BMC | A controller which provides management functions for a single computer system |
| RackManager | A controller which provides management functions for a whole or part of a rack |
| AuxiliaryController | A controller which provides management functions for a particular subsystem or group of devices |


# ManagerAccount 1.0.2




The user accounts, owned by a Manager, are defined in this resource.  Changes to a Manager Account may affect the current Redfish service connection if this manager is responsible for the Redfish service.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Enabled** | boolean<br><br>*read-write* | This property is used by a User Administrator to disable an account w/o having to delet the user information.  When set to true, the user can login.  When set to false, the account is administratively disabled and the user cannot login. |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Role** { | object<br><br>*read-only* | A reference to the Role object defining Privileges for this account--returned when the resource is read. The ID of the role is the same as property RoleId. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IsPredefined** | boolean<br><br>*read-only* | This property is used to indicate if the Role is one of the Redfish Predefined Roles vs a Custom role. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AssignedPrivileges** | array<br><br>*read-write* | The redfish privileges that this role includes. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OemPrivileges** | array<br><br>*read-write* | The OEM privileges that this role includes. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| } |   |   |
| **Locked** | boolean<br><br>*read-write* | This property indicates that the account has been auto-locked by the account service because the lockout threshold has been exceeded.  When set to true, the account is locked. A user admin can write the property to false to manually unlock, or the account service will unlock it once the lockout duration period has passed. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **Password** | string, null<br><br>*read-write* | This property is used with a PATCH or PUT to write the password for the account.  This property is null on a GET. |
| **RoleId** | string<br><br>*read-write* | This property contains the Role for this account. |
| **UserName** | string<br><br>*read-write* | This property contains the user name for the account. |

# ManagerAccountCollection




A Collection of ManagerAccount resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |

# ManagerCollection




A Collection of Manager resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |

# ManagerNetworkProtocol 1.0.2




This resource is used to obtain or modify the network services managed by a given manager.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **FQDN** | string, null<br><br>*read-only* | This is the fully qualified domain name for the manager obtained by DNS including the host name and top-level domain name. |
| **HTTP** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **HTTPS** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **HostName** | string, null<br><br>*read-only* | The DNS Host Name of this manager, without any domain information |
| **IPMI** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **KVMIP** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **SNMP** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **SSDP** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyIPv6Scope** | <br><br>*read-write* | Indicates the scope for the IPv6 Notify messages for SSDP. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyTTL** | number, null<br><br>*read-write* | Indicates the time to live hop count for SSDPs Notify messages. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyMulticastIntervalSeconds** | number, null<br><br>*read-write* | Indicates how often the Multicast is done from this service for SSDP. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **SSH** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Telnet** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |
| **VirtualMedia** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** | boolean, null<br><br>*read-write* | Indicates if the protocol is enabled or disabled |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** | number, null<br><br>*read-write* | Indicates the protocol port. |
| } |   |   |

# Memory 1.0.0




This is the schema definition for definition of a Memory and its configuration

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.DisablePassphrase** { | object<br><br>*read-write* | Disable passphrase for given regions |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.UnlockUnit** { | object<br><br>*read-write* | This defines the action for unlocking given regions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SetPassphrase** { | object<br><br>*read-write* | Set passphrase for the given regions |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SecureEraseUnit** { | object<br><br>*read-write* | This defines the action for securely erasing given regions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **AllowedSpeedsMHz** | array<br><br>*read-only* | Speed bins supported by this Memory |
| **BaseModuleType** | <br><br>*read-only* | The base module type of Memory |
| **BusWidthBits** | number, null<br><br>*read-only* | Bus Width in bits. |
| **CapacityMiB** | number, null<br><br>*read-only* | Memory Capacity in MiB. |
| **DataWidthBits** | number, null<br><br>*read-only* | Data Width in bits. |
| **Description** | <br><br>*read-write* |  |
| **DeviceID** | string, null<br><br>*read-only* | Device ID |
| **DeviceLocator** | string, null<br><br>*read-only* | Location of the Memory in the platform |
| **ErrorCorrection** | <br><br>*read-only* | Error correction scheme supported for this memory |
| **FirmwareApiVersion** | string, null<br><br>*read-only* | Version of API supported by the firmware |
| **FirmwareRevision** | string, null<br><br>*read-only* | Revision of firmware on the Memory controller |
| **FunctionClasses** | array<br><br>*read-only* | Function Classes by the Memory |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **IsRankSpareEnabled** | boolean, null<br><br>*read-only* | Rank spare enabled status |
| **IsSpareDeviceEnabled** | boolean, null<br><br>*read-only* | Spare device enabled status |
| **Manufacturer** | string, null<br><br>*read-only* | The Memory manufacturer |
| **MaxTDPMilliWatts** | array<br><br>*read-only* | Maximum TDPs in milli Watts |
| **MemoryDeviceType** | <br><br>*read-only* | Type details of the Memory |
| **MemoryLocation** { | object<br><br>*read-write* | . |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryController** | number, null<br><br>*read-only* | Memory controller number in which Memory is connected |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Slot** | number, null<br><br>*read-only* | Slot number in which Memory is connected |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Socket** | number, null<br><br>*read-only* | Socket number in which Memory is connected |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Channel** | number, null<br><br>*read-only* | Channel number in which Memory is connected |
| } |   |   |
| **MemoryMedia** | array<br><br>*read-only* | Media  of this Memory |
| **MemoryType** | <br><br>*read-only* | The type of Memory |
| **Metrics** { | object<br><br>*read-write* | MemoryMetrics contains usage and health statistics for a single Memory module or device instance. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlockSizeBytes** | number, null<br><br>*read-only* | Block size in bytes |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **OperatingMemoryModes** | array<br><br>*read-only* | Memory modes supported by the Memory |
| **OperatingSpeedMhz** | number, null<br><br>*read-only* | Operating speed of Memory in MHz |
| **PartNumber** | string, null<br><br>*read-only* | The product part number of this device |
| **PersistentRegionSizeLimitMiB** | number, null<br><br>*read-only* | Total size of persistent regions in MiB |
| **PowerManagementPolicy** { | object<br><br>*read-write* | . |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AveragePowerBudgetMilliWatts** | number, null<br><br>*read-only* | Average power budget in milli watts |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PeakPowerBudgetMilliWatts** | number, null<br><br>*read-only* | Peak power budget in milli watts |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PolicyEnabled** | boolean, null<br><br>*read-only* | Power management policy enabled status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxTDPMilliWatts** | number, null<br><br>*read-only* | Maximum TDP in milli watts |
| } |   |   |
| **RankCount** | number, null<br><br>*read-only* | Number of ranks available in the Memory |
| **Regions** | array<br><br>*read-only* | Memory regions information within the Memory |
| **SecurityCapabilities** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PassphraseCapable** | boolean, null<br><br>*read-only* | Memory passphrase set capability |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecurityStates** | array<br><br>*read-only* | Security states supported by the Memory |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPassphraseCount** | number, null<br><br>*read-only* | Maximum number of passphrases supported for this Memory |
| } |   |   |
| **SerialNumber** | string, null<br><br>*read-only* | The product serial number of this device |
| **SpareDeviceCount** | number, null<br><br>*read-only* | Number of unused spare devices available in the Memory |
| **SubsystemDeviceID** | string, null<br><br>*read-only* | Subsystem Device ID |
| **SubsystemVendorID** | string, null<br><br>*read-only* | SubSystem Vendor ID |
| **VendorID** | string, null<br><br>*read-only* | Vendor ID |
| **VolatileRegionSizeLimitMiB** | number, null<br><br>*read-only* | Total size of volatile regions in MiB |

# MemoryCollection




A Collection of Memory resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# MemoryMetrics 1.0.0




MemoryMetrics contains usage and health statistics for a single Memory module or device instance.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#MemoryMetrics.ClearCurrentPeriod** { | object<br><br>*read-write* | This sets the CurrentPeriod object values to zero. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **BlockSizeBytes** | number, null<br><br>*read-only* | Block size in bytes |
| **CurrentPeriod** { | object<br><br>*read-write* | This object contains the Memory metrics since last reset or ClearCurrentPeriod action. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** | number, null<br><br>*read-only* | Number of blocks read since reset |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** | string, null<br><br>*read-only* | Number of blocks written since reset |
| } |   |   |
| **Description** | <br><br>*read-write* |  |
| **HealthData** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PerformanceDegraded** | boolean, null<br><br>*read-only* | Performance degraded mode status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RemainingSpareBlockPercentage** | number, null<br><br>*read-only* | Remaining spare blocks in percentage |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AlarmTrips** { | object<br><br>*read-only* | Alarm trip information about the memory |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperature** | boolean, null<br><br>*read-only* | Temperature threshold crossing alarm trip detected status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SpareBlock** | boolean, null<br><br>*read-only* | Spare block capacity crossing alarm trip detected status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**UncorrectableECCError** | boolean, null<br><br>*read-only* | Uncorrectable data error threshold crossing alarm trip detected status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CorrectableECCError** | boolean, null<br><br>*read-only* | Correctable data error threshold crossing alarm trip detected status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AddressParityError** | boolean, null<br><br>*read-only* | Address parity error detected status |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LastShutdownSuccess** | boolean, null<br><br>*read-only* | Status of last shutdown |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DataLossDetected** | boolean, null<br><br>*read-only* | Data loss detection status |
| } |   |   |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **LifeTime** { | object<br><br>*read-write* | This objects contains the Memory metrics for the lifetime of the Memory. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** | number, null<br><br>*read-only* | Number of blocks read for the lifetime of the Memory |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** | string, null<br><br>*read-only* | Number of blocks written for the lifetime of the Memory |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# MessageRegistry 1.0.2




This is the schema definition for all Message Registries.  It represents the properties for the registries themselves.  The MessageId is formed per the Redfish specification.  It consists of the RegistryPrefix concatenated with the version concatenated with the unique identifier for the message registry entry.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Language** | string<br><br>*read-only* | This is the RFC 5646 compliant language code for the registry. |
| **Messages** {} | object<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **OwningEntity** | string<br><br>*read-only* | This is the organization or company that publishes this registry. |
| **RegistryPrefix** | string<br><br>*read-only* | This is the single word prefix used to form a messageID structure. |
| **RegistryVersion** | string<br><br>*read-only* | This is the message registry version which is used in the middle portion of a messageID. |

# MessageRegistryCollection




A Collection of MessageRegistry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# MessageRegistryFile 1.0.2




This is the schema definition for the Schema File locator resource.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Languages** | array<br><br>*read-only* | Language codes for the schemas available. |
| **Location** | array<br><br>*read-only* | Location information for this schema file. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Registry** | string<br><br>*read-only* | The Registry Name, Major and Minor version used in MessageID construction. |

# MessageRegistryFileCollection




A Collection of MessageRegistryFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Power 1.1.0




This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **PowerControl** | array<br><br>*read-write* | This is the definition for power control function (power reading/limiting). |
| **PowerControl@odata.navigationLink** | string<br><br>*read-write* |  |
| **PowerSupplies** | array<br><br>*read-write* | Details of the power supplies associated with this system or device |
| **PowerSupplies@odata.navigationLink** | string<br><br>*read-write* |  |
| **Redundancy** | array<br><br>*read-only* | Redundancy information for the power subsystem of this system or device |
| **Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| **Voltages** | array<br><br>*read-write* | This is the definition for voltage sensors. |
| **Voltages@odata.navigationLink** | string<br><br>*read-write* |  |

# Processor 1.0.2




This is the schema definition for the Processor resource.  It represents the properties of a processor attached to a System.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **InstructionSet** | <br><br>*read-only* | The instruction set of the processor |
| **Manufacturer** | string, null<br><br>*read-only* | The processor manufacturer |
| **MaxSpeedMHz** | number, null<br><br>*read-only* | The maximum clock speed of the processor |
| **Model** | string, null<br><br>*read-only* | The product model number of this device |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **ProcessorArchitecture** | <br><br>*read-only* | The architecture of the processor |
| **ProcessorId** { | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveFamily** | string, null<br><br>*read-only* | The effective Family for this processor |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveModel** | string, null<br><br>*read-only* | The effective Model for this processor |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Step** | string, null<br><br>*read-only* | The Step value for this processor |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IdentificationRegisters** | string, null<br><br>*read-only* | The contents of the Identification Registers (CPUID) for this processor |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MicrocodeInfo** | string, null<br><br>*read-only* | The Microcode Information for this processor |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VendorId** | string, null<br><br>*read-only* | The Vendor Identification for this processor |
| } |   |   |
| **ProcessorType** | <br><br>*read-only* | The type of processor |
| **Socket** | string, null<br><br>*read-only* | The socket or location of the processor |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **TotalCores** | number, null<br><br>*read-only* | The total number of cores contained in this processor |
| **TotalThreads** | number, null<br><br>*read-only* | The total number of execution threads supported by this processor |

# ProcessorCollection




A Collection of Processor resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Role 1.0.2




This resource defines a user role to be used in conjunction with a Manager Account.

|     |     |     |
| --- | --- | --- |
| **AssignedPrivileges** | array<br><br>*read-write* | The redfish privileges that this role includes. |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **IsPredefined** | boolean<br><br>*read-only* | This property is used to indicate if the Role is one of the Redfish Predefined Roles vs a Custom role. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **OemPrivileges** | array<br><br>*read-write* | The OEM privileges that this role includes. |

# RoleCollection




A Collection of Role resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# SecureBoot 1.0.0




This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#SecureBoot.ResetKeys** { | object<br><br>*read-write* | This action is used to reset the Secure Boot keys. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **SecureBootCurrentBoot** | <br><br>*read-only* | Secure Boot state during the current boot cycle. |
| **SecureBootEnable** | boolean, null<br><br>*read-write* | Enable or disable UEFI Secure Boot (takes effect on next boot). |
| **SecureBootMode** | <br><br>*read-only* | Current Secure Boot Mode. |

# SerialInterface 1.0.2




This schema defines an asynchronous serial interface resource.

|     |     |     |
| --- | --- | --- |
| **BitRate** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **ConnectorType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **DataBits** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **Description** | <br><br>*read-write* |  |
| **FlowControl** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **InterfaceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this interface is enabled. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Parity** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **PinOut** | <br><br>*read-only* | The physical pin configuration needed for a serial connector. |
| **SignalType** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **StopBits** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |

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
| None | No flow control imposed |
| Software | XON/XOFF in-band flow control imposed |
| Hardware | Out of band flow control imposed |

### Parity:

| string |
| --- |
| None | 
| Even | 
| Odd | 
| Mark | 
| Space | 

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
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# ServiceRoot 1.0.2




This object represents the root Redfish service.

|     |     |     |
| --- | --- | --- |
| **AccountService** { | object<br><br>*read-write* | Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinPasswordLength** | number<br><br>*read-only* | This is the minimum password length for this service. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Accounts** { | object<br><br>*read-only* | Link to a collection of Manager Accounts |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPasswordLength** | number<br><br>*read-only* | This is the maximum password length for this service. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutCounterResetAfter** | number<br><br>*read-write* | The interval of time in seconds since the last failed login attempt at which point the lockout threshold counter for the account is reset to zero. Must be less than or equal to AccountLockoutDuration |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AuthFailureLoggingThreshold** | number<br><br>*read-write* | This is the number of authorization failures that need to occur before the failure attempt is logged to the manager log. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Roles** { | object<br><br>*read-only* | Link to a collection of Roles |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutThreshold** | number, null<br><br>*read-write* | The number of failed login attempts before a user account is locked for a specified duration. (0=never locked) |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutDuration** | number, null<br><br>*read-write* | The time in seconds an account is locked after the account lockout threshold is met. Must be >= AccountLockoutResetAfter. If set to 0, no lockout will occur. |
| } |   |   |
| **Chassis** { | object<br><br>*read-write* | A Collection of Chassis resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Description** | <br><br>*read-write* |  |
| **EventService** { | object<br><br>*read-write* | The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations). |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventTypesForSubscription** | array<br><br>*read-only* | This is the types of Events that can be subscribed to. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Subscriptions** { | object<br><br>*read-only* | This is a reference to a collection of Event Destination resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryIntervalSeconds** | number<br><br>*read-only* | This represents the number of seconds between retry attempts for sending any given Event |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryAttempts** | number<br><br>*read-only* | This is the number of attempts an event posting is retried before the subscription is terminated. |
| } |   |   |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **JsonSchemas** { | object<br><br>*read-write* | A Collection of JsonSchemaFile resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** { | object<br><br>*read-only* | Link to a collection of Sessions |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| } |   |   |
| **Managers** { | object<br><br>*read-write* | A Collection of Manager resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **RedfishVersion** | string<br><br>*read-only* | The version of the Redfish service |
| **Registries** { | object<br><br>*read-write* | A Collection of MessageRegistryFile resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **SessionService** { | object<br><br>*read-write* | This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** { | object<br><br>*read-only* | Link to a collection of Sessions |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SessionTimeout** | number<br><br>*read-write* | This is the number of seconds of inactivity that a session may have before the session service closes the session due to inactivity. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Systems** { | object<br><br>*read-write* | A Collection of ComputerSystem resource instances. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Tasks** { | object<br><br>*read-write* | This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Tasks** { | object<br><br>*read-only* | References to the Tasks collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LifeCycleEventOnTaskStateChange** | boolean<br><br>*read-only* | Send an Event upon Task State Change. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTime** | string, null<br><br>*read-only* | The current DateTime (with offset) setting that the task service is using. |
| } |   |   |
| **UUID** | <br><br>*read-only* | Unique identifier for a service instance. When SSDP is used, this value should be an exact match of the UUID value returned in a 200OK from an SSDP M-SEARCH request during discovery.  |

# Session 1.0.2




The Session resource describes a single connection (session) between a client and a Redfish service instance.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Password** | string, null<br><br>*read-write* | This property is used in a POST to specify a password when creating a new session.  This property is null on a GET. |
| **UserName** | string, null<br><br>*read-only* | The UserName for the account for this session. |

# SessionCollection




A Collection of Session resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# SessionService 1.0.2




This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| **SessionTimeout** | number<br><br>*read-write* | This is the number of seconds of inactivity that a session may have before the session service closes the session due to inactivity. |
| **Sessions** { | object<br><br>*read-only* | Link to a collection of Sessions |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |

# SimpleStorage 1.1.0




This is the schema definition for the Simple Storage resource.  It represents the properties of a storage controller and its directly-attached devices.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Devices** *(deprecated v1.0.2)* | array<br><br>*read-only* | The storage devices associated with this resource |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **UefiDevicePath** | string, null<br><br>*read-only* | The UEFI device path used to access this storage controller. |

# SimpleStorageCollection




A Collection of SimpleStorage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Storage 1.0.0




This schema defines a storage subsystem and its respective properties.  A storage subsystem represents a set of storage controllers (physical or virtual) and the resources such as volumes that can be accessed from that subsystem.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Storage.SetEncryptionKey** { | object<br><br>*read-write* | This action is used to set the encryption key for the storage subsystem. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **Description** | <br><br>*read-write* |  |
| **Drives** | array<br><br>*read-only* | The set of drives attached to the storage controllers represented by this resource. |
| **Drives@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures** | array<br><br>*read-only* | An array of references to the chassis to which this storage subsystem is attached |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **Redundancy** | array<br><br>*read-only* | Redundancy information for the storage subsystem |
| **Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **StorageControllers** | array<br><br>*read-only* | The set of storage controllers represented by this resource. |
| **StorageControllers@odata.navigationLink** | string<br><br>*read-write* |  |
| **Volumes** | array<br><br>*read-only* | The set of volumes produced by the storage controllers represented by this resource. |
| **Volumes@odata.navigationLink** | string<br><br>*read-write* |  |

# StorageCollection




A Collection of Storage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |

# Task 1.0.2




This resource contains information about a specific Task scheduled by or being executed by a Redfish service's Task Service.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **EndTime** | string<br><br>*read-only* | The date-time stamp that the task was last completed. |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Messages** | array<br><br>*read-only* | This is an array of messages associated with the task. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **StartTime** | string<br><br>*read-only* | The date-time stamp that the task was last started. |
| **TaskState** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **TaskStatus** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |

## Property Details

### TaskState:

| string | Description |
| --- | --- |
| New | A new task |
| Starting | Task is starting |
| Running | Task is running normally |
| Suspended | Task has been suspended |
| Interrupted | Task has been interrupted |
| Pending | Task is pending and has not started |
| Stopping | Task is in the process of stopping |
| Completed | Task has completed |
| Killed | Task was terminated |
| Exception | Task has stopped due to an exception condition |
| Service | Task is running as a service |

### TaskStatus:

| string | Description |
| --- | --- |
| OK | Normal |
| Warning | A condition exists that requires attention |
| Critical | A critical condition exists that requires immediate attention |


# TaskCollection




A Collection of Task resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |

# TaskService 1.0.2




This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.

|     |     |     |
| --- | --- | --- |
| **CompletedTaskOverWritePolicy** | string<br><br>*read-write* |  *See Property Details, below, for more information about this property.* |
| **DateTime** | string, null<br><br>*read-only* | The current DateTime (with offset) setting that the task service is using. |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **LifeCycleEventOnTaskStateChange** | boolean<br><br>*read-only* | Send an Event upon Task State Change. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **ServiceEnabled** | boolean, null<br><br>*read-write* | This indicates whether this service is enabled. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Tasks** { | object<br><br>*read-only* | References to the Tasks collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** | <br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** | array<br><br>*read-only* | Contains the members of this collection. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** | string<br><br>*read-write* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** | string<br><br>*read-only* | The name of the resource or array element. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| } |   |   |

## Property Details

### CompletedTaskOverWritePolicy:

| string | Description |
| --- | --- |
| Manual | Completed tasks are not automatically overwritten |
| Oldest | Oldest completed tasks are overwritten |


# Thermal 1.1.0




This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Fans** | array<br><br>*read-write* | This is the definition for fans. |
| **Fans@odata.navigationLink** | string<br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **Redundancy** | array<br><br>*read-only* | This structure is used to show redundancy for fans.  The Component ids will reference the members of the redundancy groups. |
| **Redundancy@odata.navigationLink** | string<br><br>*read-write* |  |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **Temperatures** | array<br><br>*read-write* | This is the definition for temperature sensors. |
| **Temperatures@odata.navigationLink** | string<br><br>*read-write* |  |

# VLanNetworkInterface 1.0.2




This resource contains information for a Virtual LAN (VLAN) network instance available on a manager, system or other device.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **VLANEnable** | boolean, null<br><br>*read-write* | This indicates if this VLAN is enabled. |
| **VLANId** | <br><br>*read-write* | This indicates the VLAN identifier for this VLAN. |

# VLanNetworkInterfaceCollection




A Collection of VLanNetworkInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# VirtualMedia 1.0.2




This resource allows monitoring and control of an instance of virtual media (e.g. a remote CD, DVD, or USB device) functionality provided by a Manager for a system or device.

|     |     |     |
| --- | --- | --- |
| **ConnectedVia** | <br><br>*read-only* | Current virtual media connection methods |
| **Description** | <br><br>*read-write* |  |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Image** | string, null<br><br>*read-only* | A URI providing the location of the selected image |
| **ImageName** | string, null<br><br>*read-only* | The current image name |
| **Inserted** | boolean, null<br><br>*read-only* | Indicates if virtual media is inserted in the virtual device. |
| **MediaTypes** | array<br><br>*read-only* | This is the media types supported as virtual media. |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |
| **WriteProtected** | boolean, null<br><br>*read-only* | Indicates the media is write protected. |

# VirtualMediaCollection




A Collection of VirtualMedia resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** | <br><br>*read-write* |  |
| **Members** | array<br><br>*read-only* | Contains the members of this collection. |
| **Members@odata.navigationLink** | string<br><br>*read-write* |  |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections. |

# Volume 1.0.0




Volume contains properties used to describe a volume, virtual disk, LUN, or other logical storage entity for any system.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object<br><br>*read-only* | The available actions for this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Volume.Initialize** { | object<br><br>*read-write* | This action is used to prepare the contents of the volume for use by the system. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**title** | string<br><br>*read-write* | Friendly action name |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**target** | string<br><br>*read-write* | Link to invoke action |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} |   |   |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* |  |
| } |   |   |
| **BlockSizeBytes** | number, null<br><br>*read-only* | The size of the smallest addressible unit (Block) of this volume in bytes |
| **CapacityBytes** | number, null<br><br>*read-only* | The size in bytes of this Volume |
| **Description** | <br><br>*read-write* |  |
| **Encrypted** | boolean, null<br><br>*read-write* | Is this Volume encrypted |
| **EncryptionTypes** | array<br><br>*read-write* | The types of encryption used by this Volume |
| **Id** | string<br><br>*read-only* | Uniquely identifies the resource within the collection of like resources. |
| **Identifiers** | array<br><br>*read-only* | The Durable names for the volume |
| **Links** { | object<br><br>*read-only* | Contains references to other resources that are related to this resource. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** | array<br><br>*read-only* | An array of references to the drives which contain this volume. This will reference Drives that either wholly or only partly contain this volume. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** {} | object<br><br>*read-write* | Oem extension object. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.navigationLink** | string<br><br>*read-write* |  |
| } |   |   |
| **Name** | string<br><br>*read-only* | The name of the resource or array element. |
| **Oem** {} | object<br><br>*read-write* | Oem extension object. |
| **Operations** | array<br><br>*read-only* | The operations currently running on the Volume |
| **OptimumIOSizeBytes** | number, null<br><br>*read-only* | The size in bytes of this Volume's optimum IO size. |
| **Status** { | object<br><br>*read-only* |  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** | <br><br>*read-only* | This represents the health state of this resource in the absence of its dependent resources. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** | <br><br>*read-only* | This indicates the known state of the resource, such as if it is enabled. |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** | <br><br>*read-only* | This represents the overall health state from the view of this resource. |
| } |   |   |
| **VolumeType** | <br><br>*read-only* | Is this drive currently predicting a failure in the near future |

---
TODO: postscript from MD file

