---
Title: Redfish Schema

search: true
---
# AccountService 1.0.2

Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.

# AttributeRegistry 1.0.0

An Attribute Registry is a set of key-value pairs which are specific to a particular implementation or product, such that creating standardized property names would be impractical.  This schema describes the structure of a Registry, and also includes mechanisms for building user interfaces (menus) allowing consistent navigation of the contents.

# Bios 1.0.0

Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.

# Chassis 1.2.0

A Chassis represents the physical components for any system.  This resource represents the sheet-metal confined spaces and logical zones like racks, enclosures, chassis and all other containers. Subsystems (like sensors), which operate outside of a system's data plane (meaning the resources are not accessible to software running on the system) are linked either directly or indirectly through this resource.

# ChassisCollection 

A Collection of Chassis resource instances.

# ComputerSystem 1.1.0

This schema defines a computer system and its respective properties.  A computer system represents a machine (physical or virtual) and the local resources such as memory, cpu and other devices that can be accessed from that machine.

# ComputerSystemCollection 

A Collection of ComputerSystem resource instances.

# Drive 1.0.0

Drive contains properties describing a single physical disk drive for any system, along with links to associated Volumes.

# EthernetInterface 1.0.2

This schema defines a simple ethernet NIC resource.

# EthernetInterfaceCollection 

A Collection of EthernetInterface resource instances.

# Event 1.1.0

The Event schema describes the JSON payload received by an Event Destination (which has subscribed to event notification) when events occurs.  This resource contains data about event(s), including descriptions, severity and MessageId reference to a Message Registry that can be accessed for further information. 

# EventDestination 1.0.2

An Event Destination desribes the target of an event subscription, including the types of events subscribed and context to provide to the target in the Event payload.

# EventDestinationCollection 

A Collection of EventDestination resource instances.

# EventService 1.0.2

The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).

# JsonSchemaFile 1.0.2

This is the schema definition for the Schema File locator resource.

# JsonSchemaFileCollection 

A Collection of JsonSchemaFile resource instances.

# LogEntry 1.0.2

This resource defines the record format for a log.  It is designed to be used for SEL logs (from IPMI) as well as Event Logs and OEM-specific log formats.  The EntryType field indicates the type of log and the resource includes several additional properties dependent on the EntryType.

# LogEntryCollection 

A Collection of LogEntry resource instances.

# LogService 1.0.2

This resource represents the log service for the resource or service to which it is associated.

# LogServiceCollection 

A Collection of LogService resource instances.

# Manager 1.1.0

This is the schema definition for a Manager.  Examples of managers are BMCs, Enclosure Managers, Management Controllers and other subsystems assigned managability functions.

# ManagerAccount 1.0.2

The user accounts, owned by a Manager, are defined in this resource.  Changes to a Manager Account may affect the current Redfish service connection if this manager is responsible for the Redfish service.

# ManagerAccountCollection 

A Collection of ManagerAccount resource instances.

# ManagerCollection 

A Collection of Manager resource instances.

# ManagerNetworkProtocol 1.0.2

This resource is used to obtain or modify the network services managed by a given manager.

# Memory 1.0.0

This is the schema definition for definition of a Memory and its configuration

# MemoryCollection 

A Collection of Memory resource instances.

# MemoryMetrics 1.0.0

MemoryMetrics contains usage and health statistics for a single Memory module or device instance.

# Message 

# MessageRegistry 1.0.2

This is the schema definition for all Message Registries.  It represents the properties for the registries themselves.  The MessageId is formed per the Redfish specification.  It consists of the RegistryPrefix concatenated with the version concatenated with the unique identifier for the message registry entry.

# MessageRegistryCollection 

A Collection of MessageRegistry resource instances.

# MessageRegistryFile 1.0.2

This is the schema definition for the Schema File locator resource.

# MessageRegistryFileCollection 

A Collection of MessageRegistryFile resource instances.

# Power 1.1.0

This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.

# Processor 1.0.2

This is the schema definition for the Processor resource.  It represents the properties of a processor attached to a System.

# ProcessorCollection 

A Collection of Processor resource instances.

# Redundancy 

This is the common redundancy definition and structure used in other Redfish schemas.

# Resource 1.0.0

# Role 1.0.2

This resource defines a user role to be used in conjunction with a Manager Account.

# RoleCollection 

A Collection of Role resource instances.

# SecureBoot 1.0.0

This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.

# SerialInterface 1.0.2

This schema defines an asynchronous serial interface resource.

# SerialInterfaceCollection 

A Collection of SerialInterface resource instances.

# ServiceRoot 1.0.2

This object represents the root Redfish service.

# Session 1.0.2

The Session resource describes a single connection (session) between a client and a Redfish service instance.

# SessionCollection 

A Collection of Session resource instances.

# SessionService 1.0.2

This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.

# Settings 1.0.0

# SimpleStorage 1.1.0

This is the schema definition for the Simple Storage resource.  It represents the properties of a storage controller and its directly-attached devices.

# SimpleStorageCollection 

A Collection of SimpleStorage resource instances.

# Storage 1.0.0

This schema defines a storage subsystem and its respective properties.  A storage subsystem represents a set of storage controllers (physical or virtual) and the resources such as volumes that can be accessed from that subsystem.

# StorageCollection 

A Collection of Storage resource instances.

# Task 1.0.2

This resource contains information about a specific Task scheduled by or being executed by a Redfish service's Task Service.

# TaskCollection 

A Collection of Task resource instances.

# TaskService 1.0.2

This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.

# Thermal 1.1.0

This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.

# VLanNetworkInterface 1.0.2

This resource contains information for a Virtual LAN (VLAN) network instance available on a manager, system or other device.

# VLanNetworkInterfaceCollection 

A Collection of VLanNetworkInterface resource instances.

# VirtualMedia 1.0.2

This resource allows monitoring and control of an instance of virtual media (e.g. a remote CD, DVD, or USB device) functionality provided by a Manager for a system or device.

# VirtualMediaCollection 

A Collection of VirtualMedia resource instances.

# Volume 1.0.0

Volume contains properties used to describe a volume, virtual disk, LUN, or other logical storage entity for any system.
---
TODO: postscript from MD file

