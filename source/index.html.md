---
title: Redfish Schema

language tabs:
  - shell

search: true
---


# AccountService 1.0.2


```json
// AccountLockoutCounterResetAfter
{
  "type": "number",
  "readonly": false,
  "longDescription": "This property shall reference the threshold of time in seconds from the last failed login attempt at which point the AccountLockoutThreshold counter (that counts number of failed login attempts) is reset back to zero (at which point AccountLockoutThreshold failures would be required before the account is locked).  This value shall be less than or equal to AccountLockoutDuration. The threshold counter also resets to zero after each successful login.",
  "minimum": 0,
  "description": "The interval of time in seconds since the last failed login attempt at which point the lockout threshold counter for the account is reset to zero. Must be less than or equal to AccountLockoutDuration"
}
```
```json
// AccountLockoutDuration
{
  "type": [
    "number",
    "null"
  ],
  "readonly": false,
  "longDescription": "This property shall reference the period of time in seconds that an account is locked after the number of failed login attempts reaches the threshold referenced by AccountLockoutThreshold, within the window of time referenced by AccountLockoutCounterResetAfter.  The value shall be greater than or equal to the value of AccountLockoutResetAfter.  If set to 0, no lockout shall occur.",
  "minimum": 0,
  "description": "The time in seconds an account is locked after the account lockout threshold is met. Must be >= AccountLockoutResetAfter. If set to 0, no lockout will occur."
}
```
```json
// AccountLockoutThreshold
{
  "type": [
    "number",
    "null"
  ],
  "readonly": false,
  "longDescription": "This property shall reference the threshold of failed login attempts at which point the user's account is locked.  If set to 0, no lockout shall ever occur.",
  "minimum": 0,
  "description": "The number of failed login attempts before a user account is locked for a specified duration. (0=never locked)"
}
```
```json
// Accounts
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/ManagerAccount.json#/definitions/ManagerAccount"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of ManagerAccount resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AuthFailureLoggingThreshold
{
  "type": "number",
  "readonly": false,
  "longDescription": "This property shall reference the threshold for when an authorization failure is logged.  This represents a modulo function value, thus the failure shall be logged every nth occurrence where n represents the value of this property.",
  "minimum": 0,
  "description": "This is the number of authorization failures that need to occur before the failure attempt is logged to the manager log."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// MaxPasswordLength
{
  "type": "number",
  "readonly": true,
  "longDescription": "This property shall reference the maximum password length that the implementation will allow a password to be set to.",
  "minimum": 0,
  "description": "This is the maximum password length for this service."
}
```
```json
// MinPasswordLength
{
  "type": "number",
  "readonly": true,
  "longDescription": "This property shall reference the minimum password length that the implementation will allow a password to be set to.",
  "minimum": 0,
  "description": "This is the minimum password length for this service."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Roles
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Role.json#/definitions/Role"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Role resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// ServiceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
  "description": "This indicates whether this service is enabled."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.

|     |     |     |
| --- | --- | --- |
| **AccountLockoutCounterResetAfter** | number | The interval of time in seconds since the last failed login attempt at which point the lockout threshold counter for the account is reset to zero. Must be less than or equal to AccountLockoutDuration<br>*read-write* |
| **AccountLockoutDuration** | number, null | The time in seconds an account is locked after the account lockout threshold is met. Must be >= AccountLockoutResetAfter. If set to 0, no lockout will occur.<br>*read-write* |
| **AccountLockoutThreshold** | number, null | The number of failed login attempts before a user account is locked for a specified duration. (0=never locked)<br>*read-write* |
| **Accounts** { | object | A Collection of ManagerAccount resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **AuthFailureLoggingThreshold** | number | This is the number of authorization failures that need to occur before the failure attempt is logged to the manager log.<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **MaxPasswordLength** | number | This is the maximum password length for this service.<br>*read-only* |
| **MinPasswordLength** | number | This is the minimum password length for this service.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Roles** { | object | A Collection of Role resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **ServiceEnabled** | boolean, null | This indicates whether this service is enabled.<br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |

# AttributeRegistry 1.0.0


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Language
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be a string consisting of an RFC 5646 language code",
  "description": "This is the RFC 5646 compliant language code for the registry."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OwningEntity
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be a string that represents the publisher of this registry.",
  "description": "This is the organization or company that publishes this registry."
}
```
```json
// RegistryEntries
{
  "type": "object",
  "properties": {
    "Dependencies": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/Dependencies"
      },
      "longDescription": "The value of this property shall be an array containing a list of dependencies of attributes on this component.",
      "readonly": true,
      "description": "The array containing a list of dependencies of attributes on this component."
    },
    "Attributes": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/Attributes"
      },
      "longDescription": "The value of this property shall be an array containing the attributes and their possible values and other metadata.",
      "readonly": true,
      "description": "The array containing the attributes and their possible values."
    },
    "Menus": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/Menus"
      },
      "longDescription": "The value of this property shall be an array containing the attributes menus and their hierarchy.",
      "readonly": true,
      "description": "The array containing the attributes menus and their hierarchy."
    }
  },
  "additionalProperties": true,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// RegistryVersion
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the version of this attribute registry. The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification.",
  "description": "This is the attribute registry version which is used in the middle portion of a AttributeRegistry."
}
```
```json
// SupportedSystems
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/SupportedSystems"
  },
  "longDescription": "The value of this property shall be an array containing a list of systems supported by this attribute registry.",
  "description": "Array of systems supported by this attribute registry."
}
```

An Attribute Registry is a set of key-value pairs which are specific to a particular implementation or product, such that creating standardized property names would be impractical.  This schema describes the structure of a Registry, and also includes mechanisms for building user interfaces (menus) allowing consistent navigation of the contents.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Language** | string | This is the RFC 5646 compliant language code for the registry.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OwningEntity** | string | This is the organization or company that publishes this registry.<br>*read-only* |
| **RegistryEntries** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Dependencies** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Attributes** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Menus** |    |    |
|     } |   |   |
| **RegistryVersion** | string | This is the attribute registry version which is used in the middle portion of a AttributeRegistry.<br>*read-only* |
| **SupportedSystems** | array | Array of systems supported by this attribute registry.<br>*read-write* |

# Bios 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Bios.ChangePassword": {
      "$ref": "#/definitions/ChangePassword"
    },
    "#Bios.ResetBios": {
      "$ref": "#/definitions/ResetBios"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AttributeRegistry
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The reference to the Attribute Registry that lists the metadata describing the BIOS attribute settings in this resource.",
  "description": "The Resource ID of the Attribute Registry for the BIOS Attributes resource."
}
```
```json
// Attributes
{
  "type": "object",
  "properties": {},
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9]+": {
      "type": [
        "string",
        "boolean",
        "number",
        "null"
      ]
    }
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ChangePassword** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Bios.ResetBios** |    |    |
|     } |   |   |
| **AttributeRegistry** | string, null | The Resource ID of the Attribute Registry for the BIOS Attributes resource.<br>*read-write* |
| **Attributes** {} | object | <br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Chassis 1.2.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Chassis.Reset": {
      "$ref": "#/definitions/Reset"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AssetTag
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be an identifying string used to track the chassis for inventory purposes.",
  "description": "The user assigned asset tag for this chassis."
}
```
```json
// ChassisType
{
  "type": "string",
  "enum": [
    "Rack",
    "Blade",
    "Enclosure",
    "StandAlone",
    "RackMount",
    "Card",
    "Cartridge",
    "Row",
    "Pod",
    "Expansion",
    "Sidecar",
    "Zone",
    "Sled",
    "Shelf",
    "Drawer",
    "Module",
    "Component",
    "Other"
  ],
  "enumDescriptions": {
    "Pod": "A collection of equipment racks in a large, likely transportable, container",
    "Module": "A small, typically removable, chassis or card which contains devices for a particular subsystem or function",
    "StandAlone": "A single, free-standing system, commonly called a tower or desktop chassis",
    "Sidecar": "A chassis that mates mechanically with another chassis to expand its capabilities or capacity",
    "Row": "A collection of equipment racks",
    "Sled": "An enclosed or semi-enclosed, system chassis which must be plugged into a multi-system chassis to function normally similar to a blade type chassis.",
    "Other": "A chassis that does not fit any of these definitions",
    "Cartridge": "A small self-contained system intended to be plugged into a multi-system chassis",
    "Card": "A loose device or circuit board intended to be installed in a system or other enclosure",
    "Zone": "A logical division or portion of a physical chassis that contains multiple devices or systems that cannot be physically separated",
    "Rack": "An equipment rack, typically a 19-inch wide freestanding unit",
    "Enclosure": "A generic term for a chassis that does not fit any other description",
    "Drawer": "An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which may be slid into a multi-system chassis.",
    "Component": "A small chassis, card, or device which contains devices for a particular subsystem or function",
    "Expansion": "A chassis which expands the capabilities or capacity of another chassis",
    "Blade": "An enclosed or semi-enclosed, typically vertically-oriented, system chassis which must be plugged into a multi-system chassis to function normally",
    "RackMount": "A single system chassis designed specifically for mounting in an equipment rack",
    "Shelf": "An enclosed or semi-enclosed, typically horizontally-oriented, system chassis which must be plugged into a multi-system chassis to function normally"
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// IndicatorLED
{
  "anyOf": [
    {
      "$ref": "#/definitions/IndicatorLED"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "This value of this property shall contain the indicator light state for the indicator light associated with this system.",
  "description": "The state of the indicator LED, used to identify the chassis."
}
```
```json
// Links
{
  "properties": {
    "ManagedBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Contains": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
      },
      "longDescription": "The value of this property shall be a reference to the resource that represents the chassis that this chassis contains and shall be of type Chassis.",
      "readonly": true,
      "description": "An array of references to any other chassis that this chassis has in it."
    },
    "ManagersInChassis@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "CooledBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Storage@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Drives": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Drive.json#/definitions/Drive"
      },
      "longDescription": "The value of this property shall reference one or more resources of type Drive that are in this Chassis.",
      "readonly": true,
      "description": "An array of references to the disk drives located in this Chassis."
    },
    "Storage": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Storage.json#/definitions/Storage"
      },
      "longDescription": "The value of this property shall reference one or more resources of type Storage that are connected to or contained inside this Chassis.",
      "readonly": true,
      "description": "An array of references to the storage subsystems connected to or inside this Chassis."
    },
    "ComputerSystems@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Contains@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Drives@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "CooledBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/idRef"
      },
      "longDescription": "The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that cools this chassis.",
      "readonly": true,
      "description": "An array of ID[s] of resources that cool this chassis. Normally the ID will be a chassis or a specific set of fans."
    },
    "Storage@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagersInChassis": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Manager.json#/definitions/Manager"
      },
      "longDescription": "The value of this property shall reference one or more resources of type Manager that are in this Chassis.",
      "readonly": true,
      "description": "An array of references to the managers located in this Chassis."
    },
    "ManagedBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Drives@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ComputerSystems": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/ComputerSystem.json#/definitions/ComputerSystem"
      },
      "longDescription": "The value of this property shall be a reference to the resource that this physical container is associated with and shall reference a resource of type ComputerSystem.  If a ComputerSystem is also referenced in a Chassis that is referenced in a Contains link from this resource, that ComputerSystem shall not be referenced in this Chassis.",
      "readonly": true,
      "description": "An array of references to the computer systems contained in this chassis.  This will only reference ComputerSystems that are directly and wholly contained in this chassis."
    },
    "CooledBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "PoweredBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagedBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Manager.json#/definitions/Manager"
      },
      "longDescription": "The value of this property shall be a reference to the resource that manages this chassis and shall reference a resource of type Manager.",
      "readonly": true,
      "description": "An array of references to the Managers responsible for managing this chassis."
    },
    "PoweredBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Contains@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagersInChassis@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ComputerSystems@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "PoweredBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/idRef"
      },
      "longDescription": "The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this chassis.",
      "readonly": true,
      "description": "An array of ID[s] of resources that power this chassis. Normally the ID will be a chassis or a specific set of powerSupplies"
    },
    "ContainedBy": {
      "longDescription": "The value of this property shall be a reference to the resource that represents the chassis that contains this chassis and shall be of type Chassis.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis",
      "description": "A reference to the chassis that this chassis is contained by."
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Location
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem"
    },
    "InfoFormat": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall represent the format of the Info property.",
      "description": "This represents the format of the Info property."
    },
    "Info": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall represent the location of the resource.",
      "description": "This indicates the location of the resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// LogServices
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/LogService.json#/definitions/LogService"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of LogService resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Manufacturer
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the name of the organization responsible for producing the chassis. This organization might be the entity from whom the chassis is purchased, but this is not necessarily true.",
  "description": "This is the manufacturer of this chassis."
}
```
```json
// Model
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the name by which the manufacturer generally refers to the chassis.",
  "description": "This is the model number for the chassis."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// PartNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the chassis.",
  "description": "The part number for this chassis."
}
```
```json
// PhysicalSecurity
{
  "type": "object",
  "properties": {
    "IntrusionSensor": {
      "anyOf": [
        {
          "$ref": "#/definitions/IntrusionSensor"
        },
        {
          "type": "null"
        }
      ],
      "readonly": false,
      "longDescription": "This property shall represent the state of this physical security sensor.  Hardware intrusion indicates the internal hardware is detected as being accessed in an insecure state. Tampering detected indicates the physical tampering of the monitored entity is detected.",
      "description": "This indicates the known state of the physical security sensor, such as if it is hardware intrusion detected."
    },
    "IntrusionSensorNumber": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be a numerical identifier for this physical security sensor that is unique within this resource. ",
      "description": "A numerical identifier to represent the physical security sensor."
    },
    "IntrusionSensorReArm": {
      "anyOf": [
        {
          "$ref": "#/definitions/IntrusionSensorReArm"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the method to set back to the Normal statue of this physical security sensor.  Manual indicates manual re-arm is needed.  Automatic indicates the state is restored automatically as no abnormal physical security conditions are detected.",
      "description": "This indicates how the Normal state to be restored."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Power
{
  "properties": {
    "PowerSupplies@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Voltages@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "PowerControl@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "Voltages@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Voltages": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/Voltage"
      },
      "longDescription": "These properties shall be the definition for voltage sensors for a Redfish implementation.",
      "readonly": false,
      "description": "This is the definition for voltage sensors."
    },
    "PowerSupplies@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Redundancy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Redundancy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
      },
      "readonly": true,
      "description": "Redundancy information for the power subsystem of this system or device"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "PowerControl": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/PowerControl"
      },
      "longDescription": "These properties shall be the definition for power control (power reading and limiting) for a Redfish implementation.",
      "readonly": false,
      "description": "This is the definition for power control function (power reading/limiting)."
    },
    "PowerControl@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "Redundancy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "PowerSupplies": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Power.v1_0_0.json#/definitions/PowerSupply"
      },
      "longDescription": "This object shall contain details of the power supplies associated with this system or device",
      "readonly": false,
      "description": "Details of the power supplies associated with this system or device"
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent a power metrics resource for a Redfish implementation.",
  "type": "object",
  "description": "This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// PowerState
{
  "anyOf": [
    {
      "$ref": "#/definitions/PowerState"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the power state of the chassis.",
  "description": "This is the current power state of the chassis."
}
```
```json
// SKU
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the stock-keeping unit number for this chassis.",
  "description": "This is the SKU for this chassis."
}
```
```json
// SerialNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be a manufacturer-allocated number used to identify the chassis.",
  "description": "The serial number for this chassis."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Thermal
{
  "properties": {
    "Redundancy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Fans@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "Temperatures": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/Temperature"
      },
      "longDescription": "These properties shall be the definition for temperature sensors for a Redfish implementation.",
      "readonly": false,
      "description": "This is the definition for temperature sensors."
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Redundancy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Redundancy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
      },
      "longDescription": "The values of the properties in this array shall be used to show redundancy for fans and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups.",
      "readonly": true,
      "description": "This structure is used to show redundancy for fans.  The Component ids will reference the members of the redundancy groups."
    },
    "Fans": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Thermal.v1_0_0.json#/definitions/Fan"
      },
      "longDescription": "These properties shall be the definition for fans for a Redfish implementation.",
      "readonly": false,
      "description": "This is the definition for fans."
    },
    "Temperatures@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Fans@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Temperatures@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent a thermal metrics resource for a Redfish implementation.",
  "type": "object",
  "description": "This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

A Chassis represents the physical components for any system.  This resource represents the sheet-metal confined spaces and logical zones like racks, enclosures, chassis and all other containers. Subsystems (like sensors), which operate outside of a system's data plane (meaning the resources are not accessible to software running on the system) are linked either directly or indirectly through this resource.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Chassis.Reset** |    |    |
|     } |   |   |
| **AssetTag** | string, null | The user assigned asset tag for this chassis.<br>*read-write* |
| **ChassisType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **IndicatorLED** |  | The state of the indicator LED, used to identify the chassis.<br>*read-write* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Storage@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Contains@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagersInChassis@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ComputerSystems@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ContainedBy** |    |    |
|     } |   |   |
| **Location** *(v1.2.0)* { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**InfoFormat** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Info** |    |    |
|     } |   |   |
| **LogServices** { | object | A Collection of LogService resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Manufacturer** | string, null | This is the manufacturer of this chassis.<br>*read-only* |
| **Model** | string, null | This is the model number for the chassis.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **PartNumber** | string, null | The part number for this chassis.<br>*read-only* |
| **PhysicalSecurity** *(v1.1.0)* { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensor** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorNumber** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IntrusionSensorReArm** |    |    |
|     } |   |   |
| **Power** { | object | This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Voltages** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerControl@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PowerSupplies** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **PowerState** *(v1.0.1)* |  | This is the current power state of the chassis.<br>*read-only* |
| **SKU** | string, null | This is the SKU for this chassis.<br>*read-only* |
| **SerialNumber** | string, null | The serial number for this chassis.<br>*read-only* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Thermal** { | object | This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Redundancy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Fans@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Temperatures@odata.count** |    |    |
|     } |   |   |

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


# ChassisCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Chassis resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# ComputerSystem 1.1.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#ComputerSystem.Reset": {
      "$ref": "#/definitions/Reset"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AssetTag
{
  "type": [
    "string",
    "null"
  ],
  "readonly": false,
  "longDescription": "The value of this property shall contain the value of the asset tag of the system.",
  "description": "The user definable tag that can be used to track this computer system for inventory or other client purposes"
}
```
```json
// Bios
{
  "properties": {
    "Actions": {
      "properties": {
        "Oem": {
          "type": "object",
          "properties": {},
          "additionalProperties": true,
          "patternProperties": {
            "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
              "type": [
                "array",
                "boolean",
                "number",
                "null",
                "object",
                "string"
              ],
              "description": "This property shall specify a valid odata or Redfish property."
            }
          }
        },
        "#Bios.ChangePassword": {
          "$ref": "#/definitions/ChangePassword"
        },
        "#Bios.ResetBios": {
          "$ref": "#/definitions/ResetBios"
        }
      },
      "readonly": true,
      "longDescription": "The Actions property shall contain the available actions for this resource.",
      "type": "object",
      "description": "The available actions for this resource.",
      "additionalProperties": false,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "Attributes": {
      "longDescription": "BIOS Attribute settings appear as additional properties in this object, and can be looked up in the Attribute Registry by their AttributeName.",
      "$ref": "#/definitions/Attributes",
      "description": "This is the manufacturer/provider specific list of BIOS attributes."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "AttributeRegistry": {
      "type": [
        "string",
        "null"
      ],
      "longDescription": "The reference to the Attribute Registry that lists the metadata describing the BIOS attribute settings in this resource.",
      "description": "The Resource ID of the Attribute Registry for the BIOS Attributes resource."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent BIOS attributes for a Redfish implementation.",
  "type": "object",
  "description": "Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.",
  "additionalProperties": true,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// BiosVersion
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be the version string of the currently installed and running BIOS (for x86 systems).  For other systems, the value may contain a version string representing the primary system firmware.",
  "description": "The version of the system BIOS or primary system firmware."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EthernetInterfaces
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/EthernetInterface.json#/definitions/EthernetInterface"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of EthernetInterface resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// HostName
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be the host name for this system, as reported by the operating system or hypervisor.  This value is typically provided to the Manager by a service running in the host operating system.",
  "description": "The DNS Host Name, without any domain information"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// IndicatorLED
{
  "anyOf": [
    {
      "$ref": "#/definitions/IndicatorLED"
    },
    {
      "type": "null"
    }
  ],
  "readonly": false,
  "longDescription": "The value of this property shall contain the indicator light state for the indicator light associated with this system.",
  "description": "The state of the indicator LED, used to identify the system"
}
```
```json
// Links
{
  "properties": {
    "Chassis@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "ManagedBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "CooledBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/idRef"
      },
      "longDescription": "The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this computer system.",
      "readonly": true,
      "description": "An array of ID[s] of resources that cool this computer system. Normally the ID will be a chassis or a specific set of fans."
    },
    "PoweredBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "CooledBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "ManagedBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Manager.json#/definitions/Manager"
      },
      "longDescription": "The value of this property shall reference a resource of type manager that represents the resource with management responsibility for this resource.",
      "readonly": true,
      "description": "An array of references to the Managers responsible for this system"
    },
    "PoweredBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "CooledBy@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Chassis@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagedBy@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "PoweredBy": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/idRef"
      },
      "longDescription": "The value of this property shall be an array of IDs containing pointers consistent with JSON pointer syntax to the resource that powers this computer system.",
      "readonly": true,
      "description": "An array of ID[s] of resources that power this computer system. Normally the ID will be a chassis or a specific set of powerSupplies"
    },
    "Chassis": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
      },
      "longDescription": "The value of this property shall reference a resource of type Chassis that represents the physical container associated with this resource.",
      "readonly": true,
      "description": "An array of references to the chassis in which this system is contained"
    },
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// LogServices
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/LogService.json#/definitions/LogService"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of LogService resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Manufacturer
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain a value that represents the manufacturer of the system.",
  "description": "The manufacturer or OEM of this system."
}
```
```json
// Memory
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Memory.json#/definitions/Memory"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Memory resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Model
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the information about how the manufacturer references this system.",
  "description": "The model number for this system"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// PartNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the part number for the system as defined by the manufacturer.",
  "description": "The part number for this system"
}
```
```json
// PowerState
{
  "anyOf": [
    {
      "$ref": "#/definitions/PowerState"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the power state of the system.",
  "description": "This is the current power state of the system"
}
```
```json
// ProcessorSummary
{
  "type": "object",
  "properties": {
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "Count": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall contain the number of central processors in the system.",
      "minimum": 0,
      "description": "The number of processors in the system."
    },
    "Model": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall contain the processor model for the central processors in the system, per the description in Table 22 of the SMBIOS Specification DSP0134 2.8 or later.",
      "description": "The processor model for the primary or majority of processors in this system."
    }
  },
  "description": "This object describes the central processors of the system in general detail.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Processors
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Processor.json#/definitions/Processor"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Processor resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SKU
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the Stock Keeping Unit (SKU) for the system.",
  "description": "The manufacturer SKU for this system"
}
```
```json
// SecureBoot
{
  "properties": {
    "SecureBootMode": {
      "anyOf": [
        {
          "$ref": "#/definitions/SecureBootModeType"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall contain the current Secure Boot mode, as defined in the UEFI Specification.",
      "description": "Current Secure Boot Mode."
    },
    "Actions": {
      "properties": {
        "Oem": {
          "type": "object",
          "properties": {},
          "additionalProperties": true,
          "patternProperties": {
            "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
              "type": [
                "array",
                "boolean",
                "number",
                "null",
                "object",
                "string"
              ],
              "description": "This property shall specify a valid odata or Redfish property."
            }
          }
        },
        "#SecureBoot.ResetKeys": {
          "$ref": "#/definitions/ResetKeys"
        }
      },
      "readonly": true,
      "longDescription": "The Actions property shall contain the available actions for this resource.",
      "type": "object",
      "description": "The available actions for this resource.",
      "additionalProperties": false,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "SecureBootCurrentBoot": {
      "anyOf": [
        {
          "$ref": "#/definitions/SecureBootCurrentBootType"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "The value of this property shall indicate the UEFI Secure Boot state during the current boot cycle.",
      "description": "Secure Boot state during the current boot cycle."
    },
    "SecureBootEnable": {
      "type": [
        "boolean",
        "null"
      ],
      "longDescription": "Setting this property to true enables UEFI Secure Boot, and setting it to false disables it. This property can be enabled only in UEFI boot mode.",
      "description": "Enable or disable UEFI Secure Boot (takes effect on next boot)."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent a UEFI Secure Boot resource for a Redfish implementation.",
  "type": "object",
  "description": "This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SerialNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the serial number for the system.",
  "description": "The serial number for this system"
}
```
```json
// SimpleStorage
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/SimpleStorage.json#/definitions/SimpleStorage"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of SimpleStorage resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Storage
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Storage.json#/definitions/Storage"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Storage resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SystemType
{
  "type": "string",
  "enum": [
    "Physical",
    "Virtual",
    "OS",
    "PhysicallyPartitioned",
    "VirtuallyPartitioned"
  ],
  "enumDescriptions": {
    "OS": "An operating system instance",
    "VirtuallyPartitioned": "A virtual or software-based partition of a computer system",
    "PhysicallyPartitioned": "A hardware-based partition of a computer system",
    "Physical": "A computer system",
    "Virtual": "A virtual machine instance running on this system"
  }
}
```
```json
// TrustedModules
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/TrustedModules"
  },
  "longDescription": "This object shall contain an array of objects with properties which describe the truted modules for the current resource.",
  "description": "This object describes the array of Trusted Modules in the system."
}
```
```json
// UUID
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/UUID"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be used to contain a universal unique identifier number for the system. RFC4122 describes methods that can be used to create the value. The value should be considered to be opaque. Client software should only treat the overall value as a universally unique identifier and should not interpret any sub-fields within the UUID. If the system supports SMBIOS, the value and byte order of the property should match byte-for-byte with the memory byte order (from lowest address to highest) of the SMBIOS UUID. Following this order will make it simpler to correlate the UUID with the SMBIOS UUID",
  "description": "The universal unique identifier (UUID) for this system"
}
```

This schema defines a computer system and its respective properties.  A computer system represents a machine (physical or virtual) and the local resources such as memory, cpu and other devices that can be accessed from that machine.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#ComputerSystem.Reset** |    |    |
|     } |   |   |
| **AssetTag** | string, null | The user definable tag that can be used to track this computer system for inventory or other client purposes<br>*read-write* |
| **Bios** *(v1.1.0)* { | object | Bios contains properties surrounding a BIOS Attribute Registry (where the system-specific BIOS attributes are described) and the Actions needed to perform changes to BIOS settings, which typically require a system reset to apply.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Attributes** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AttributeRegistry** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **BiosVersion** | string, null | The version of the system BIOS or primary system firmware.<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **EthernetInterfaces** { | object | A Collection of EthernetInterface resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **HostName** | string, null | The DNS Host Name, without any domain information<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **IndicatorLED** |  | The state of the indicator LED, used to identify the system<br>*read-write* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CooledBy@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagedBy@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PoweredBy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Chassis** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
|     } |   |   |
| **LogServices** { | object | A Collection of LogService resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Manufacturer** | string, null | The manufacturer or OEM of this system.<br>*read-only* |
| **Memory** *(v1.1.0)* { | object | A Collection of Memory resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Model** | string, null | The model number for this system<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **PartNumber** | string, null | The part number for this system<br>*read-only* |
| **PowerState** |  | This is the current power state of the system<br>*read-only* |
| **ProcessorSummary** { | object | This object describes the central processors of the system in general detail.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Model** |    |    |
|     } |   |   |
| **Processors** { | object | A Collection of Processor resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **SKU** | string, null | The manufacturer SKU for this system<br>*read-only* |
| **SecureBoot** *(v1.1.0)* { | object | This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootMode** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootCurrentBoot** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecureBootEnable** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **SerialNumber** | string, null | The serial number for this system<br>*read-only* |
| **SimpleStorage** { | object | A Collection of SimpleStorage resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Storage** *(v1.1.0)* { | object | A Collection of Storage resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **SystemType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **TrustedModules** *(v1.1.0)* | array | This object describes the array of Trusted Modules in the system.<br>*read-write* |
| **UUID** |  | The universal unique identifier (UUID) for this system<br>*read-only* |

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


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/ComputerSystem.json#/definitions/ComputerSystem"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of ComputerSystem resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Drive 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Drive.SecureErase": {
      "$ref": "#/definitions/SecureErase"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AssetTag
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be an identifying string used to track the drive for inventory purposes.",
  "description": "The user assigned asset tag for this drive."
}
```
```json
// BlockSizeBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain size of the smallest addressible unit of the associated drive.",
  "description": "The size of the smallest addressible unit (Block) of this drive in bytes"
}
```
```json
// CapableSpeedGbs
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain fastest capable bus speed of the associated drive.",
  "description": "The speed which this drive can communicate to a storage controller in ideal conditions in Gigabits per second"
}
```
```json
// CapacityBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the raw size in bytes of the associated drive.",
  "description": "The size in bytes of this Drive"
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EncryptionAbility
{
  "anyOf": [
    {
      "$ref": "#/definitions/EncryptionAbility"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the encryption ability for the associated drive.",
  "description": "The encryption abilities of this drive"
}
```
```json
// EncryptionStatus
{
  "anyOf": [
    {
      "$ref": "#/definitions/EncryptionStatus"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the encrytion status for the associated drive.",
  "description": "The status of the encrytion of this drive"
}
```
```json
// FailurePredicted
{
  "type": [
    "boolean",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain failure information as defined by the manufacturer for the associated drive.",
  "description": "Is this drive currently predicting a failure in the near future"
}
```
```json
// HotspareType
{
  "anyOf": [
    {
      "$ref": "#/definitions/HotspareType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the hot spare type for the associated drive. If the drive is currently serving as a hot spare its Status.State field shall be 'StandbySpare' and 'Enabled' when it is being used as part of a Volume.",
  "description": "The type of hotspare this drive is currently serving as"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Identifiers
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.v1_1_0.json#/definitions/Identifier"
  },
  "longDescription": "This property shall contain a list of all known durable names for the associated drive.",
  "readonly": true,
  "description": "The Durable names for the drive"
}
```
```json
// IndicatorLED
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.v1_1_0.json#/definitions/IndicatorLED"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "This value of this property shall contain the indicator light state for the indicator light associated with this drive.",
  "description": "The state of the indicator LED, used to identify the drive."
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "Volumes@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Volumes": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Volume.json#/definitions/Volume"
      },
      "longDescription": "The value of this property shall be a reference to the resources that this drive is associated with and shall reference a resource of type Volume. This shall include all Volume resources of which this Drive is a member and all Volumes for which this Drive is acting as a spare if the HotspareType is Dedicated.",
      "readonly": true,
      "description": "An array of references to the volumes contained in this drive. This will reference Volumes that are either wholly or only partly contained by this drive."
    },
    "Volumes@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Location
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.v1_1_0.json#/definitions/Location"
  },
  "longDescription": "This property shall contain location information of the associated drive.",
  "readonly": true,
  "description": "The Location of the drive"
}
```
```json
// Manufacturer
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the name of the organization responsible for producing the drive. This organization might be the entity from whom the drive is purchased, but this is not necessarily true.",
  "description": "This is the manufacturer of this drive."
}
```
```json
// MediaType
{
  "anyOf": [
    {
      "$ref": "#/definitions/MediaType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the type of media contained in the associated drive.",
  "description": "The type of media contained in this drive"
}
```
```json
// Model
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the name by which the manufacturer generally refers to the drive.",
  "description": "This is the model number for the drive."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// NegotiatedSpeedGbs
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain current bus speed of the associated drive.",
  "description": "The speed which this drive is currently communicating to the storage controller in Gigabits per second"
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// PartNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be a part number assigned by the organization that is responsible for producing or manufacturing the drive.",
  "description": "The part number for this drive."
}
```
```json
// PredictedMediaLifeLeftPercent
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain an indicator of the percentage of life remaining in the Drive's media.",
  "description": "The percentage of reads and writes that are predicted to still be available for the media"
}
```
```json
// Protocol
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Storage.v1_0_0.json#/definitions/Protocol"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the protocol the associated drive is using to communicate to the storage controller for this system.",
  "description": "The protocol this drive is using to communicate to the storage controller"
}
```
```json
// Revision
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the revision as defined by the manufacturer for the associated drive.",
  "description": "The revision of this Drive"
}
```
```json
// RotationSpeedRPM
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain rotation speed of the associated drive.",
  "description": "The rotation speed of this Drive in Revolutions per Minute (RPM)"
}
```
```json
// SKU
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the stock-keeping unit number for this drive.",
  "description": "This is the SKU for this drive."
}
```
```json
// SerialNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be a manufacturer-allocated number used to identify the drive.",
  "description": "The serial number for this drive."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// StatusIndicator
{
  "anyOf": [
    {
      "$ref": "#/definitions/StatusIndicator"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "The value of this property shall contain the status indicator state for the status indicator associated with this drive. The valid values for this property are specified through the Redfish.AllowableValues annotation.",
  "description": "The state of the status indicator, used to communicate status information about this drive."
}
```

Drive contains properties describing a single physical disk drive for any system, along with links to associated Volumes.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Drive.SecureErase** |    |    |
|     } |   |   |
| **AssetTag** | string, null | The user assigned asset tag for this drive.<br>*read-write* |
| **BlockSizeBytes** | number, null | The size of the smallest addressible unit (Block) of this drive in bytes<br>*read-only* |
| **CapableSpeedGbs** | number, null | The speed which this drive can communicate to a storage controller in ideal conditions in Gigabits per second<br>*read-only* |
| **CapacityBytes** | number, null | The size in bytes of this Drive<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **EncryptionAbility** |  | The encryption abilities of this drive<br>*read-only* |
| **EncryptionStatus** |  | The status of the encrytion of this drive<br>*read-only* |
| **FailurePredicted** | boolean, null | Is this drive currently predicting a failure in the near future<br>*read-only* |
| **HotspareType** |  | The type of hotspare this drive is currently serving as<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Identifiers** | array | The Durable names for the drive<br>*read-only* |
| **IndicatorLED** |  | The state of the indicator LED, used to identify the drive.<br>*read-write* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Volumes@odata.navigationLink** |    |    |
|     } |   |   |
| **Location** | array | The Location of the drive<br>*read-only* |
| **Manufacturer** | string, null | This is the manufacturer of this drive.<br>*read-only* |
| **MediaType** |  | The type of media contained in this drive<br>*read-only* |
| **Model** | string, null | This is the model number for the drive.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **NegotiatedSpeedGbs** | number, null | The speed which this drive is currently communicating to the storage controller in Gigabits per second<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **PartNumber** | string, null | The part number for this drive.<br>*read-only* |
| **PredictedMediaLifeLeftPercent** | number, null | The percentage of reads and writes that are predicted to still be available for the media<br>*read-only* |
| **Protocol** |  | The protocol this drive is using to communicate to the storage controller<br>*read-only* |
| **Revision** | string, null | The revision of this Drive<br>*read-only* |
| **RotationSpeedRPM** | number, null | The rotation speed of this Drive in Revolutions per Minute (RPM)<br>*read-only* |
| **SKU** | string, null | This is the SKU for this drive.<br>*read-only* |
| **SerialNumber** | string, null | The serial number for this drive.<br>*read-only* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **StatusIndicator** |  | The state of the status indicator, used to communicate status information about this drive.<br>*read-write* |

# EthernetInterface 1.0.2


```json
// AutoNeg
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be true if auto negotiation of speed and duplex is enabled on this interface and false if it is disabled.",
  "description": "This indicates if the speed and duplex are automatically negotiated and configured on this interface."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// FQDN
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be the fully qualified domain name for this interface.",
  "description": "This is the complete, fully qualified domain name obtained by DNS for this interface."
}
```
```json
// FullDuplex
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall represent the duplex status of the Ethernet connection on this interface.",
  "description": "This indicates if the interface is in Full Duplex mode or not."
}
```
```json
// HostName
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be host name for this interface.",
  "description": "The DNS Host Name, without any domain information"
}
```
```json
// IPv4Addresses
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/IPAddresses.v1_0_0.json#/definitions/IPv4Address"
  },
  "longDescription": "The value of this property shall be an array of objects used to represent the IPv4 connection characteristics for this interface.",
  "readonly": true,
  "description": "The IPv4 addresses assigned to this interface"
}
```
```json
// IPv6AddressPolicyTable
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/IPv6AddressPolicyEntry"
  },
  "longDescription": "The value of this property shall be an array of objects used to represent the Address Selection Policy Table as defined in RFC 6724.",
  "description": "An array representing the RFC 6724 Address Selection Policy Table."
}
```
```json
// IPv6Addresses
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/IPAddresses.v1_0_0.json#/definitions/IPv6Address"
  },
  "longDescription": "The value of this property shall be an array of objects used to represent the IPv6 connection characteristics for this interface.",
  "readonly": true,
  "description": "This array of objects enumerates all of the currently assigned IPv6 addresses on this interface."
}
```
```json
// IPv6DefaultGateway
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the current IPv6 default gateway address that is in use on this interface.",
  "description": "This is the IPv6 default gateway address that is currently in use on this interface."
}
```
```json
// IPv6StaticAddresses
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/IPAddresses.v1_0_0.json#/definitions/IPv6StaticAddress"
  },
  "longDescription": "The value of this property shall be an array of objects used to represent the IPv6 static connection characteristics for this interface.",
  "readonly": true,
  "description": "This array of objects represents all of the IPv6 static addresses to be assigned on this interface."
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// InterfaceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this interface is enabled.",
  "description": "This indicates whether this interface is enabled."
}
```
```json
// MACAddress
{
  "anyOf": [
    {
      "$ref": "#/definitions/MACAddress"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "The value of this property shall be the effective current MAC Address of this interface. If an assignable MAC address is not supported, this is a read only alias of the PermanentMACAddress.",
  "description": "This is the currently configured MAC address of the (logical port) interface."
}
```
```json
// MTUSize
{
  "type": [
    "number",
    "null"
  ],
  "longDescription": "The value of this property shall be the size in bytes of largest Protocol Data Unit (PDU) that can be passed in an Ethernet (MAC) frame on this interface.",
  "description": "This is the currently configured Maximum Transmission Unit (MTU) in bytes on this interface."
}
```
```json
// MaxIPv6StaticAddresses
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall indicate the number of array items supported by IPv6StaticAddresses.",
  "description": "This indicates the maximum number of Static IPv6 addresses that can be configured on this interface."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// NameServers
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "The value of this property shall be the DNS name servers used on this interface.",
  "readonly": true,
  "description": "This represents DNS name servers that are currently in use on this interface."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// PermanentMACAddress
{
  "anyOf": [
    {
      "$ref": "#/definitions/MACAddress"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the Permanent MAC Address of this interface (port). This value is typically programmed during the manufacturing time. This address is not assignable.",
  "description": "This is the permanent MAC address assigned to this interface (port)"
}
```
```json
// SpeedMbps
{
  "type": [
    "number",
    "null"
  ],
  "longDescription": "The value of this property shall be the link speed of the interface in Mbps.",
  "description": "This is the current speed in Mbps of this interface."
}
```
```json
// Status
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// UefiDevicePath
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the UEFI device path to the device which implements this interface (port).",
  "description": "The UEFI device path for this interface"
}
```
```json
// VLAN
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/VLanNetworkInterface.v1_0_0.json#/definitions/VLAN"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "The value of this property shall be the VLAN for this interface.  If this interface supports more than one VLAN, the VLAN property shall not be present and the VLANS collection link shall be present instead.",
  "description": "If this Network Interface supports more than one VLAN, this property will not be present and the client should look for VLANs collection in the link section of this resource."
}
```
```json
// VLANs
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/VLanNetworkInterface.json#/definitions/VLanNetworkInterface"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of VLanNetworkInterface resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

This schema defines a simple ethernet NIC resource.

|     |     |     |
| --- | --- | --- |
| **AutoNeg** | boolean, null | This indicates if the speed and duplex are automatically negotiated and configured on this interface.<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **FQDN** | string, null | This is the complete, fully qualified domain name obtained by DNS for this interface.<br>*read-write* |
| **FullDuplex** | boolean, null | This indicates if the interface is in Full Duplex mode or not.<br>*read-write* |
| **HostName** | string, null | The DNS Host Name, without any domain information<br>*read-write* |
| **IPv4Addresses** | array | The IPv4 addresses assigned to this interface<br>*read-only* |
| **IPv6AddressPolicyTable** | array | An array representing the RFC 6724 Address Selection Policy Table.<br>*read-write* |
| **IPv6Addresses** | array | This array of objects enumerates all of the currently assigned IPv6 addresses on this interface.<br>*read-only* |
| **IPv6DefaultGateway** | string, null | This is the IPv6 default gateway address that is currently in use on this interface.<br>*read-only* |
| **IPv6StaticAddresses** | array | This array of objects represents all of the IPv6 static addresses to be assigned on this interface.<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **InterfaceEnabled** | boolean, null | This indicates whether this interface is enabled.<br>*read-write* |
| **MACAddress** |  | This is the currently configured MAC address of the (logical port) interface.<br>*read-write* |
| **MTUSize** | number, null | This is the currently configured Maximum Transmission Unit (MTU) in bytes on this interface.<br>*read-write* |
| **MaxIPv6StaticAddresses** | number, null | This indicates the maximum number of Static IPv6 addresses that can be configured on this interface.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **NameServers** | array | This represents DNS name servers that are currently in use on this interface.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **PermanentMACAddress** |  | This is the permanent MAC address assigned to this interface (port)<br>*read-only* |
| **SpeedMbps** | number, null | This is the current speed in Mbps of this interface.<br>*read-write* |
| **Status** |  | <br>*read-write* |
| **UefiDevicePath** | string, null | The UEFI device path for this interface<br>*read-only* |
| **VLAN** |  | If this Network Interface supports more than one VLAN, this property will not be present and the client should look for VLANs collection in the link section of this resource.<br>*read-write* |
| **VLANs** { | object | A Collection of VLanNetworkInterface resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |

# EthernetInterfaceCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/EthernetInterface.json#/definitions/EthernetInterface"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of EthernetInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Event 1.1.0


```json
// Context
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property shall contain a client supplied context for the Event Destination to which this event is being sent.",
  "description": "A context can be supplied at subscription time.  This property is the context value supplied by the subscriber."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Events
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/EventRecord"
  },
  "longDescription": "The value of this resource shall be an array of Event objects used to represent the occurrence of one or more events.",
  "description": "Each event in this array has a set of properties that describe the event.  Since this is an array, more than one event can be sent simultaneously."
}
```
```json
// Events@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

The Event schema describes the JSON payload received by an Event Destination (which has subscribed to event notification) when events occurs.  This resource contains data about event(s), including descriptions, severity and MessageId reference to a Message Registry that can be accessed for further information. 

|     |     |     |
| --- | --- | --- |
| **Context** *(v1.1.0)* | string | A context can be supplied at subscription time.  This property is the context value supplied by the subscriber.<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **Events** | array | Each event in this array has a set of properties that describe the event.  Since this is an array, more than one event can be sent simultaneously.<br>*read-write* |
| **Events@odata.navigationLink** | string | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# EventDestination 1.0.2


```json
// Context
{
  "type": "string",
  "longDescription": "This property shall contain a client supplied context that will remain with the connection through the connections lifetime.",
  "description": "A client-supplied string that is stored with the event destination subscription."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Destination
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property shall contain a URI to the destination where the events will be sent.",
  "format": "uri",
  "description": "The URI of the destination Event Service."
}
```
```json
// EventTypes
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Event.v1_0_0.json#/definitions/EventType"
  },
  "readonly": true,
  "description": "This property shall contain the types of events that shall be sent to the desination."
}
```
```json
// HttpHeaders
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/HttpHeaderProperty"
  },
  "longDescription": "This property shall contain an object consisting of the names and values of of HTTP header to be included with every event POST to the Event Destination.  This property shall be null on a GET.",
  "description": "This is for setting HTTP headers, such as authorization information.  This object will be null on a GET."
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Protocol
{
  "type": "string",
  "enum": [
    "Redfish"
  ]
}
```

An Event Destination desribes the target of an event subscription, including the types of events subscribed and context to provide to the target in the Event payload.

|     |     |     |
| --- | --- | --- |
| **Context** | string | A client-supplied string that is stored with the event destination subscription.<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Destination** | string | The URI of the destination Event Service.<br>*read-only* |
| **EventTypes** | array | This property shall contain the types of events that shall be sent to the desination.<br>*read-only* |
| **HttpHeaders** | array | This is for setting HTTP headers, such as authorization information.  This object will be null on a GET.<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Protocol** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |

## Property Details

### Protocol:

| string |
| --- |
| Redfish | 


# EventDestinationCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/EventDestination.json#/definitions/EventDestination"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of EventDestination resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# EventService 1.0.2


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#EventService.SubmitTestEvent": {
      "$ref": "#/definitions/SubmitTestEvent"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// DeliveryRetryAttempts
{
  "type": "number",
  "readonly": true,
  "longDescription": "The value of this property shall be the number of retrys attempted for any given event to the subscription destination before the subscription is terminated.",
  "description": "This is the number of attempts an event posting is retried before the subscription is terminated."
}
```
```json
// DeliveryRetryIntervalSeconds
{
  "type": "number",
  "readonly": true,
  "longDescription": "The value of this property shall be the interval in seconds between the retry attempts for any given event to the subscription destination.",
  "description": "This represents the number of seconds between retry attempts for sending any given Event"
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EventTypesForSubscription
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Event.v1_0_0.json#/definitions/EventType"
  },
  "longDescription": "The value of this property shall be the types of events that subscriptions can subscribe to.  The semantics associated with the enumerations values are defined in the Redfish specification.",
  "readonly": true,
  "description": "This is the types of Events that can be subscribed to."
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// ServiceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
  "description": "This indicates whether this service is enabled."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Subscriptions
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/EventDestination.json#/definitions/EventDestination"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of EventDestination resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#EventService.SubmitTestEvent** |    |    |
|     } |   |   |
| **DeliveryRetryAttempts** | number | This is the number of attempts an event posting is retried before the subscription is terminated.<br>*read-only* |
| **DeliveryRetryIntervalSeconds** | number | This represents the number of seconds between retry attempts for sending any given Event<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **EventTypesForSubscription** | array | This is the types of Events that can be subscribed to.<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **ServiceEnabled** | boolean, null | This indicates whether this service is enabled.<br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Subscriptions** { | object | A Collection of EventDestination resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |

# JsonSchemaFile 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Languages
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "The value of this property shall be a string consisting of an RFC 5646 language code.",
  "readonly": true,
  "description": "Language codes for the schemas available."
}
```
```json
// Location
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/Location"
  },
  "readonly": true,
  "description": "Location information for this schema file."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Schema
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the value of the @odata.type property for that schema and shall conform to the syntax specified in the Redfish specification for the Type property.",
  "description": "The @odata.type name this schema describes."
}
```

This is the schema definition for the Schema File locator resource.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Languages** | array | Language codes for the schemas available.<br>*read-only* |
| **Location** | array | Location information for this schema file.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Schema** | string | The @odata.type name this schema describes.<br>*read-only* |

# JsonSchemaFileCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/JsonSchemaFile.json#/definitions/JsonSchemaFile"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of JsonSchemaFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# LogEntry 1.0.2


```json
// Created
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the time at which the log entry was created.",
  "format": "date-time",
  "description": "The time the log entry was created."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EntryCode
{
  "anyOf": [
    {
      "$ref": "#/definitions/LogEntryCode"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall be present if the EntryType value is SEL.  These enumerations are the values from table 42-1 and 42-2 of the IPMI specification",
  "description": "If the EntryType is SEL, this will have the entry code for the log entry."
}
```
```json
// EntryType
{
  "type": "string",
  "enum": [
    "Event",
    "SEL",
    "Oem"
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "OriginOfCondition": {
      "longDescription": "The value of this property shall be an href that references the resource for which the log is associated.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/idRef",
      "description": "This is the URI of the resource that caused the log entry"
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Message
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the Message property of the event if the EntryType is Event, the Description if EntryType is SEL and OEM Specific if the EntryType is OEM.",
  "description": "This property decodes from EntryType:  If it is Event then it is a message string.  Otherwise, it is SEL or Oem specific.  In most cases, this will be the actual Log Entry."
}
```
```json
// MessageArgs
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "This contains message arguments to be substituted into the message included or in the message looked up via a registry.",
  "readonly": true,
  "description": "The values of this property shall be any arguments for the message."
}
```
```json
// MessageId
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall the MessageId property of the event if the EntryType is Event, the EventData if EntryType is SEL and OEM Specific if the EntryType is OEM.  The format of this property shall be as defined in the Redfish specification.",
  "description": "This property decodes from EntryType:  If it is Event then it is a message id.  Otherwise, it is SEL or Oem specific.  This value is only used for registries - for more information, see the specification."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OemRecordFormat
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall represent the OEM specific format of the Entry.  This property shall be required if the value of EntryType is Oem",
  "description": "If the entry type is Oem, this will contain more information about the record format from the Oem."
}
```
```json
// SensorNumber
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the EntityInstance from IPMI spec if EntryType is SEL, the count of events if EntryType is Event and OEM Specific if the EntryType is OEM.",
  "description": "This property decodes from EntryType:  If it is SEL, it is the sensor number; if Event then the count of events.  Otherwise, it is Oem specific."
}
```
```json
// SensorType
{
  "anyOf": [
    {
      "$ref": "#/definitions/SensorType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall be present if the EntryType value is SEL.",
  "description": "If the EntryType is SEL, this will have the sensor type that the log entry pertains to."
}
```
```json
// Severity
{
  "anyOf": [
    {
      "$ref": "#/definitions/EventSeverity"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the severity of the condition resulting in the log entry, as defined in the Status section of the Redfish specificaiton.",
  "description": "This is the severity of the log entry."
}
```

This resource defines the record format for a log.  It is designed to be used for SEL logs (from IPMI) as well as Event Logs and OEM-specific log formats.  The EntryType field indicates the type of log and the resource includes several additional properties dependent on the EntryType.

|     |     |     |
| --- | --- | --- |
| **Created** | string | The time the log entry was created.<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **EntryCode** |  | If the EntryType is SEL, this will have the entry code for the log entry.<br>*read-only* |
| **EntryType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**OriginOfCondition** |    |    |
|     } |   |   |
| **Message** | string, null | This property decodes from EntryType:  If it is Event then it is a message string.  Otherwise, it is SEL or Oem specific.  In most cases, this will be the actual Log Entry.<br>*read-only* |
| **MessageArgs** | array | The values of this property shall be any arguments for the message.<br>*read-only* |
| **MessageId** | string | This property decodes from EntryType:  If it is Event then it is a message id.  Otherwise, it is SEL or Oem specific.  This value is only used for registries - for more information, see the specification.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OemRecordFormat** | string, null | If the entry type is Oem, this will contain more information about the record format from the Oem.<br>*read-only* |
| **SensorNumber** | number, null | This property decodes from EntryType:  If it is SEL, it is the sensor number; if Event then the count of events.  Otherwise, it is Oem specific.<br>*read-only* |
| **SensorType** |  | If the EntryType is SEL, this will have the sensor type that the log entry pertains to.<br>*read-only* |
| **Severity** |  | This is the severity of the log entry.<br>*read-only* |

## Property Details

### EntryType:

| string |
| --- |
| Event | 
| SEL | 
| Oem | 


# LogEntryCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/LogEntry.json#/definitions/LogEntry"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of LogEntry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# LogService 1.0.2


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#LogService.ClearLog": {
      "$ref": "#/definitions/ClearLog"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// DateTime
{
  "type": [
    "string",
    "null"
  ],
  "readonly": false,
  "longDescription": "The value of this property shall represent the current DateTime value that the log service is using, with offset from UTC, in Redfish Timestamp format.",
  "format": "date-time",
  "description": "The current DateTime (with offset) for the log service, used to set or read time."
}
```
```json
// DateTimeLocalOffset
{
  "type": [
    "string",
    "null"
  ],
  "readonly": false,
  "longDescription": "The value is property shall represent the offset from UTC time that the current value of DataTime property contains.",
  "pattern": "([-+][0-1][0-9]:[0-5][0-9])",
  "description": "The time offset from UTC that the DateTime property is set to in format: +06:00 ."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Entries
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/LogEntry.json#/definitions/LogEntry"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of LogEntry resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// MaxNumberOfRecords
{
  "type": "number",
  "readonly": true,
  "longDescription": "The value of this property shall be the maximum numbers of LogEntry resources in the Entries collection for this service.",
  "minimum": 0,
  "description": "The maximum number of log entries this service can have."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OverWritePolicy
{
  "type": "string",
  "enum": [
    "Unknown",
    "WrapsWhenFull",
    "NeverOverWrites"
  ],
  "enumDescriptions": {
    "Unknown": "The overwrite policy is not known or is undefined",
    "WrapsWhenFull": "When full, new entries to the Log will overwrite previous entries",
    "NeverOverWrites": "When full, new entries to the Log will be discarded"
  }
}
```
```json
// ServiceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
  "description": "This indicates whether this service is enabled."
}
```
```json
// Status
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    {
      "type": "null"
    }
  ]
}
```

This resource represents the log service for the resource or service to which it is associated.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#LogService.ClearLog** |    |    |
|     } |   |   |
| **DateTime** | string, null | The current DateTime (with offset) for the log service, used to set or read time.<br>*read-write* |
| **DateTimeLocalOffset** | string, null | The time offset from UTC that the DateTime property is set to in format: +06:00 .<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Entries** { | object | A Collection of LogEntry resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **MaxNumberOfRecords** | number | The maximum number of log entries this service can have.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OverWritePolicy** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **ServiceEnabled** | boolean, null | This indicates whether this service is enabled.<br>*read-write* |
| **Status** |  | <br>*read-write* |

## Property Details

### OverWritePolicy:

| string | Description |
| --- | --- |
| Unknown | The overwrite policy is not known or is undefined |
| WrapsWhenFull | When full, new entries to the Log will overwrite previous entries |
| NeverOverWrites | When full, new entries to the Log will be discarded |


# LogServiceCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/LogService.json#/definitions/LogService"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of LogService resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Manager 1.1.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Manager.ForceFailover": {
      "$ref": "#/definitions/ForceFailover"
    },
    "#Manager.Reset": {
      "$ref": "#/definitions/Reset"
    },
    "#Manager.ModifyRedundancySet": {
      "$ref": "#/definitions/ModifyRedundancySet"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// CommandShell
{
  "type": "object",
  "properties": {
    "ConnectTypesSupported": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/CommandConnectTypesSupported"
      },
      "longDescription": "The value of ConnectTypesSupported shall be an array of the enumerations provided here.  SSH shall be included if the Secure Shell (SSH) protocol is supported.  Telnet shall be included if the Telnet protocol is supported.  IPMI shall be included if the IPMI (Serial-over-LAN) protocol is supported.",
      "readonly": true,
      "description": "This object is used to enumerate the Command Shell connection types allowed by the implementation."
    },
    "MaxConcurrentSessions": {
      "type": "number",
      "readonly": true,
      "longDescription": "The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation.",
      "minimum": 0,
      "description": "Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support."
    },
    "ServiceEnabled": {
      "type": "boolean",
      "longDescription": "The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the service is enabled for this manager."
    }
  },
  "description": "Used for describing services like Serial Console, Command Shell or Graphical Console",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// DateTime
{
  "type": [
    "string",
    "null"
  ],
  "readonly": false,
  "longDescription": "The value of this property shall represent the current DateTime value for the manager, with offset from UTC, in Redfish Timestamp format.",
  "format": "date-time",
  "description": "The current DateTime (with offset) for the manager, used to set or read time."
}
```
```json
// DateTimeLocalOffset
{
  "type": [
    "string",
    "null"
  ],
  "readonly": false,
  "longDescription": "The value is property shall represent the offset from UTC time that the current value of DataTime property contains.",
  "pattern": "([-+][0-1][0-9]:[0-5][0-9])",
  "description": "The time offset from UTC that the DateTime property is set to in format: +06:00 ."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EthernetInterfaces
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/EthernetInterface.json#/definitions/EthernetInterface"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of EthernetInterface resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// FirmwareVersion
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the firwmare version as defined by the manufacturer for the associated manager.",
  "description": "The firmware version of this Manager"
}
```
```json
// GraphicalConsole
{
  "type": "object",
  "properties": {
    "ConnectTypesSupported": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/GraphicalConnectTypesSupported"
      },
      "longDescription": "The value of ConnectTypesSupported shall be an array of the enumerations provided here.  RDP shall be included if the Remote Desktop (RDP) protocol is supported.  KVMIP shall be included if a vendor-define KVM-IP protocol is supported.",
      "readonly": true,
      "description": "This object is used to enumerate the Graphical Console connection types allowed by the implementation."
    },
    "MaxConcurrentSessions": {
      "type": "number",
      "readonly": true,
      "longDescription": "The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation.",
      "minimum": 0,
      "description": "Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support."
    },
    "ServiceEnabled": {
      "type": "boolean",
      "longDescription": "The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the service is enabled for this manager."
    }
  },
  "description": "Used for describing services like Serial Console, Command Shell or Graphical Console",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Links
{
  "properties": {
    "ManagerInChassis": {
      "longDescription": "This property shall contain a reference to the chassis that this manager is located in.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis",
      "description": "This property is a reference to the chassis that this manager is located in."
    },
    "ManagerForServers@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "ManagerForServers@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagerForChassis@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "ManagerForChassis@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "ManagerForServers": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/ComputerSystem.json#/definitions/ComputerSystem"
      },
      "longDescription": "This property shall contain an array of references to ComputerSystem resources of which this Manager instance has control.",
      "readonly": true,
      "description": "This property is an array of references to the systems that this manager has control over."
    },
    "ManagerForChassis": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
      },
      "longDescription": "This property shall contain an array of references to Chassis resources of which this Manager instance has control.",
      "readonly": true,
      "description": "This property is an array of references to the chassis that this manager has control over."
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// LogServices
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/LogService.json#/definitions/LogService"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of LogService resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// ManagerType
{
  "type": "string",
  "enum": [
    "ManagementController",
    "EnclosureManager",
    "BMC",
    "RackManager",
    "AuxiliaryController"
  ],
  "enumDescriptions": {
    "RackManager": "A controller which provides management functions for a whole or part of a rack",
    "BMC": "A controller which provides management functions for a single computer system",
    "EnclosureManager": "A controller which provides management functions for a chassis or group of devices or systems",
    "ManagementController": "A controller used primarily to monitor or manage the operation of a device or system",
    "AuxiliaryController": "A controller which provides management functions for a particular subsystem or group of devices"
  }
}
```
```json
// Model
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the information about how the manufacturer references this manager.",
  "description": "The model information of this Manager as defined by the manufacturer"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// NetworkProtocol
{
  "properties": {
    "FQDN": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall contain the fully qualified domain name for the manager.",
      "description": "This is the fully qualified domain name for the manager obtained by DNS including the host name and top-level domain name."
    },
    "HTTPS": {
      "longDescription": "This object shall contain information for the HTTPS/SSL protocol settings for this manager. The default value of the Port property should be 443 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's HTTPS protocol support"
    },
    "VirtualMedia": {
      "longDescription": "This object shall contain information for the Virtual Media protocol settings for this manager. The value of the Port property shall contain the TCP port assigned for Virtual Media usage.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's Virtual Media support"
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "IPMI": {
      "longDescription": "This object shall contain information for the IPMI over LAN protocol settings for the manager. The default value of the Port property should be 623 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's IPMI-over-LAN protocol support"
    },
    "SSDP": {
      "longDescription": "This object shall contain information for the SSDP protocol settings for this manager.  Simple Service Discovery Protocol (SSDP) is for network discovery of devices supporting the Redfish service. The default value of the Port property should be 1900 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/SSDProtocol",
      "description": "Settings for this Manager's SSDP support"
    },
    "SNMP": {
      "longDescription": "This object shall contain information for the SNMP protocol settings for this manager. The default value of the Port property should be 161 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's SNMP support"
    },
    "KVMIP": {
      "longDescription": "This object shall contain information for the KVM-IP (Keyboard, Video, Mouse) protocol settings for the manager.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's KVM-IP protocol support"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "SSH": {
      "longDescription": "This object shall contain information for the SSH protocol settings for the manager. The default value of the Port property should be 22 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's SSH (Secure Shell) protocol support"
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "HostName": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall contain the host name without any domain information.",
      "description": "The DNS Host Name of this manager, without any domain information"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    },
    "Telnet": {
      "longDescription": "This object shall contain information for the Telnet protocol settings for this manager. The default value of the Port property should be 23 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's Telnet protocol support"
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "HTTP": {
      "longDescription": "This object shall contain information for the HTTP protocol settings for the manager. The default value of the Port property should be 80 for compatibility with established client implementations.",
      "readonly": false,
      "$ref": "#/definitions/Protocol",
      "description": "Settings for this Manager's HTTP protocol support"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This object shall be used to represent the network service settings for the manager.",
  "type": "object",
  "description": "This resource is used to obtain or modify the network services managed by a given manager.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Redundancy
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
  },
  "readonly": true,
  "description": "Redundancy information for the managers of this system"
}
```
```json
// Redundancy@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// SerialConsole
{
  "type": "object",
  "properties": {
    "ConnectTypesSupported": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/SerialConnectTypesSupported"
      },
      "longDescription": "The value of ConnectTypesSupported shall be an array of the enumerations provided here.  SSH shall be included if the Secure Shell (SSH) protocol is supported.  Telnet shall be included if the Telnet protocol is supported.  IPMI shall be included if the IPMI (Serial-over-LAN) protocol is supported.",
      "readonly": true,
      "description": "This object is used to enumerate the Serial Console connection types allowed by the implementation."
    },
    "MaxConcurrentSessions": {
      "type": "number",
      "readonly": true,
      "longDescription": "The value of this property shall contain the maximum number of concurrent service sessions supported by the implementation.",
      "minimum": 0,
      "description": "Indicates the maximum number of service sessions, regardless of protocol, this manager is able to support."
    },
    "ServiceEnabled": {
      "type": "boolean",
      "longDescription": "The value of this property shall contain the enabled status of the protocol used for the service.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the service is enabled for this manager."
    }
  },
  "description": "Used for describing services like Serial Console, Command Shell or Graphical Console",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SerialInterfaces
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/SerialInterface.json#/definitions/SerialInterface"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of SerialInterface resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// ServiceEntryPointUUID
{
  "type": "string",
  "pattern": "([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})"
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// UUID
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/UUID"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the universal unique identifier number for the manager.",
  "description": "The Universal Unique Identifier (UUID) for this Manager"
}
```
```json
// VirtualMedia
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/VirtualMedia.json#/definitions/VirtualMedia"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of VirtualMedia resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

This is the schema definition for a Manager.  Examples of managers are BMCs, Enclosure Managers, Management Controllers and other subsystems assigned managability functions.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ForceFailover** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.Reset** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Manager.ModifyRedundancySet** |    |    |
|     } |   |   |
| **CommandShell** { | object | Used for describing services like Serial Console, Command Shell or Graphical Console<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
|     } |   |   |
| **DateTime** | string, null | The current DateTime (with offset) for the manager, used to set or read time.<br>*read-write* |
| **DateTimeLocalOffset** | string, null | The time offset from UTC that the DateTime property is set to in format: +06:00 .<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **EthernetInterfaces** { | object | A Collection of EthernetInterface resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **FirmwareVersion** | string, null | The firmware version of this Manager<br>*read-only* |
| **GraphicalConsole** { | object | Used for describing services like Serial Console, Command Shell or Graphical Console<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
|     } |   |   |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerInChassis** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForServers** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ManagerForChassis** |    |    |
|     } |   |   |
| **LogServices** { | object | A Collection of LogService resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **ManagerType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **Model** | string, null | The model information of this Manager as defined by the manufacturer<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **NetworkProtocol** { | object | This resource is used to obtain or modify the network services managed by a given manager.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**FQDN** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HTTPS** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VirtualMedia** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IPMI** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SSDP** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SNMP** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**KVMIP** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SSH** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HostName** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Telnet** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HTTP** |    |    |
|     } |   |   |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Redundancy** | array | Redundancy information for the managers of this system<br>*read-only* |
| **Redundancy@odata.navigationLink** | string | <br>*read-write* |
| **SerialConsole** { | object | Used for describing services like Serial Console, Command Shell or Graphical Console<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ConnectTypesSupported** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxConcurrentSessions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
|     } |   |   |
| **SerialInterfaces** { | object | A Collection of SerialInterface resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **ServiceEntryPointUUID** | string | <br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **UUID** |  | The Universal Unique Identifier (UUID) for this Manager<br>*read-only* |
| **VirtualMedia** { | object | A Collection of VirtualMedia resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |

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


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Enabled
{
  "type": "boolean",
  "longDescription": "This property shall enable (if set to true) or disable (if set to false) the account for future logins. The value of Enable over-rides the locked property.",
  "description": "This property is used by a User Administrator to disable an account w/o having to delet the user information.  When set to true, the user can login.  When set to false, the account is administratively disabled and the user cannot login."
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "Role": {
      "longDescription": "The value of this property shall be a link to a Role object instance, and should reference the object identified by property RoleId.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/Role.json#/definitions/Role",
      "description": "A reference to the Role object defining Privileges for this account--returned when the resource is read. The ID of the role is the same as property RoleId."
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Locked
{
  "type": "boolean",
  "longDescription": "This property (when set to true) shall indicate that the account service has automatically locked the account due to the accountLockoutThreshold having been exceeded. If set to true, the account is locked.  If set to false, the account is not locked.  A user admin shall be able to write a false to the property to clear the lockout condition, prior to the lockout duration period.",
  "description": "This property indicates that the account has been auto-locked by the account service because the lockout threshold has been exceeded.  When set to true, the account is locked. A user admin can write the property to false to manually unlock, or the account service will unlock it once the lockout duration period has passed."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Password
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be the password for this account.  The value shall be null for GET requests.",
  "description": "This property is used with a PATCH or PUT to write the password for the account.  This property is null on a GET."
}
```
```json
// RoleId
{
  "type": "string",
  "longDescription": "The value of this property shall be the ID of the Role resource that configured for this account.",
  "description": "This property contains the Role for this account."
}
```
```json
// UserName
{
  "type": "string",
  "longDescription": "The value of this property shall be the user name for this account.",
  "description": "This property contains the user name for the account."
}
```

The user accounts, owned by a Manager, are defined in this resource.  Changes to a Manager Account may affect the current Redfish service connection if this manager is responsible for the Redfish service.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Enabled** | boolean | This property is used by a User Administrator to disable an account w/o having to delet the user information.  When set to true, the user can login.  When set to false, the account is administratively disabled and the user cannot login.<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Role** |    |    |
|     } |   |   |
| **Locked** | boolean | This property indicates that the account has been auto-locked by the account service because the lockout threshold has been exceeded.  When set to true, the account is locked. A user admin can write the property to false to manually unlock, or the account service will unlock it once the lockout duration period has passed.<br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Password** | string, null | This property is used with a PATCH or PUT to write the password for the account.  This property is null on a GET.<br>*read-write* |
| **RoleId** | string | This property contains the Role for this account.<br>*read-write* |
| **UserName** | string | This property contains the user name for the account.<br>*read-write* |

# ManagerAccountCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/ManagerAccount.json#/definitions/ManagerAccount"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of ManagerAccount resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# ManagerCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Manager.json#/definitions/Manager"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Manager resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# ManagerNetworkProtocol 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// FQDN
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the fully qualified domain name for the manager.",
  "description": "This is the fully qualified domain name for the manager obtained by DNS including the host name and top-level domain name."
}
```
```json
// HTTP
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// HTTPS
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// HostName
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall contain the host name without any domain information.",
  "description": "The DNS Host Name of this manager, without any domain information"
}
```
```json
// IPMI
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// KVMIP
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// SNMP
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SSDP
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "NotifyIPv6Scope": {
      "anyOf": [
        {
          "$ref": "#/definitions/NotifyIPv6Scope"
        },
        {
          "type": "null"
        }
      ],
      "longDescription": "The value of this property shall contain the IPv6 scope used for multicast NOTIFY messages.  The valid enumerations are a subset of the available IPv6 Scope types.",
      "description": "Indicates the scope for the IPv6 Notify messages for SSDP."
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    },
    "NotifyTTL": {
      "type": [
        "number",
        "null"
      ],
      "longDescription": "The value of this property shall contain the Time-To-Live hop count used for multicast NOTIFY messages.  The recommended value is 2.",
      "minimum": 1,
      "description": "Indicates the time to live hop count for SSDPs Notify messages."
    },
    "NotifyMulticastIntervalSeconds": {
      "type": [
        "number",
        "null"
      ],
      "longDescription": "The value of this property shall contain the time interval, in seconds, between transmissions of the multicast NOTIFY ALIVE message.  A setting of 0 seconds shall disable this functionality.  The recommended value is 600 seconds.",
      "minimum": 0,
      "description": "Indicates how often the Multicast is done from this service for SSDP."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SSH
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Telnet
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// VirtualMedia
{
  "type": "object",
  "properties": {
    "ProtocolEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the enabled status of the protocol.  The value shall be true if enabled and false if disabled.",
      "description": "Indicates if the protocol is enabled or disabled"
    },
    "Port": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "The value of this property shall contain the port assigned for the protocol.",
      "minimum": 0,
      "description": "Indicates the protocol port."
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

This resource is used to obtain or modify the network services managed by a given manager.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **FQDN** | string, null | This is the fully qualified domain name for the manager obtained by DNS including the host name and top-level domain name.<br>*read-only* |
| **HTTP** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **HTTPS** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **HostName** | string, null | The DNS Host Name of this manager, without any domain information<br>*read-only* |
| **IPMI** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **KVMIP** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **SNMP** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **SSDP** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyIPv6Scope** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyTTL** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**NotifyMulticastIntervalSeconds** |    |    |
|     } |   |   |
| **SSH** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Telnet** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |
| **VirtualMedia** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ProtocolEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Port** |    |    |
|     } |   |   |

# Memory 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Memory.DisablePassphrase": {
      "$ref": "#/definitions/DisablePassphrase"
    },
    "#Memory.UnlockUnit": {
      "$ref": "#/definitions/UnlockUnit"
    },
    "#Memory.SetPassphrase": {
      "$ref": "#/definitions/SetPassphrase"
    },
    "#Memory.SecureEraseUnit": {
      "$ref": "#/definitions/SecureEraseUnit"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// AllowedSpeedsMHz
{
  "type": "array",
  "items": {
    "type": "number"
  },
  "longDescription": "The value of this property shall be the speed supported by this Memory.",
  "readonly": true,
  "description": "Speed bins supported by this Memory"
}
```
```json
// BaseModuleType
{
  "anyOf": [
    {
      "$ref": "#/definitions/BaseModuleType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the base module type of Memory",
  "description": "The base module type of Memory"
}
```
```json
// BusWidthBits
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the bus width in bits.",
  "description": "Bus Width in bits."
}
```
```json
// CapacityMiB
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the Memory capacity in MiB.",
  "description": "Memory Capacity in MiB."
}
```
```json
// DataWidthBits
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the data width in bits.",
  "description": "Data Width in bits."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// DeviceID
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the device ID of the Memory.",
  "description": "Device ID"
}
```
```json
// DeviceLocator
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be location of the Memory in the platform, typically marked in the silk screen.",
  "description": "Location of the Memory in the platform"
}
```
```json
// ErrorCorrection
{
  "anyOf": [
    {
      "$ref": "#/definitions/ErrorCorrection"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the error correction scheme supported for this memory.",
  "description": "Error correction scheme supported for this memory"
}
```
```json
// FirmwareApiVersion
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the version of API supported by the firmware.",
  "description": "Version of API supported by the firmware"
}
```
```json
// FirmwareRevision
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the revision of firmware on the Memory controller.",
  "description": "Revision of firmware on the Memory controller"
}
```
```json
// FunctionClasses
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "The value of this property shall be the function classes by the Memory.",
  "readonly": true,
  "description": "Function Classes by the Memory"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// IsRankSpareEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be true if a rank spare is enabled for this Memory.",
  "description": "Rank spare enabled status"
}
```
```json
// IsSpareDeviceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be true if a spare device is enabled for this Memory.",
  "description": "Spare device enabled status"
}
```
```json
// Manufacturer
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain a string which identifies the manufacturer of the Memory.",
  "description": "The Memory manufacturer"
}
```
```json
// MaxTDPMilliWatts
{
  "type": "array",
  "items": {
    "type": "number"
  },
  "longDescription": "The value of this property shall be the maximum power budgets supported by the Memory in milli Watts.",
  "readonly": true,
  "description": "Maximum TDPs in milli Watts"
}
```
```json
// MemoryDeviceType
{
  "anyOf": [
    {
      "$ref": "#/definitions/MemoryDeviceType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the Memory Device Type as defined by SMBIOS.",
  "description": "Type details of the Memory"
}
```
```json
// MemoryLocation
{
  "type": "object",
  "properties": {
    "Channel": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Channel number in which Memory is connected.",
      "description": "Channel number in which Memory is connected"
    },
    "Slot": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Slot number in which Memory is connected.",
      "description": "Slot number in which Memory is connected"
    },
    "MemoryController": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Memory controller number in which Memory is connected.",
      "description": "Memory controller number in which Memory is connected"
    },
    "Socket": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Socket number in which Memory is connected.",
      "description": "Socket number in which Memory is connected"
    }
  },
  "description": ".",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// MemoryMedia
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/MemoryMedia"
  },
  "longDescription": "The value of this property shall be the media types of this Memory",
  "readonly": true,
  "description": "Media  of this Memory"
}
```
```json
// MemoryType
{
  "anyOf": [
    {
      "$ref": "#/definitions/MemoryType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the type of Memory represented by this resource.",
  "description": "The type of Memory"
}
```
```json
// Metrics
{
  "properties": {
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "CurrentPeriod": {
      "longDescription": "This object shall contain properties which describe the CurrentPeriod metrics for the current resource.",
      "$ref": "#/definitions/CurrentPeriod",
      "description": "This object describes the central memory of the system in general detail."
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "HealthData": {
      "longDescription": "This object shall contain properties which describe the HealthData metrics for the current resource.",
      "$ref": "#/definitions/HealthData",
      "description": "This object describes the central memory of the system in general detail."
    },
    "LifeTime": {
      "longDescription": "This object shall contain properties which describe the LifeTime metrics for the current resource.",
      "$ref": "#/definitions/LifeTime",
      "description": "This object describes the central memory of the system in general detail."
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "BlockSizeBytes": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be the block size in bytes of all stucture elements.",
      "description": "Block size in bytes"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "Actions": {
      "properties": {
        "Oem": {
          "type": "object",
          "properties": {},
          "additionalProperties": true,
          "patternProperties": {
            "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
              "type": [
                "array",
                "boolean",
                "number",
                "null",
                "object",
                "string"
              ],
              "description": "This property shall specify a valid odata or Redfish property."
            }
          }
        },
        "#MemoryMetrics.ClearCurrentPeriod": {
          "$ref": "#/definitions/ClearCurrentPeriod"
        }
      },
      "readonly": true,
      "longDescription": "The Actions property shall contain the available actions for this resource.",
      "type": "object",
      "description": "The available actions for this resource.",
      "additionalProperties": false,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent the Memory Metrics for a single Memory device in a Redfish implementation.",
  "type": "object",
  "description": "MemoryMetrics contains usage and health statistics for a single Memory module or device instance.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OperatingMemoryModes
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/OperatingMemoryModes"
  },
  "longDescription": "The value of this property shall be the memory modes supported by the Memory.",
  "readonly": true,
  "description": "Memory modes supported by the Memory"
}
```
```json
// OperatingSpeedMhz
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the operating speed of Memory in MHz.",
  "description": "Operating speed of Memory in MHz"
}
```
```json
// PartNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the part number as provided by the manufacturer of this Memory.",
  "description": "The product part number of this device"
}
```
```json
// PersistentRegionSizeLimitMiB
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the total size of persistent regions in MiB.",
  "description": "Total size of persistent regions in MiB"
}
```
```json
// PowerManagementPolicy
{
  "type": "object",
  "properties": {
    "MaxTDPMilliWatts": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Maximum TDP in milli watts.",
      "description": "Maximum TDP in milli watts"
    },
    "PeakPowerBudgetMilliWatts": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Peak power budget in milli watts.",
      "description": "Peak power budget in milli watts"
    },
    "PolicyEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": true,
      "longDescription": "Power management policy enabled status.",
      "description": "Power management policy enabled status"
    },
    "AveragePowerBudgetMilliWatts": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Average power budget in milli watts.",
      "description": "Average power budget in milli watts"
    }
  },
  "description": ".",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// RankCount
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be number of ranks available in the Memory. The ranks could be used for spare or interleave.",
  "description": "Number of ranks available in the Memory"
}
```
```json
// Regions
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/RegionSet"
  },
  "longDescription": "The value of this property shall be the memory region information within the Memory.",
  "readonly": true,
  "description": "Memory regions information within the Memory"
}
```
```json
// SecurityCapabilities
{
  "type": "object",
  "properties": {
    "SecurityStates": {
      "type": "array",
      "items": {
        "$ref": "#/definitions/SecurityStates"
      },
      "longDescription": "Security states supported by the Memory.",
      "readonly": true,
      "description": "Security states supported by the Memory"
    },
    "MaxPassphraseCount": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "Maximum number of passphrases supported for this Memory.",
      "description": "Maximum number of passphrases supported for this Memory"
    },
    "PassphraseCapable": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": true,
      "longDescription": "Memory passphrase set capability.",
      "description": "Memory passphrase set capability"
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SerialNumber
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the serial number as provided by the manufacturer of this Memory.",
  "description": "The product serial number of this device"
}
```
```json
// SpareDeviceCount
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the number of unused spare devices available in the Memory. If memory devices fails, the spare device could be used.",
  "description": "Number of unused spare devices available in the Memory"
}
```
```json
// SubsystemDeviceID
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the subsystem Device ID of the Memory.",
  "description": "Subsystem Device ID"
}
```
```json
// SubsystemVendorID
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the subsystem Vendor ID of the Memory.",
  "description": "SubSystem Vendor ID"
}
```
```json
// VendorID
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the vendor ID of the Memory.",
  "description": "Vendor ID"
}
```
```json
// VolatileRegionSizeLimitMiB
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the total size of volatile regions in MiB.",
  "description": "Total size of volatile regions in MiB"
}
```

This is the schema definition for definition of a Memory and its configuration

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.DisablePassphrase** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.UnlockUnit** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SetPassphrase** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Memory.SecureEraseUnit** |    |    |
|     } |   |   |
| **AllowedSpeedsMHz** | array | Speed bins supported by this Memory<br>*read-only* |
| **BaseModuleType** |  | The base module type of Memory<br>*read-only* |
| **BusWidthBits** | number, null | Bus Width in bits.<br>*read-only* |
| **CapacityMiB** | number, null | Memory Capacity in MiB.<br>*read-only* |
| **DataWidthBits** | number, null | Data Width in bits.<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **DeviceID** | string, null | Device ID<br>*read-only* |
| **DeviceLocator** | string, null | Location of the Memory in the platform<br>*read-only* |
| **ErrorCorrection** |  | Error correction scheme supported for this memory<br>*read-only* |
| **FirmwareApiVersion** | string, null | Version of API supported by the firmware<br>*read-only* |
| **FirmwareRevision** | string, null | Revision of firmware on the Memory controller<br>*read-only* |
| **FunctionClasses** | array | Function Classes by the Memory<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **IsRankSpareEnabled** | boolean, null | Rank spare enabled status<br>*read-only* |
| **IsSpareDeviceEnabled** | boolean, null | Spare device enabled status<br>*read-only* |
| **Manufacturer** | string, null | The Memory manufacturer<br>*read-only* |
| **MaxTDPMilliWatts** | array | Maximum TDPs in milli Watts<br>*read-only* |
| **MemoryDeviceType** |  | Type details of the Memory<br>*read-only* |
| **MemoryLocation** { | object | .<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Channel** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Slot** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MemoryController** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Socket** |    |    |
|     } |   |   |
| **MemoryMedia** | array | Media  of this Memory<br>*read-only* |
| **MemoryType** |  | The type of Memory<br>*read-only* |
| **Metrics** { | object | MemoryMetrics contains usage and health statistics for a single Memory module or device instance.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CurrentPeriod** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthData** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LifeTime** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlockSizeBytes** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OperatingMemoryModes** | array | Memory modes supported by the Memory<br>*read-only* |
| **OperatingSpeedMhz** | number, null | Operating speed of Memory in MHz<br>*read-only* |
| **PartNumber** | string, null | The product part number of this device<br>*read-only* |
| **PersistentRegionSizeLimitMiB** | number, null | Total size of persistent regions in MiB<br>*read-only* |
| **PowerManagementPolicy** { | object | .<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxTDPMilliWatts** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PeakPowerBudgetMilliWatts** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PolicyEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AveragePowerBudgetMilliWatts** |    |    |
|     } |   |   |
| **RankCount** | number, null | Number of ranks available in the Memory<br>*read-only* |
| **Regions** | array | Memory regions information within the Memory<br>*read-only* |
| **SecurityCapabilities** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SecurityStates** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPassphraseCount** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PassphraseCapable** |    |    |
|     } |   |   |
| **SerialNumber** | string, null | The product serial number of this device<br>*read-only* |
| **SpareDeviceCount** | number, null | Number of unused spare devices available in the Memory<br>*read-only* |
| **SubsystemDeviceID** | string, null | Subsystem Device ID<br>*read-only* |
| **SubsystemVendorID** | string, null | SubSystem Vendor ID<br>*read-only* |
| **VendorID** | string, null | Vendor ID<br>*read-only* |
| **VolatileRegionSizeLimitMiB** | number, null | Total size of volatile regions in MiB<br>*read-only* |

# MemoryCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Memory.json#/definitions/Memory"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Memory resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# MemoryMetrics 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#MemoryMetrics.ClearCurrentPeriod": {
      "$ref": "#/definitions/ClearCurrentPeriod"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// BlockSizeBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the block size in bytes of all stucture elements.",
  "description": "Block size in bytes"
}
```
```json
// CurrentPeriod
{
  "type": "object",
  "properties": {
    "BlocksWritten": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be mumber of blocks written since reset.",
      "description": "Number of blocks written since reset"
    },
    "BlocksRead": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be number of blocks read since reset.",
      "description": "Number of blocks read since reset"
    }
  },
  "description": "This object contains the Memory metrics since last reset or ClearCurrentPeriod action.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// HealthData
{
  "type": "object",
  "properties": {
    "PerformanceDegraded": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be verformance degraded mode status, with true indicating perfomance degraded.",
      "description": "Performance degraded mode status"
    },
    "RemainingSpareBlockPercentage": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be the remaining spare blocks in percentage.",
      "description": "Remaining spare blocks in percentage"
    },
    "DataLossDetected": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be data loss detection status, with true indicating data loss detected.",
      "description": "Data loss detection status"
    },
    "AlarmTrips": {
      "longDescription": "This object shall contain properties describe the types of alarms that have been raised by the memory.",
      "readonly": true,
      "$ref": "#/definitions/AlarmTrips",
      "description": "Alarm trip information about the memory"
    },
    "LastShutdownSuccess": {
      "type": [
        "boolean",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be the status ofthe  last shutdown, with true indicating success.",
      "description": "Status of last shutdown"
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// LifeTime
{
  "type": "object",
  "properties": {
    "BlocksWritten": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be number of blocks written for the lifetime of the Memory.",
      "description": "Number of blocks written for the lifetime of the Memory"
    },
    "BlocksRead": {
      "type": [
        "number",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall be number of blocks read for the lifetime of the Memory.",
      "description": "Number of blocks read for the lifetime of the Memory"
    }
  },
  "description": "This objects contains the Memory metrics for the lifetime of the Memory.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

MemoryMetrics contains usage and health statistics for a single Memory module or device instance.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#MemoryMetrics.ClearCurrentPeriod** |    |    |
|     } |   |   |
| **BlockSizeBytes** | number, null | Block size in bytes<br>*read-only* |
| **CurrentPeriod** { | object | This object contains the Memory metrics since last reset or ClearCurrentPeriod action.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** |    |    |
|     } |   |   |
| **Description** |  | <br>*read-write* |
| **HealthData** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**PerformanceDegraded** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**RemainingSpareBlockPercentage** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DataLossDetected** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AlarmTrips** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LastShutdownSuccess** |    |    |
|     } |   |   |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **LifeTime** { | object | This objects contains the Memory metrics for the lifetime of the Memory.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksWritten** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**BlocksRead** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# MessageRegistry 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Language
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be a string consisting of an RFC 5646 language code",
  "description": "This is the RFC 5646 compliant language code for the registry."
}
```
```json
// Messages
{
  "type": "object",
  "properties": {},
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9]+": {
      "$ref": "#/definitions/Message"
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OwningEntity
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be a string that represents the publisher of this registry.",
  "description": "This is the organization or company that publishes this registry."
}
```
```json
// RegistryPrefix
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the prefix used in messageIDs which uniquely identifies all of the messages in this registry as belonging to this registry.",
  "description": "This is the single word prefix used to form a messageID structure."
}
```
```json
// RegistryVersion
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the version of this message registry.   The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification",
  "description": "This is the message registry version which is used in the middle portion of a messageID."
}
```

This is the schema definition for all Message Registries.  It represents the properties for the registries themselves.  The MessageId is formed per the Redfish specification.  It consists of the RegistryPrefix concatenated with the version concatenated with the unique identifier for the message registry entry.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Language** | string | This is the RFC 5646 compliant language code for the registry.<br>*read-only* |
| **Messages** {} | object | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OwningEntity** | string | This is the organization or company that publishes this registry.<br>*read-only* |
| **RegistryPrefix** | string | This is the single word prefix used to form a messageID structure.<br>*read-only* |
| **RegistryVersion** | string | This is the message registry version which is used in the middle portion of a messageID.<br>*read-only* |

# MessageRegistryCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/MessageRegistry.json#/definitions/MessageRegistry"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of MessageRegistry resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# MessageRegistryFile 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Languages
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "The value of this property shall be a string consisting of an RFC 5646 language code.",
  "readonly": true,
  "description": "Language codes for the schemas available."
}
```
```json
// Location
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/Location"
  },
  "readonly": true,
  "description": "Location information for this schema file."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Registry
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall be the value of the Registry Name, Major and Minor version and shall conform to the syntax specified in the Redfish specification for the MessageId property without the MessageKey.",
  "description": "The Registry Name, Major and Minor version used in MessageID construction."
}
```

This is the schema definition for the Schema File locator resource.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Languages** | array | Language codes for the schemas available.<br>*read-only* |
| **Location** | array | Location information for this schema file.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Registry** | string | The Registry Name, Major and Minor version used in MessageID construction.<br>*read-only* |

# MessageRegistryFileCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/MessageRegistryFile.json#/definitions/MessageRegistryFile"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of MessageRegistryFile resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Power 1.1.0


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// PowerControl
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/PowerControl"
  },
  "longDescription": "These properties shall be the definition for power control (power reading and limiting) for a Redfish implementation.",
  "readonly": false,
  "description": "This is the definition for power control function (power reading/limiting)."
}
```
```json
// PowerControl@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// PowerSupplies
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Power.v1_0_0.json#/definitions/PowerSupply"
  },
  "longDescription": "This object shall contain details of the power supplies associated with this system or device",
  "readonly": false,
  "description": "Details of the power supplies associated with this system or device"
}
```
```json
// PowerSupplies@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Redundancy
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
  },
  "readonly": true,
  "description": "Redundancy information for the power subsystem of this system or device"
}
```
```json
// Redundancy@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Voltages
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/Voltage"
  },
  "longDescription": "These properties shall be the definition for voltage sensors for a Redfish implementation.",
  "readonly": false,
  "description": "This is the definition for voltage sensors."
}
```
```json
// Voltages@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```

This is the schema definition for the Power Metrics.  It represents the properties for Power Consumption and Power Limiting.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **PowerControl** | array | This is the definition for power control function (power reading/limiting).<br>*read-write* |
| **PowerControl@odata.navigationLink** | string | <br>*read-write* |
| **PowerSupplies** | array | Details of the power supplies associated with this system or device<br>*read-write* |
| **PowerSupplies@odata.navigationLink** | string | <br>*read-write* |
| **Redundancy** | array | Redundancy information for the power subsystem of this system or device<br>*read-only* |
| **Redundancy@odata.navigationLink** | string | <br>*read-write* |
| **Voltages** | array | This is the definition for voltage sensors.<br>*read-write* |
| **Voltages@odata.navigationLink** | string | <br>*read-write* |

# Processor 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// InstructionSet
{
  "anyOf": [
    {
      "$ref": "#/definitions/InstructionSet"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the string which identifies the instruction set of the processor contained in this socket.",
  "description": "The instruction set of the processor"
}
```
```json
// Manufacturer
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain a string which identifies the manufacturer of the processor.",
  "description": "The processor manufacturer"
}
```
```json
// MaxSpeedMHz
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the maximum rated clock speed of the processor in MHz.",
  "description": "The maximum clock speed of the processor"
}
```
```json
// Model
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the model information as provided by the manufacturer of this processor.",
  "description": "The product model number of this device"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// ProcessorArchitecture
{
  "anyOf": [
    {
      "$ref": "#/definitions/ProcessorArchitecture"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the string which identifies the architecture of the processor contained in this Socket.",
  "description": "The architecture of the processor"
}
```
```json
// ProcessorId
{
  "type": "object",
  "properties": {
    "Step": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall indicate the Step or revision string information as provided by the manufacturer of this processor.",
      "description": "The Step value for this processor"
    },
    "EffectiveFamily": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall indicate the effective Family information as provided by the manufacturer of this processor.",
      "description": "The effective Family for this processor"
    },
    "VendorId": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall indicate the Vendor Identification string information as provided by the manufacturer of this processor.",
      "description": "The Vendor Identification for this processor"
    },
    "IdentificationRegisters": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall include the raw CPUID instruction output as provided by the manufacturer of this processor.",
      "description": "The contents of the Identification Registers (CPUID) for this processor"
    },
    "MicrocodeInfo": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall indicate the Microcode Information as provided by the manufacturer of this processor.",
      "description": "The Microcode Information for this processor"
    },
    "EffectiveModel": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "This property shall indicate the effective Model information as provided by the manufacturer of this processor.",
      "description": "The effective Model for this processor"
    }
  },
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// ProcessorType
{
  "anyOf": [
    {
      "$ref": "#/definitions/ProcessorType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the string which identifies the type of processor contained in this Socket.",
  "description": "The type of processor"
}
```
```json
// Socket
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the string which identifies the physical location or socket of the processor.",
  "description": "The socket or location of the processor"
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// TotalCores
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the total count of independent processor cores contained within this processor.",
  "description": "The total number of cores contained in this processor"
}
```
```json
// TotalThreads
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the total count of independent execution threads supported by this processor.",
  "description": "The total number of execution threads supported by this processor"
}
```

This is the schema definition for the Processor resource.  It represents the properties of a processor attached to a System.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **InstructionSet** |  | The instruction set of the processor<br>*read-only* |
| **Manufacturer** | string, null | The processor manufacturer<br>*read-only* |
| **MaxSpeedMHz** | number, null | The maximum clock speed of the processor<br>*read-only* |
| **Model** | string, null | The product model number of this device<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **ProcessorArchitecture** |  | The architecture of the processor<br>*read-only* |
| **ProcessorId** { | object | <br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Step** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveFamily** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**VendorId** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**IdentificationRegisters** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MicrocodeInfo** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EffectiveModel** |    |    |
|     } |   |   |
| **ProcessorType** |  | The type of processor<br>*read-only* |
| **Socket** | string, null | The socket or location of the processor<br>*read-only* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **TotalCores** | number, null | The total number of cores contained in this processor<br>*read-only* |
| **TotalThreads** | number, null | The total number of execution threads supported by this processor<br>*read-only* |

# ProcessorCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Processor.json#/definitions/Processor"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Processor resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Role 1.0.2


```json
// AssignedPrivileges
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Privileges.v1_0_0.json#/definitions/PrivilegeType"
  },
  "longDescription": "The value of this property shall be the redfish privileges that the role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property.",
  "readonly": false,
  "description": "The redfish privileges that this role includes."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// IsPredefined
{
  "type": "boolean",
  "readonly": true,
  "longDescription": "The value of this property shall indicate if the role is a predefined role. .",
  "description": "This property is used to indicate if the Role is one of the Redfish Predefined Roles vs a Custom role."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// OemPrivileges
{
  "type": "array",
  "items": {
    "type": "string"
  },
  "longDescription": "The value of this property shall be the OEM privileges that this role includes. For pre-defined roles, this property shall be readOnly. For custom roles some implementations may not allow writing this property.",
  "readonly": false,
  "description": "The OEM privileges that this role includes."
}
```

This resource defines a user role to be used in conjunction with a Manager Account.

|     |     |     |
| --- | --- | --- |
| **AssignedPrivileges** | array | The redfish privileges that this role includes.<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **IsPredefined** | boolean | This property is used to indicate if the Role is one of the Redfish Predefined Roles vs a Custom role.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **OemPrivileges** | array | The OEM privileges that this role includes.<br>*read-write* |

# RoleCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Role.json#/definitions/Role"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Role resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# SecureBoot 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#SecureBoot.ResetKeys": {
      "$ref": "#/definitions/ResetKeys"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// SecureBootCurrentBoot
{
  "anyOf": [
    {
      "$ref": "#/definitions/SecureBootCurrentBootType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall indicate the UEFI Secure Boot state during the current boot cycle.",
  "description": "Secure Boot state during the current boot cycle."
}
```
```json
// SecureBootEnable
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "Setting this property to true enables UEFI Secure Boot, and setting it to false disables it. This property can be enabled only in UEFI boot mode.",
  "description": "Enable or disable UEFI Secure Boot (takes effect on next boot)."
}
```
```json
// SecureBootMode
{
  "anyOf": [
    {
      "$ref": "#/definitions/SecureBootModeType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain the current Secure Boot mode, as defined in the UEFI Specification.",
  "description": "Current Secure Boot Mode."
}
```

This resource contains UEFI Secure Boot information. It represents properties for managing the UEFI Secure Boot functionality of a system.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#SecureBoot.ResetKeys** |    |    |
|     } |   |   |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **SecureBootCurrentBoot** |  | Secure Boot state during the current boot cycle.<br>*read-only* |
| **SecureBootEnable** | boolean, null | Enable or disable UEFI Secure Boot (takes effect on next boot).<br>*read-write* |
| **SecureBootMode** |  | Current Secure Boot Mode.<br>*read-only* |

# SerialInterface 1.0.2


```json
// BitRate
{
  "type": "string",
  "enum": [
    "1200",
    "2400",
    "4800",
    "9600",
    "19200",
    "38400",
    "57600",
    "115200",
    "230400"
  ]
}
```
```json
// ConnectorType
{
  "type": "string",
  "enum": [
    "RJ45",
    "RJ11",
    "DB9 Female",
    "DB9 Male",
    "DB25 Female",
    "DB25 Male",
    "USB",
    "mUSB",
    "uUSB"
  ]
}
```
```json
// DataBits
{
  "type": "string",
  "enum": [
    "5",
    "6",
    "7",
    "8"
  ]
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// FlowControl
{
  "type": "string",
  "enum": [
    "None",
    "Software",
    "Hardware"
  ],
  "enumDescriptions": {
    "Software": "XON/XOFF in-band flow control imposed",
    "Hardware": "Out of band flow control imposed",
    "None": "No flow control imposed"
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// InterfaceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this interface is enabled.",
  "description": "This indicates whether this interface is enabled."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Parity
{
  "type": "string",
  "enum": [
    "None",
    "Even",
    "Odd",
    "Mark",
    "Space"
  ]
}
```
```json
// PinOut
{
  "anyOf": [
    {
      "$ref": "#/definitions/PinOut"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall indicate the physical pin out for the serial connection.",
  "description": "The physical pin configuration needed for a serial connector."
}
```
```json
// SignalType
{
  "type": "string",
  "enum": [
    "Rs232",
    "Rs485"
  ]
}
```
```json
// StopBits
{
  "type": "string",
  "enum": [
    "1",
    "2"
  ]
}
```

This schema defines an asynchronous serial interface resource.

|     |     |     |
| --- | --- | --- |
| **BitRate** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **ConnectorType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **DataBits** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **Description** |  | <br>*read-write* |
| **FlowControl** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **InterfaceEnabled** | boolean, null | This indicates whether this interface is enabled.<br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Parity** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **PinOut** |  | The physical pin configuration needed for a serial connector.<br>*read-only* |
| **SignalType** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **StopBits** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |

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


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/SerialInterface.json#/definitions/SerialInterface"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of SerialInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# ServiceRoot 1.0.2


```json
// AccountService
{
  "properties": {
    "MinPasswordLength": {
      "type": "number",
      "readonly": true,
      "longDescription": "This property shall reference the minimum password length that the implementation will allow a password to be set to.",
      "minimum": 0,
      "description": "This is the minimum password length for this service."
    },
    "AccountLockoutCounterResetAfter": {
      "type": "number",
      "readonly": false,
      "longDescription": "This property shall reference the threshold of time in seconds from the last failed login attempt at which point the AccountLockoutThreshold counter (that counts number of failed login attempts) is reset back to zero (at which point AccountLockoutThreshold failures would be required before the account is locked).  This value shall be less than or equal to AccountLockoutDuration. The threshold counter also resets to zero after each successful login.",
      "minimum": 0,
      "description": "The interval of time in seconds since the last failed login attempt at which point the lockout threshold counter for the account is reset to zero. Must be less than or equal to AccountLockoutDuration"
    },
    "Roles": {
      "longDescription": "This property shall contain the link to a collection of type RoleCollection.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/RoleCollection.json#/definitions/RoleCollection",
      "description": "Link to a collection of Roles"
    },
    "Accounts": {
      "longDescription": "This property shall contain the link to a collection of type ManagerAccountCollection.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/ManagerAccountCollection.json#/definitions/ManagerAccountCollection",
      "description": "Link to a collection of Manager Accounts"
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "AuthFailureLoggingThreshold": {
      "type": "number",
      "readonly": false,
      "longDescription": "This property shall reference the threshold for when an authorization failure is logged.  This represents a modulo function value, thus the failure shall be logged every nth occurrence where n represents the value of this property.",
      "minimum": 0,
      "description": "This is the number of authorization failures that need to occur before the failure attempt is logged to the manager log."
    },
    "AccountLockoutDuration": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "This property shall reference the period of time in seconds that an account is locked after the number of failed login attempts reaches the threshold referenced by AccountLockoutThreshold, within the window of time referenced by AccountLockoutCounterResetAfter.  The value shall be greater than or equal to the value of AccountLockoutResetAfter.  If set to 0, no lockout shall occur.",
      "minimum": 0,
      "description": "The time in seconds an account is locked after the account lockout threshold is met. Must be >= AccountLockoutResetAfter. If set to 0, no lockout will occur."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "AccountLockoutThreshold": {
      "type": [
        "number",
        "null"
      ],
      "readonly": false,
      "longDescription": "This property shall reference the threshold of failed login attempts at which point the user's account is locked.  If set to 0, no lockout shall ever occur.",
      "minimum": 0,
      "description": "The number of failed login attempts before a user account is locked for a specified duration. (0=never locked)"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "ServiceEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
      "description": "This indicates whether this service is enabled."
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "MaxPasswordLength": {
      "type": "number",
      "readonly": true,
      "longDescription": "This property shall reference the maximum password length that the implementation will allow a password to be set to.",
      "minimum": 0,
      "description": "This is the maximum password length for this service."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent a management account service for a Redfish implementation.",
  "type": "object",
  "description": "Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Chassis
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Chassis resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EventService
{
  "properties": {
    "DeliveryRetryAttempts": {
      "type": "number",
      "readonly": true,
      "longDescription": "The value of this property shall be the number of retrys attempted for any given event to the subscription destination before the subscription is terminated.",
      "description": "This is the number of attempts an event posting is retried before the subscription is terminated."
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "DeliveryRetryIntervalSeconds": {
      "type": "number",
      "readonly": true,
      "longDescription": "The value of this property shall be the interval in seconds between the retry attempts for any given event to the subscription destination.",
      "description": "This represents the number of seconds between retry attempts for sending any given Event"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "EventTypesForSubscription": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Event.v1_0_0.json#/definitions/EventType"
      },
      "longDescription": "The value of this property shall be the types of events that subscriptions can subscribe to.  The semantics associated with the enumerations values are defined in the Redfish specification.",
      "readonly": true,
      "description": "This is the types of Events that can be subscribed to."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "ServiceEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
      "description": "This indicates whether this service is enabled."
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "Subscriptions": {
      "longDescription": "The value of this property shall contain the link to a collection of type EventDestinationCollection.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/EventDestinationCollection.json#/definitions/EventDestinationCollection",
      "description": "This is a reference to a collection of Event Destination resources."
    },
    "Actions": {
      "properties": {
        "Oem": {
          "type": "object",
          "properties": {},
          "additionalProperties": true,
          "patternProperties": {
            "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
              "type": [
                "array",
                "boolean",
                "number",
                "null",
                "object",
                "string"
              ],
              "description": "This property shall specify a valid odata or Redfish property."
            }
          }
        },
        "#EventService.SubmitTestEvent": {
          "$ref": "#/definitions/SubmitTestEvent"
        }
      },
      "readonly": true,
      "longDescription": "The Actions property shall contain the available actions for this resource.",
      "type": "object",
      "description": "The available actions for this resource.",
      "additionalProperties": false,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "type": "object",
  "description": "The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// JsonSchemas
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/JsonSchemaFile.json#/definitions/JsonSchemaFile"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of JsonSchemaFile resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "Sessions": {
      "longDescription": "This property shall contain the link to a collection of Sessions.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/SessionCollection.json#/definitions/SessionCollection",
      "description": "Link to a collection of Sessions"
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Managers
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Manager.json#/definitions/Manager"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Manager resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// RedfishVersion
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this string shall represent the version of the Redfish service.  The format of this string shall be of the format majorversion.minorversion.errata in compliance with Protocol Version section of the Redfish specification. ",
  "pattern": "^\\d+\\.\\d+\\.\\d+$",
  "description": "The version of the Redfish service"
}
```
```json
// Registries
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/MessageRegistryFile.json#/definitions/MessageRegistryFile"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of MessageRegistryFile resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// SessionService
{
  "properties": {
    "Sessions": {
      "longDescription": "This property shall contain the link to a collection of Sessions.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/SessionCollection.json#/definitions/SessionCollection",
      "description": "Link to a collection of Sessions"
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "ServiceEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
      "description": "This indicates whether this service is enabled."
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "SessionTimeout": {
      "maximum": 86400,
      "readonly": false,
      "type": "number",
      "longDescription": "This property shall reference the threshold of time in seconds between requests on a specific session at which point the session service shall close the session due to inactivity. The session service shall support any value between the Validation.Minimum and Validation.Maximum.",
      "minimum": 30,
      "description": "This is the number of seconds of inactivity that a session may have before the session service closes the session due to inactivity."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent the Session Service Properties for a Redfish implementation.",
  "type": "object",
  "description": "This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Systems
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/ComputerSystem.json#/definitions/ComputerSystem"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of ComputerSystem resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Tasks
{
  "properties": {
    "Tasks": {
      "longDescription": "The value of this property shall be a link to a resource of type TaskCollection.",
      "readonly": true,
      "$ref": "http://redfish.dmtf.org/schemas/v1/TaskCollection.json#/definitions/TaskCollection",
      "description": "References to the Tasks collection."
    },
    "Status": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Status"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "LifeCycleEventOnTaskStateChange": {
      "type": "boolean",
      "readonly": true,
      "longDescription": "The value of this property, if set to true, shall indicate that the service shall send a LifeCycle event to ListenerDestinations registered for such events upon change of task state.",
      "description": "Send an Event upon Task State Change."
    },
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "CompletedTaskOverWritePolicy": {
      "longDescription": "The value of this property shall indicate how completed tasks are handled should the task service need to track more tasks.",
      "readonly": true,
      "$ref": "#/definitions/OverWritePolicy",
      "description": "Overwrite policy of completed tasks"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "ServiceEnabled": {
      "type": [
        "boolean",
        "null"
      ],
      "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
      "description": "This indicates whether this service is enabled."
    },
    "DateTime": {
      "type": [
        "string",
        "null"
      ],
      "readonly": true,
      "longDescription": "The value of this property shall represent the current DateTime value for the TaskService, with offset from UTC, in Redfish Timestamp format.",
      "format": "date-time",
      "description": "The current DateTime (with offset) setting that the task service is using."
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Id"
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "required": [
    "Id",
    "Name"
  ],
  "longDescription": "This resource shall be used to represent a task service for a Redfish implementation.",
  "type": "object",
  "description": "This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// UUID
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/UUID"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this string shall represent the id of the Redfish service instance.  The format of this string shall be a 32-byte value in the form 8-4-4-4-12.  If SSDP is used, this value shall be an exact match of the UUID value returned in a 200OK from an SSDP M-SEARCH request during discovery. RFC4122 describes methods that can be used to create a UUID value. The value should be considered to be opaque. Client software should only treat the overall value as a universally unique identifier and should not interpret any sub-fields within the UUID.",
  "description": "Unique identifier for a service instance. When SSDP is used, this value should be an exact match of the UUID value returned in a 200OK from an SSDP M-SEARCH request during discovery. "
}
```

This object represents the root Redfish service.

|     |     |     |
| --- | --- | --- |
| **AccountService** { | object | Account Service contains properties common to all user accounts, such as password requirements, and control features such as account lockout.  It also contains links to the collections of Manager Accounts and Roles.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MinPasswordLength** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutCounterResetAfter** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Roles** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Accounts** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AuthFailureLoggingThreshold** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutDuration** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**AccountLockoutThreshold** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**MaxPasswordLength** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Chassis** { | object | A Collection of Chassis resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Description** |  | <br>*read-write* |
| **EventService** { | object | The Event Service resource contains properties for managing event subcriptions and generates the events sent to subscribers.  The resource has links to the actual collection of subscriptions (called Event Destinations).<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryAttempts** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DeliveryRetryIntervalSeconds** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**EventTypesForSubscription** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Subscriptions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Actions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **JsonSchemas** { | object | A Collection of JsonSchemaFile resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** |    |    |
|     } |   |   |
| **Managers** { | object | A Collection of Manager resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **RedfishVersion** | string | The version of the Redfish service<br>*read-only* |
| **Registries** { | object | A Collection of MessageRegistryFile resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **SessionService** { | object | This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Sessions** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**SessionTimeout** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Systems** { | object | A Collection of ComputerSystem resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Tasks** { | object | This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Tasks** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Status** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**LifeCycleEventOnTaskStateChange** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**CompletedTaskOverWritePolicy** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**ServiceEnabled** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**DateTime** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **UUID** |  | Unique identifier for a service instance. When SSDP is used, this value should be an exact match of the UUID value returned in a 200OK from an SSDP M-SEARCH request during discovery. <br>*read-only* |

# Session 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Password
{
  "type": [
    "string",
    "null"
  ],
  "longDescription": "The value of this property shall be the password for this session.  The value shall be null for GET requests.",
  "description": "This property is used in a POST to specify a password when creating a new session.  This property is null on a GET."
}
```
```json
// UserName
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the UserName that matches a registered account identified by a ManagerAccount resource registered with the Account Service.",
  "description": "The UserName for the account for this session."
}
```

The Session resource describes a single connection (session) between a client and a Redfish service instance.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Password** | string, null | This property is used in a POST to specify a password when creating a new session.  This property is null on a GET.<br>*read-write* |
| **UserName** | string, null | The UserName for the account for this session.<br>*read-only* |

# SessionCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Session.json#/definitions/Session"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Session resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# SessionService 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// ServiceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
  "description": "This indicates whether this service is enabled."
}
```
```json
// SessionTimeout
{
  "maximum": 86400,
  "readonly": false,
  "type": "number",
  "longDescription": "This property shall reference the threshold of time in seconds between requests on a specific session at which point the session service shall close the session due to inactivity. The session service shall support any value between the Validation.Minimum and Validation.Maximum.",
  "minimum": 30,
  "description": "This is the number of seconds of inactivity that a session may have before the session service closes the session due to inactivity."
}
```
```json
// Sessions
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Session.json#/definitions/Session"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Session resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

This is the schema definition for the Session Service.  It represents the properties for the service itself and has links to the actual list of sessions.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **ServiceEnabled** | boolean, null | This indicates whether this service is enabled.<br>*read-write* |
| **SessionTimeout** | number | This is the number of seconds of inactivity that a session may have before the session service closes the session due to inactivity.<br>*read-write* |
| **Sessions** { | object | A Collection of Session resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |

# SimpleStorage 1.1.0


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Devices
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/SimpleStorage.v1_0_0.json#/definitions/Device"
  },
  "longDescription": "This property shall contain a list of storage devices associated with this resource",
  "readonly": true,
  "description": "The storage devices associated with this resource"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// UefiDevicePath
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the UEFI device path used to identify and locate the specific storage controller",
  "description": "The UEFI device path used to access this storage controller."
}
```

This is the schema definition for the Simple Storage resource.  It represents the properties of a storage controller and its directly-attached devices.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Devices** *(deprecated v1.0.2)* | array | The storage devices associated with this resource<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **UefiDevicePath** | string, null | The UEFI device path used to access this storage controller.<br>*read-only* |

# SimpleStorageCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/SimpleStorage.json#/definitions/SimpleStorage"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of SimpleStorage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Storage 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Storage.SetEncryptionKey": {
      "$ref": "#/definitions/SetEncryptionKey"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Drives
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Drive.json#/definitions/Drive"
  },
  "longDescription": "A collection that indicates all the drives attached to the storage controllers that this resource represents.",
  "readonly": true,
  "description": "The set of drives attached to the storage controllers represented by this resource."
}
```
```json
// Drives@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "Enclosures@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Enclosures": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Chassis.json#/definitions/Chassis"
      },
      "longDescription": "The value of this property shall reference a resource of type Chassis that represents the physical containers attached to this resource.",
      "readonly": true,
      "description": "An array of references to the chassis to which this storage subsystem is attached"
    },
    "Enclosures@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Redundancy
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
  },
  "readonly": true,
  "description": "Redundancy information for the storage subsystem"
}
```
```json
// Redundancy@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// StorageControllers
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/StorageController"
  },
  "longDescription": "A collection that indicates all the storage controllers that this resource represents.",
  "readonly": true,
  "description": "The set of storage controllers represented by this resource."
}
```
```json
// StorageControllers@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Volumes
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Volume.json#/definitions/Volume"
  },
  "longDescription": "A collection that indicates all the volumes produced by the storage controllers that this resource represents.",
  "readonly": true,
  "description": "The set of volumes produced by the storage controllers represented by this resource."
}
```
```json
// Volumes@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```

This schema defines a storage subsystem and its respective properties.  A storage subsystem represents a set of storage controllers (physical or virtual) and the resources such as volumes that can be accessed from that subsystem.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Storage.SetEncryptionKey** |    |    |
|     } |   |   |
| **Description** |  | <br>*read-write* |
| **Drives** | array | The set of drives attached to the storage controllers represented by this resource.<br>*read-only* |
| **Drives@odata.navigationLink** | string | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Enclosures@odata.count** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Redundancy** | array | Redundancy information for the storage subsystem<br>*read-only* |
| **Redundancy@odata.navigationLink** | string | <br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **StorageControllers** | array | The set of storage controllers represented by this resource.<br>*read-only* |
| **StorageControllers@odata.navigationLink** | string | <br>*read-write* |
| **Volumes** | array | The set of volumes produced by the storage controllers represented by this resource.<br>*read-only* |
| **Volumes@odata.navigationLink** | string | <br>*read-write* |

# StorageCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Storage.json#/definitions/Storage"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Storage resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Task 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// EndTime
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall indicate the time the task was completed.",
  "format": "date-time",
  "description": "The date-time stamp that the task was last completed."
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Messages
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Message.json#/definitions/Message"
  },
  "longDescription": "The value of this property shall be an array of messages associated with the task.",
  "readonly": true,
  "description": "This is an array of messages associated with the task."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// StartTime
{
  "type": "string",
  "readonly": true,
  "longDescription": "The value of this property shall indicate the time the task was started.",
  "format": "date-time",
  "description": "The date-time stamp that the task was last started."
}
```
```json
// TaskState
{
  "type": "string",
  "enum": [
    "New",
    "Starting",
    "Running",
    "Suspended",
    "Interrupted",
    "Pending",
    "Stopping",
    "Completed",
    "Killed",
    "Exception",
    "Service"
  ],
  "enumDescriptions": {
    "Stopping": "Task is in the process of stopping",
    "Service": "Task is running as a service",
    "Killed": "Task was terminated",
    "Running": "Task is running normally",
    "Interrupted": "Task has been interrupted",
    "Exception": "Task has stopped due to an exception condition",
    "New": "A new task",
    "Starting": "Task is starting",
    "Suspended": "Task has been suspended",
    "Completed": "Task has completed",
    "Pending": "Task is pending and has not started"
  }
}
```
```json
// TaskStatus
{
  "type": "string",
  "enum": [
    "OK",
    "Warning",
    "Critical"
  ],
  "enumDescriptions": {
    "Warning": "A condition exists that requires attention",
    "Critical": "A critical condition exists that requires immediate attention",
    "OK": "Normal"
  }
}
```

This resource contains information about a specific Task scheduled by or being executed by a Redfish service's Task Service.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **EndTime** | string | The date-time stamp that the task was last completed.<br>*read-only* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Messages** | array | This is an array of messages associated with the task.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **StartTime** | string | The date-time stamp that the task was last started.<br>*read-only* |
| **TaskState** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **TaskStatus** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |

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


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Task.json#/definitions/Task"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of Task resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# TaskService 1.0.2


```json
// CompletedTaskOverWritePolicy
{
  "type": "string",
  "enum": [
    "Manual",
    "Oldest"
  ],
  "enumDescriptions": {
    "Manual": "Completed tasks are not automatically overwritten",
    "Oldest": "Oldest completed tasks are overwritten"
  }
}
```
```json
// DateTime
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall represent the current DateTime value for the TaskService, with offset from UTC, in Redfish Timestamp format.",
  "format": "date-time",
  "description": "The current DateTime (with offset) setting that the task service is using."
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// LifeCycleEventOnTaskStateChange
{
  "type": "boolean",
  "readonly": true,
  "longDescription": "The value of this property, if set to true, shall indicate that the service shall send a LifeCycle event to ListenerDestinations registered for such events upon change of task state.",
  "description": "Send an Event upon Task State Change."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// ServiceEnabled
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be a boolean indicating whether this service is enabled.",
  "description": "This indicates whether this service is enabled."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Tasks
{
  "type": "object",
  "properties": {
    "@odata.id": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/id"
    },
    "Members@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    },
    "Name": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Name"
    },
    "Members@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Oem": {
      "longDescription": "The value of this string shall be of the format for the reserved word *Oem*.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "This is the manufacturer/provider specific extension moniker used to divide the Oem object into sections."
    },
    "Members": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Task.json#/definitions/Task"
      },
      "readonly": true,
      "description": "Contains the members of this collection."
    },
    "@odata.context": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/context"
    },
    "Description": {
      "anyOf": [
        {
          "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
        },
        {
          "type": "null"
        }
      ]
    },
    "@odata.type": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/type"
    }
  },
  "description": "A Collection of Task resource instances.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```

This is the schema definition for the Task Service.  It represents the properties for the service itself and has links to the actual list of tasks.

|     |     |     |
| --- | --- | --- |
| **CompletedTaskOverWritePolicy** | string |  *See Property Details, below, for more information about this property.*<br>*read-write* |
| **DateTime** | string, null | The current DateTime (with offset) setting that the task service is using.<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **LifeCycleEventOnTaskStateChange** | boolean | Send an Event upon Task State Change.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **ServiceEnabled** | boolean, null | This indicates whether this service is enabled.<br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Tasks** { | object | A Collection of Task resource instances.<br>*read-write* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.id** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.navigationLink** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Name** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Members** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.context** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Description** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**@odata.type** |    |    |
|     } |   |   |

## Property Details

### CompletedTaskOverWritePolicy:

| string | Description |
| --- | --- |
| Manual | Completed tasks are not automatically overwritten |
| Oldest | Oldest completed tasks are overwritten |


# Thermal 1.1.0


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Fans
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Thermal.v1_0_0.json#/definitions/Fan"
  },
  "longDescription": "These properties shall be the definition for fans for a Redfish implementation.",
  "readonly": false,
  "description": "This is the definition for fans."
}
```
```json
// Fans@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Redundancy
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Redundancy.json#/definitions/Redundancy"
  },
  "longDescription": "The values of the properties in this array shall be used to show redundancy for fans and other elements in this resource.  The use of IDs within these arrays shall reference the members of the redundancy groups.",
  "readonly": true,
  "description": "This structure is used to show redundancy for fans.  The Component ids will reference the members of the redundancy groups."
}
```
```json
// Redundancy@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Temperatures
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/Temperature"
  },
  "longDescription": "These properties shall be the definition for temperature sensors for a Redfish implementation.",
  "readonly": false,
  "description": "This is the definition for temperature sensors."
}
```
```json
// Temperatures@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```

This is the schema definition for the Thermal properties.  It represents the properties for Temperature and Cooling.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Fans** | array | This is the definition for fans.<br>*read-write* |
| **Fans@odata.navigationLink** | string | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Redundancy** | array | This structure is used to show redundancy for fans.  The Component ids will reference the members of the redundancy groups.<br>*read-only* |
| **Redundancy@odata.navigationLink** | string | <br>*read-write* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **Temperatures** | array | This is the definition for temperature sensors.<br>*read-write* |
| **Temperatures@odata.navigationLink** | string | <br>*read-write* |

# VLanNetworkInterface 1.0.2


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// VLANEnable
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "The value of this property shall be used to indicate if this VLAN is enabled for this interface.",
  "description": "This indicates if this VLAN is enabled."
}
```
```json
// VLANId
{
  "anyOf": [
    {
      "$ref": "#/definitions/VLANId"
    },
    {
      "type": "null"
    }
  ],
  "longDescription": "The value of this property shall be used to indicate the VLAN identifier for this VLAN.",
  "description": "This indicates the VLAN identifier for this VLAN."
}
```

This resource contains information for a Virtual LAN (VLAN) network instance available on a manager, system or other device.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **VLANEnable** | boolean, null | This indicates if this VLAN is enabled.<br>*read-write* |
| **VLANId** |  | This indicates the VLAN identifier for this VLAN.<br>*read-write* |

# VLanNetworkInterfaceCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/VLanNetworkInterface.json#/definitions/VLanNetworkInterface"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of VLanNetworkInterface resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# VirtualMedia 1.0.2


```json
// ConnectedVia
{
  "anyOf": [
    {
      "$ref": "#/definitions/ConnectedVia"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "The value of this property shall indicate the current connection method from a client to the virtual media represented by this resource.  A value of NotConnected shall indicate no connection is present.  A value of URI shall indicate that a remote connection via a URI reference type is being used. ",
  "description": "Current virtual media connection methods"
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Image
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this string shall be an URI.  A null value indicated no image connection.",
  "format": "uri",
  "description": "A URI providing the location of the selected image"
}
```
```json
// ImageName
{
  "type": [
    "string",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be the name of the image. ",
  "description": "The current image name"
}
```
```json
// Inserted
{
  "type": [
    "boolean",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be used to indicate if media is present in the virtual media device.  This is usually only applicable to remoting of devices and not for image virtual media usage. ",
  "description": "Indicates if virtual media is inserted in the virtual device."
}
```
```json
// MediaTypes
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/MediaType"
  },
  "longDescription": "The values of this array shall be the supported media types for this connection.",
  "readonly": true,
  "description": "This is the media types supported as virtual media."
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// WriteProtected
{
  "type": [
    "boolean",
    "null"
  ],
  "readonly": true,
  "longDescription": "The value of this property shall be used to indicate if the remote device media prevents writing to that media. ",
  "description": "Indicates the media is write protected."
}
```

This resource allows monitoring and control of an instance of virtual media (e.g. a remote CD, DVD, or USB device) functionality provided by a Manager for a system or device.

|     |     |     |
| --- | --- | --- |
| **ConnectedVia** |  | Current virtual media connection methods<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Image** | string, null | A URI providing the location of the selected image<br>*read-only* |
| **ImageName** | string, null | The current image name<br>*read-only* |
| **Inserted** | boolean, null | Indicates if virtual media is inserted in the virtual device.<br>*read-only* |
| **MediaTypes** | array | This is the media types supported as virtual media.<br>*read-only* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **WriteProtected** | boolean, null | Indicates the media is write protected.<br>*read-only* |

# VirtualMediaCollection


```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Members
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/VirtualMedia.json#/definitions/VirtualMedia"
  },
  "readonly": true,
  "description": "Contains the members of this collection."
}
```
```json
// Members@odata.navigationLink
{
  "type": "string",
  "format": "uri"
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```

A Collection of VirtualMedia resource instances.

|     |     |     |
| --- | --- | --- |
| **Description** |  | <br>*read-write* |
| **Members** | array | Contains the members of this collection.<br>*read-only* |
| **Members@odata.navigationLink** | string | <br>*read-write* |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |

# Volume 1.0.0


```json
// Actions
{
  "properties": {
    "Oem": {
      "type": "object",
      "properties": {},
      "additionalProperties": true,
      "patternProperties": {
        "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
          "type": [
            "array",
            "boolean",
            "number",
            "null",
            "object",
            "string"
          ],
          "description": "This property shall specify a valid odata or Redfish property."
        }
      }
    },
    "#Volume.Initialize": {
      "$ref": "#/definitions/Initialize"
    }
  },
  "readonly": true,
  "longDescription": "The Actions property shall contain the available actions for this resource.",
  "type": "object",
  "description": "The available actions for this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// BlockSizeBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain size of the smallest addressible unit of the associated volume.",
  "description": "The size of the smallest addressible unit (Block) of this volume in bytes"
}
```
```json
// CapacityBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the size in bytes of the associated volume.",
  "description": "The size in bytes of this Volume"
}
```
```json
// Description
{
  "anyOf": [
    {
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Description"
    },
    {
      "type": "null"
    }
  ]
}
```
```json
// Encrypted
{
  "type": [
    "boolean",
    "null"
  ],
  "longDescription": "This property shall contain a boolean indicator if the Volume is currently utilizing encryption or not.",
  "description": "Is this Volume encrypted"
}
```
```json
// EncryptionTypes
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/EncryptionTypes"
  },
  "longDescription": "This property shall contain the types of encryption used by this Volume.",
  "description": "The types of encryption used by this Volume"
}
```
```json
// Id
{
  "type": "string",
  "readonly": true,
  "longDescription": "This property represents an identifier for the resource.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "description": "Uniquely identifies the resource within the collection of like resources."
}
```
```json
// Identifiers
{
  "type": "array",
  "items": {
    "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.v1_1_0.json#/definitions/Identifier"
  },
  "longDescription": "This property shall contain a list of all known durable names for the associated volume.",
  "readonly": true,
  "description": "The Durable names for the volume"
}
```
```json
// Links
{
  "properties": {
    "Oem": {
      "longDescription": "This object represents the Oem property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
      "$ref": "http://redfish.dmtf.org/schemas/v1/Resource.json#/definitions/Oem",
      "description": "Oem extension object."
    },
    "Drives@odata.count": {
      "$ref": "http://redfish.dmtf.org/schemas/v1/odata.4.0.0.json#/definitions/count"
    },
    "Drives": {
      "type": "array",
      "items": {
        "$ref": "http://redfish.dmtf.org/schemas/v1/Drive.json#/definitions/Drive"
      },
      "longDescription": "The value of this property shall be a reference to the resources that this volume is associated with and shall reference resources of type Drive. This property shall only contain references to Drive entities which are currently members of the Volume, not hot spare Drives which are not currently a member of the volume.",
      "readonly": true,
      "description": "An array of references to the drives which contain this volume. This will reference Drives that either wholly or only partly contain this volume."
    },
    "Drives@odata.navigationLink": {
      "type": "string",
      "format": "uri"
    }
  },
  "readonly": true,
  "longDescription": "The Links property, as described by the Redfish Specification, shall contain references to resources that are related to, but not contained by (subordinate to), this resource.",
  "type": "object",
  "description": "Contains references to other resources that are related to this resource.",
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// Name
{
  "type": "string",
  "readonly": true,
  "longDescription": "This object represents the Name property.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification. The value of this string shall be of the format for the reserved word *Name*.",
  "description": "The name of the resource or array element."
}
```
```json
// Oem
{
  "properties": {},
  "longDescription": "This object represents the Oem properties.  All values for resources described by this schema shall comply to the requirements as described in the Redfish specification.",
  "type": "object",
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    },
    "[A-Za-z0-9_.:]+": {
      "$ref": "#/definitions/OemObject"
    }
  },
  "additionalProperties": true,
  "description": "Oem extension object."
}
```
```json
// Operations
{
  "type": "array",
  "items": {
    "$ref": "#/definitions/Operations"
  },
  "longDescription": "This property shall contain a list of all currently running on the Volume.",
  "readonly": true,
  "description": "The operations currently running on the Volume"
}
```
```json
// OptimumIOSizeBytes
{
  "type": [
    "number",
    "null"
  ],
  "readonly": true,
  "longDescription": "This property shall contain the optimum IO size to use when performing IO on this volume. For logical disks, this is the stripe size. For physical disks, this describes the physical sector size.",
  "description": "The size in bytes of this Volume's optimum IO size."
}
```
```json
// Status
{
  "type": "object",
  "properties": {
    "Oem": {
      "$ref": "#/definitions/Oem"
    },
    "State": {
      "anyOf": [
        {
          "$ref": "#/definitions/State"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent if this component is available or not and why.  Enabled indicates the resource is available.  Disabled indicates the resource has been intentionally made unavailable but it can be enabled.  Offline indicates the resource is unavailable intentionally and requires action to be made available.  InTest indicates that the component is undergoing testing.  Starting indicates that the resource is on its way to becoming available.  Absent indicates the resources is physically unavailable.",
      "description": "This indicates the known state of the resource, such as if it is enabled."
    },
    "Health": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource without considering its dependent resources. The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the health state of this resource in the absence of its dependent resources."
    },
    "HealthRollup": {
      "anyOf": [
        {
          "$ref": "#/definitions/Health"
        },
        {
          "type": "null"
        }
      ],
      "readonly": true,
      "longDescription": "This property shall represent the HealthState of the resource and its dependent resources.  The values shall conform to those defined in the Redfish specification.",
      "description": "This represents the overall health state from the view of this resource."
    }
  },
  "readonly": true,
  "additionalProperties": false,
  "patternProperties": {
    "^([a-zA-Z_][a-zA-Z0-9_]*)?@(odata|Redfish|Message|Privileges)\\.[a-zA-Z_][a-zA-Z0-9_.]+$": {
      "type": [
        "array",
        "boolean",
        "number",
        "null",
        "object",
        "string"
      ],
      "description": "This property shall specify a valid odata or Redfish property."
    }
  }
}
```
```json
// VolumeType
{
  "anyOf": [
    {
      "$ref": "#/definitions/VolumeType"
    },
    {
      "type": "null"
    }
  ],
  "readonly": true,
  "longDescription": "This property shall contain failure information as defined by the manufacturer for the associated drive.",
  "description": "Is this drive currently predicting a failure in the near future"
}
```

Volume contains properties used to describe a volume, virtual disk, LUN, or other logical storage entity for any system.

|     |     |     |
| --- | --- | --- |
| **Actions** { | object | The available actions for this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**#Volume.Initialize** |    |    |
|     } |   |   |
| **BlockSizeBytes** | number, null | The size of the smallest addressible unit (Block) of this volume in bytes<br>*read-only* |
| **CapacityBytes** | number, null | The size in bytes of this Volume<br>*read-only* |
| **Description** |  | <br>*read-write* |
| **Encrypted** | boolean, null | Is this Volume encrypted<br>*read-write* |
| **EncryptionTypes** | array | The types of encryption used by this Volume<br>*read-write* |
| **Id** | string | Uniquely identifies the resource within the collection of like resources.<br>*read-only* |
| **Identifiers** | array | The Durable names for the volume<br>*read-only* |
| **Links** { | object | Contains references to other resources that are related to this resource.<br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.count** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Drives@odata.navigationLink** |    |    |
|     } |   |   |
| **Name** | string | The name of the resource or array element.<br>*read-only* |
| **Oem** {} | object | Oem extension object.<br>*read-write* |
| **Operations** | array | The operations currently running on the Volume<br>*read-only* |
| **OptimumIOSizeBytes** | number, null | The size in bytes of this Volume's optimum IO size.<br>*read-only* |
| **Status** { | object | <br>*read-only* |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Oem** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**State** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Health** |    |    |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**HealthRollup** |    |    |
|     } |   |   |
| **VolumeType** |  | Is this drive currently predicting a failure in the near future<br>*read-only* |

---
TODO: postscript from MD file

