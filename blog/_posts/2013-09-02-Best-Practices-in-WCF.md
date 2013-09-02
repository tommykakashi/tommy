---
layout: post
title: Best Practices in Windows Communication Foundation
---

# Best Practices in Windows Communication Foundation

## Best Practices of Service Contract Versioning

###If precise compliance between schemas is required, you should assign a new version to your contract every time a change is implemented.

###If there is no need for precise compliance between schemas, you should heed the following points:
- You can add new methods at any time
- You may not delete any existing methods
- The parameter data types must remain compatible

## Best Practices of Data Contract Versioning

###If precise compliance between schemas is required, you should assign a new version to your contract every time a change is implemented.

###If there is no need for precise compliance between schemas, you should heed the following points:
- Data contracts should not be assigned new versions as a result of inheritance. Create a new independent data class instead.
- To facilitate round - tripping, you should implement the IExtensibleDataObject interface at the start.
- If you have to change the name of your data class or of some members, compatible data contracts can be created using the DataContract or DataMember attributes.
- Do not make subsequent changes to your data types.
- Do not change the order in which your data members appear by using the property [DataMember(Order=?)] .
- Leave the default IsRequired value ( false ) unchanged.
- You can add additional data members at any time but you should remember that this would change the serialization order. This problem is avoided by setting the Order property for new members to the current version ’ s value. Therefore, data members added in version 2 should be assigned Order=2 .
- Data members should not be deleted.
- Subsequent changes should not be made to the IsRequired property.
