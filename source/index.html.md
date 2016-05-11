---
title: Redfish Schema

language tabs:
  - shell

search: true
---

# AccountService 1.0.2

Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.

**@odata.context**

**@odata.id**

**@odata.type**

**AccountLockoutCounterResetAfter**

**AccountLockoutDuration**

**AccountLockoutThreshold**

**Accounts**

[http://redfish.dmtf.org/schemas/v1/ManagerAccountCollection.json#/definitions/ManagerAccountCollection](#manageraccountcollection)

**AuthFailureLoggingThreshold**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**MaxPasswordLength**

Read Only

**MinPasswordLength**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Roles**

[http://redfish.dmtf.org/schemas/v1/RoleCollection.json#/definitions/RoleCollection](#rolecollection)

**ServiceEnabled**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

# AttributeRegistry 1.0.0

An Attribute Registry is a set of key-value pairs which are specific to a particular implementation or product, such that creating standardized property names would be impractical.  This schema describes the structure of a Registry, and also includes mechanisms for building user interfaces (menus) allowing consistent navigation of the contents.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Language**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OwningEntity**

Read Only

**RegistryEntries**

**RegistryVersion**

Read Only

**SupportedSystems**

# Bios 1.0.0

Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**AttributeRegistry**

**Attributes**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Chassis 1.2.0

A Chassis represents the physical components for any system.  This resource represents the sheet-metal confined spaces and logical zones like racks, enclosures, chassis and all other containers. Subsystems (like sensors), which operate outside of a system's data plane (meaning the resources are not accessible to software running on the system) are linked either directly or indirectly through this resource.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**AssetTag**

**ChassisType**

Read Only

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**IndicatorLED**

**Links**

Read Only

**Location**

**LogServices**

[http://redfish.dmtf.org/schemas/v1/LogServiceCollection.json#/definitions/LogServiceCollection](#logservicecollection)

**Manufacturer**

Read Only

**Model**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**PartNumber**

Read Only

**PhysicalSecurity**

**Power**

[http://redfish.dmtf.org/schemas/v1/Power.json#/definitions/Power](#power-1-1-0)

**PowerState**

Read Only

**SKU**

Read Only

**SerialNumber**

Read Only

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Thermal**

[http://redfish.dmtf.org/schemas/v1/Thermal.json#/definitions/Thermal](#thermal-1-1-0)

# ChassisCollection

A Collection of Chassis resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# ComputerSystem 1.1.0

This schema defines a computer system and its respective properties.  A computer system represents a machine (physical or virtual) and the local resources such as memory, cpu and other devices that can be accessed from that machine.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**AssetTag**

**Bios**

[http://redfish.dmtf.org/schemas/v1/Bios.json#/definitions/Bios](#bios-1-0-0)

**BiosVersion**

**Boot**

**Description**

**EthernetInterfaces**

[http://redfish.dmtf.org/schemas/v1/EthernetInterfaceCollection.json#/definitions/EthernetInterfaceCollection](#ethernetinterfacecollection)

**HostName**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**IndicatorLED**

**Links**

Read Only

**LogServices**

[http://redfish.dmtf.org/schemas/v1/LogServiceCollection.json#/definitions/LogServiceCollection](#logservicecollection)

**Manufacturer**

Read Only

**Memory**

[http://redfish.dmtf.org/schemas/v1/MemoryCollection.json#/definitions/MemoryCollection](#memorycollection)

**MemorySummary**

**Model**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**PartNumber**

Read Only

**PowerState**

Read Only

**ProcessorSummary**

**Processors**

[http://redfish.dmtf.org/schemas/v1/ProcessorCollection.json#/definitions/ProcessorCollection](#processorcollection)

**SKU**

Read Only

**SecureBoot**

[http://redfish.dmtf.org/schemas/v1/SecureBoot.json#/definitions/SecureBoot](#secureboot-1-0-0)

**SerialNumber**

Read Only

**SimpleStorage**

[http://redfish.dmtf.org/schemas/v1/SimpleStorageCollection.json#/definitions/SimpleStorageCollection](#simplestoragecollection)

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Storage**

[http://redfish.dmtf.org/schemas/v1/StorageCollection.json#/definitions/StorageCollection](#storagecollection)

**SystemType**

Read Only

**TrustedModules**

**UUID**

Read Only

# ComputerSystemCollection

A Collection of ComputerSystem resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Drive 1.0.0

Drive contains properties describing a single physical disk drive for any system, along with links to associated Volumes.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**AssetTag**

**BlockSizeBytes**

Read Only

**CapableSpeedGbs**

Read Only

**CapacityBytes**

Read Only

**Description**

**EncryptionAbility**

Read Only

**EncryptionStatus**

Read Only

**FailurePredicted**

Read Only

**HotspareType**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Identifiers**

Read Only

**IndicatorLED**

**Links**

Read Only

**Location**

Read Only

**Manufacturer**

Read Only

**MediaType**

Read Only

**Model**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**NegotiatedSpeedGbs**

Read Only

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**PartNumber**

Read Only

**PredictedMediaLifeLeftPercent**

Read Only

**Protocol**

Read Only

**Revision**

Read Only

**RotationSpeedRPM**

Read Only

**SKU**

Read Only

**SerialNumber**

Read Only

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**StatusIndicator**

# EthernetInterface 1.0.2

This schema defines a simple ethernet NIC resource.

**@odata.context**

**@odata.id**

**@odata.type**

**AutoNeg**

**Description**

**FQDN**

**FullDuplex**

**HostName**

**IPv4Addresses**

Read Only

**IPv6AddressPolicyTable**

**IPv6Addresses**

Read Only

**IPv6DefaultGateway**

Read Only

**IPv6StaticAddresses**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**InterfaceEnabled**

**MACAddress**

**MTUSize**

**MaxIPv6StaticAddresses**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**NameServers**

Read Only

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**PermanentMACAddress**

Read Only

**SpeedMbps**

**Status**

**UefiDevicePath**

Read Only

**VLAN**

**VLANs**

[http://redfish.dmtf.org/schemas/v1/VLanNetworkInterfaceCollection.json#/definitions/VLanNetworkInterfaceCollection](#vlannetworkinterfacecollection)

# EthernetInterfaceCollection

A Collection of EthernetInterface resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Event 1.1.0

The Event schema describes the JSON payload received by an Event Destination (which has subscribed to event notification) when events occurs.  This resource contains data about event(s), including descriptions, severity and MessageId reference to a Message Registry that can be accessed for further information. 

**@odata.context**

**@odata.id**

**@odata.type**

**Context**

Read Only

**Description**

**Events**

**Events@odata.count**

**Events@odata.navigationLink**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# EventDestination 1.0.2

An Event Destination desribes the target of an event subscription, including the types of events subscribed and context to provide to the target in the Event payload.

**@odata.context**

**@odata.id**

**@odata.type**

**Context**

**Description**

**Destination**

Read Only

**EventTypes**

Read Only

**HttpHeaders**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Protocol**

Read Only

# EventDestinationCollection

A Collection of EventDestination resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# EventService 1.0.2

The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**DeliveryRetryAttempts**

Read Only

**DeliveryRetryIntervalSeconds**

Read Only

**Description**

**EventTypesForSubscription**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**ServiceEnabled**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Subscriptions**

[http://redfish.dmtf.org/schemas/v1/EventDestinationCollection.json#/definitions/EventDestinationCollection](#eventdestinationcollection)

# JsonSchemaFile 1.0.2

This is the schema definition for the Schema File locator resource.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Languages**

Read Only

**Location**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Schema**

Read Only

# JsonSchemaFileCollection

A Collection of JsonSchemaFile resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# LogEntry 1.0.2

This resource defines the record format for a log.  It is designed to be used for SEL logs (from IPMI) as well as Event Logs and OEM-specific log formats.  The EntryType field indicates the type of log and the resource includes several additional properties dependent on the EntryType.

**@odata.context**

**@odata.id**

**@odata.type**

**Created**

Read Only

**Description**

**EntryCode**

Read Only

**EntryType**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Links**

Read Only

**Message**

Read Only

**MessageArgs**

Read Only

**MessageId**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OemRecordFormat**

Read Only

**SensorNumber**

Read Only

**SensorType**

Read Only

**Severity**

Read Only

# LogEntryCollection

A Collection of LogEntry resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# LogService 1.0.2

This resource represents the log service for the resource or service to which it is associated.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**DateTime**

**DateTimeLocalOffset**

**Description**

**Entries**

[http://redfish.dmtf.org/schemas/v1/LogEntryCollection.json#/definitions/LogEntryCollection](#logentrycollection)

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**MaxNumberOfRecords**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OverWritePolicy**

Read Only

**ServiceEnabled**

**Status**

# LogServiceCollection

A Collection of LogService resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Manager 1.1.0

This is the schema definition for a Manager.  Examples of managers are BMCs, Enclosure Managers, Management Controllers and other subsystems assigned managability functions.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**CommandShell**

**DateTime**

**DateTimeLocalOffset**

**Description**

**EthernetInterfaces**

[http://redfish.dmtf.org/schemas/v1/EthernetInterfaceCollection.json#/definitions/EthernetInterfaceCollection](#ethernetinterfacecollection)

**FirmwareVersion**

Read Only

**GraphicalConsole**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Links**

Read Only

**LogServices**

[http://redfish.dmtf.org/schemas/v1/LogServiceCollection.json#/definitions/LogServiceCollection](#logservicecollection)

**ManagerType**

Read Only

**Model**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**NetworkProtocol**

[http://redfish.dmtf.org/schemas/v1/ManagerNetworkProtocol.json#/definitions/ManagerNetworkProtocol](#managernetworkprotocol-1-0-2)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Redundancy**

Read Only

**Redundancy@odata.count**

**Redundancy@odata.navigationLink**

**SerialConsole**

**SerialInterfaces**

[http://redfish.dmtf.org/schemas/v1/SerialInterfaceCollection.json#/definitions/SerialInterfaceCollection](#serialinterfacecollection)

**ServiceEntryPointUUID**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/UUID](#resource-1-0-0)

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**UUID**

Read Only

**VirtualMedia**

[http://redfish.dmtf.org/schemas/v1/VirtualMediaCollection.json#/definitions/VirtualMediaCollection](#virtualmediacollection)

# ManagerAccount 1.0.2

The user accounts, owned by a Manager, are defined in this resource.  Changes to a Manager Account may affect the current Redfish service connection if this manager is responsible for the Redfish service.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Enabled**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Links**

Read Only

**Locked**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Password**

**RoleId**

**UserName**

# ManagerAccountCollection

A Collection of ManagerAccount resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# ManagerCollection

A Collection of Manager resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# ManagerNetworkProtocol 1.0.2

This resource is used to obtain or modify the network services managed by a given manager.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**FQDN**

Read Only

**HTTP**

**HTTPS**

**HostName**

Read Only

**IPMI**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**KVMIP**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**SNMP**

**SSDP**

**SSH**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Telnet**

**VirtualMedia**

# Memory 1.0.0

This is the schema definition for definition of a Memory and its configuration

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**AllowedSpeedsMHz**

Read Only

**BaseModuleType**

Read Only

**BusWidthBits**

Read Only

**CapacityMiB**

Read Only

**DataWidthBits**

Read Only

**Description**

**DeviceID**

Read Only

**DeviceLocator**

Read Only

**ErrorCorrection**

Read Only

**FirmwareApiVersion**

Read Only

**FirmwareRevision**

Read Only

**FunctionClasses**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**IsRankSpareEnabled**

Read Only

**IsSpareDeviceEnabled**

Read Only

**Manufacturer**

Read Only

**MaxTDPMilliWatts**

Read Only

**MemoryDeviceType**

Read Only

**MemoryLocation**

**MemoryMedia**

Read Only

**MemoryType**

Read Only

**Metrics**

[http://redfish.dmtf.org/schemas/v1/MemoryMetrics.json#/definitions/MemoryMetrics](#memorymetrics-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OperatingMemoryModes**

Read Only

**OperatingSpeedMhz**

Read Only

**PartNumber**

Read Only

**PersistentRegionSizeLimitMiB**

Read Only

**PowerManagementPolicy**

**RankCount**

Read Only

**Regions**

Read Only

**SecurityCapabilities**

**SerialNumber**

Read Only

**SpareDeviceCount**

Read Only

**SubsystemDeviceID**

Read Only

**SubsystemVendorID**

Read Only

**VendorID**

Read Only

**VolatileRegionSizeLimitMiB**

Read Only

# MemoryCollection

A Collection of Memory resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# MemoryMetrics 1.0.0

MemoryMetrics contains usage and health statistics for a single Memory module or device instance.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**BlockSizeBytes**

Read Only

**CurrentPeriod**

**Description**

**HealthData**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**LifeTime**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Message

# MessageRegistry 1.0.2

This is the schema definition for all Message Registries.  It represents the properties for the registries themselves.  The MessageId is formed per the Redfish specification.  It consists of the RegistryPrefix concatenated with the version concatenated with the unique identifier for the message registry entry.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Language**

Read Only

**Messages**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OwningEntity**

Read Only

**RegistryPrefix**

Read Only

**RegistryVersion**

Read Only

# MessageRegistryCollection

A Collection of MessageRegistry resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# MessageRegistryFile 1.0.2

This is the schema definition for the Schema File locator resource.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Languages**

Read Only

**Location**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Registry**

Read Only

# MessageRegistryFileCollection

A Collection of MessageRegistryFile resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Power 1.1.0

This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**PowerControl**

**PowerControl@odata.count**

**PowerControl@odata.navigationLink**

**PowerSupplies**

**PowerSupplies@odata.count**

**PowerSupplies@odata.navigationLink**

**Redundancy**

Read Only

**Redundancy@odata.count**

**Redundancy@odata.navigationLink**

**Voltages**

**Voltages@odata.count**

**Voltages@odata.navigationLink**

# Processor 1.0.2

This is the schema definition for the Processor resource.  It represents the properties of a processor attached to a System.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**InstructionSet**

Read Only

**Manufacturer**

Read Only

**MaxSpeedMHz**

Read Only

**Model**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**ProcessorArchitecture**

Read Only

**ProcessorId**

**ProcessorType**

Read Only

**Socket**

Read Only

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**TotalCores**

Read Only

**TotalThreads**

Read Only

# ProcessorCollection

A Collection of Processor resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Redundancy

This is the common redundancy definition and structure used in other Redfish schemas.

**MemberId**

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Resource 1.0.0

# Role 1.0.2

This resource defines a user role to be used in conjunction with a Manager Account.

**@odata.context**

**@odata.id**

**@odata.type**

**AssignedPrivileges**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**IsPredefined**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**OemPrivileges**

# RoleCollection

A Collection of Role resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# SecureBoot 1.0.0

This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**SecureBootCurrentBoot**

Read Only

**SecureBootEnable**

**SecureBootMode**

Read Only

# SerialInterface 1.0.2

This schema defines an asynchronous serial interface resource.

**@odata.context**

**@odata.id**

**@odata.type**

**BitRate**

**ConnectorType**

Read Only

**DataBits**

**Description**

**FlowControl**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**InterfaceEnabled**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Parity**

**PinOut**

Read Only

**SignalType**

Read Only

**StopBits**

# SerialInterfaceCollection

A Collection of SerialInterface resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# ServiceRoot 1.0.2

This object represents the root Redfish service.

**@odata.context**

**@odata.id**

**@odata.type**

**AccountService**

[http://redfish.dmtf.org/schemas/v1/AccountService.json#/definitions/AccountService](#accountservice-1-0-2)

**Chassis**

[http://redfish.dmtf.org/schemas/v1/ChassisCollection.json#/definitions/ChassisCollection](#chassiscollection)

**Description**

**EventService**

[http://redfish.dmtf.org/schemas/v1/EventService.json#/definitions/EventService](#eventservice-1-0-2)

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**JsonSchemas**

[http://redfish.dmtf.org/schemas/v1/JsonSchemaFileCollection.json#/definitions/JsonSchemaFileCollection](#jsonschemafilecollection)

**Links**

Read Only

**Managers**

[http://redfish.dmtf.org/schemas/v1/ManagerCollection.json#/definitions/ManagerCollection](#managercollection)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**RedfishVersion**

Read Only

**Registries**

[http://redfish.dmtf.org/schemas/v1/MessageRegistryFileCollection.json#/definitions/MessageRegistryFileCollection](#messageregistryfilecollection)

**SessionService**

[http://redfish.dmtf.org/schemas/v1/SessionService.json#/definitions/SessionService](#sessionservice-1-0-2)

**Systems**

[http://redfish.dmtf.org/schemas/v1/ComputerSystemCollection.json#/definitions/ComputerSystemCollection](#computersystemcollection)

**Tasks**

[http://redfish.dmtf.org/schemas/v1/TaskService.json#/definitions/TaskService](#taskservice-1-0-2)

**UUID**

Read Only

# Session 1.0.2

The Session resource describes a single connection (session) between a client and a Redfish service instance.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Password**

**UserName**

Read Only

# SessionCollection

A Collection of Session resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# SessionService 1.0.2

This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**ServiceEnabled**

**SessionTimeout**

**Sessions**

[http://redfish.dmtf.org/schemas/v1/SessionCollection.json#/definitions/SessionCollection](#sessioncollection)

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

# Settings 1.0.0

**ETag**

Read Only

**Messages**

Read Only

**SettingsObject**

**Time**

Read Only

# SimpleStorage 1.1.0

This is the schema definition for the Simple Storage resource.  It represents the properties of a storage controller and its directly-attached devices.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Devices**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**UefiDevicePath**

Read Only

# SimpleStorageCollection

A Collection of SimpleStorage resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Storage 1.0.0

This schema defines a storage subsystem and its respective properties.  A storage subsystem represents a set of storage controllers (physical or virtual) and the resources such as volumes that can be accessed from that subsystem.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**Description**

**Drives**

Read Only

**Drives@odata.count**

**Drives@odata.navigationLink**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Links**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Redundancy**

Read Only

**Redundancy@odata.count**

**Redundancy@odata.navigationLink**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**StorageControllers**

Read Only

**StorageControllers@odata.count**

**StorageControllers@odata.navigationLink**

**Volumes**

Read Only

**Volumes@odata.count**

**Volumes@odata.navigationLink**

# StorageCollection

A Collection of Storage resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Task 1.0.2

This resource contains information about a specific Task scheduled by or being executed by a Redfish service's Task Service.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**EndTime**

Read Only

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Messages**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**StartTime**

Read Only

**TaskState**

Read Only

**TaskStatus**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Health](#resource-1-0-0)

# TaskCollection

A Collection of Task resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# TaskService 1.0.2

This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.

**@odata.context**

**@odata.id**

**@odata.type**

**CompletedTaskOverWritePolicy**

Read Only

**DateTime**

Read Only

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**LifeCycleEventOnTaskStateChange**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**ServiceEnabled**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Tasks**

[http://redfish.dmtf.org/schemas/v1/TaskCollection.json#/definitions/TaskCollection](#taskcollection)

# Thermal 1.1.0

This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Fans**

**Fans@odata.count**

**Fans@odata.navigationLink**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Redundancy**

Read Only

**Redundancy@odata.count**

**Redundancy@odata.navigationLink**

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**Temperatures**

**Temperatures@odata.count**

**Temperatures@odata.navigationLink**

# VLanNetworkInterface 1.0.2

This resource contains information for a Virtual LAN (VLAN) network instance available on a manager, system or other device.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**VLANEnable**

**VLANId**

# VLanNetworkInterfaceCollection

A Collection of VLanNetworkInterface resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# VirtualMedia 1.0.2

This resource allows monitoring and control of an instance of virtual media (e.g. a remote CD, DVD, or USB device) functionality provided by a Manager for a system or device.

**@odata.context**

**@odata.id**

**@odata.type**

**ConnectedVia**

Read Only

**Description**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Image**

Read Only

**ImageName**

Read Only

**Inserted**

Read Only

**MediaTypes**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**WriteProtected**

Read Only

# VirtualMediaCollection

A Collection of VirtualMedia resource instances.

**@odata.context**

**@odata.id**

**@odata.type**

**Description**

**Members**

Read Only

**Members@odata.count**

**Members@odata.navigationLink**

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

# Volume 1.0.0

Volume contains properties used to describe a volume, virtual disk, LUN, or other logical storage entity for any system.

**@odata.context**

**@odata.id**

**@odata.type**

**Actions**

Read Only

**BlockSizeBytes**

Read Only

**CapacityBytes**

Read Only

**Description**

**Encrypted**

**EncryptionTypes**

**Id**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id](#resource-1-0-0)

**Identifiers**

Read Only

**Links**

Read Only

**Name**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name](#resource-1-0-0)

**Oem**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem](#resource-1-0-0)

**Operations**

Read Only

**OptimumIOSizeBytes**

Read Only

**Status**

[http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status](#resource-1-0-0)

**VolumeType**

Read Only

---
TODO: postscript from MD file

