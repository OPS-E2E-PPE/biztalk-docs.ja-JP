---
title: "TIBCO EMS メッセージ記述子のプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a2a7d6529cffba6afa3969964d1ea436d7fcda
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a>TIBCO Enterprise Message Service のメッセージ記述子のプロパティ

## <a name="descriptor-properties-and-values"></a>記述子のプロパティ、および値
次の表は、使用可能なメッセージ記述子 (TibcoEMSMD 構造) プロパティの完全なセットと、それらに対応する型と値を示しています。  
  
|名前|型|値|注|  
|----------|----------|-----------|-----------|  
|TibcoEMS .CorrelationID|string|||  
|TibcoEMS .DelieveryMode|string|PERSISENT または NON-PERSISTENT のいずれか||  
|TibcoEMS .Destination|string||読み取り専用です。|  
|TibcoEMS .Expiration|long|||  
|TibcoEMS .MessageID|string||読み取り専用です。|  
|TibcoEMS .Priority|整数 (integer)|0 ～ 9||  
|TibcoEMS .Redelivered|boolean||読み取り専用です。|  
|TibcoEMS .ReplyTo|string|Destination と同様||  
|TibcoEMS .Timestamp|long||読み取り専用です。|  
  
 読み取り専用プロパティに Microsoft BizTalk Adapter for TIBCO EMS メッセージが配信されるときに、TIBCO Enterprise Message Service で設定されているこれらのプロパティです。 メッセージの割り当て図形の式でこの値を変更することはできますが、メッセージに影響はありません。  
  
 EMS メッセージから BizTalk Server メッセージに移動する必要がある他のプロパティについては、プロパティの DLL を作成し、それをプロジェクトで使用する必要があります。  
  
 次のサンプル プロパティ スキーマを使用すると、オーケストレーションで `JMSXDeliveryCount` メッセージ プロパティを使用できます。  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 必ずターゲットの名前空間を使用し、その名前空間を使用するプロパティのみを BizTalk Server メッセージまたは EMS メッセージにコピーします。 メッセージ コンテキストのプロパティの詳細については、BizTalk Server のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
[TIBCO EMS メッセージ コンテキスト プロパティ](../core/message-context-properties-in-biztalk-server.md)