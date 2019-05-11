---
title: TIBCO EMS メッセージ記述子のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3684b21f7e37757a9d6ab3bf66e352d4518d33bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379900"
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a>TIBCO Enterprise Message Service のメッセージ記述子のプロパティ

## <a name="descriptor-properties-and-values"></a>記述子のプロパティと値
次の表では、使用可能なメッセージ記述子 (TibcoEMSMD 構造) プロパティと、対応する型と値の完全なセットを示します。  
  
|名前|型|値|メモ|  
|----------|----------|-----------|-----------|  
|TibcoEMS します。関連付け Id|string|||  
|TibcoEMS します。DelieveryMode|string|PERSISENT または NON-PERSISTENT のいずれか||  
|TibcoEMS します。変換先|string||読み取り専用です。|  
|TibcoEMS します。有効期限|long|||  
|TibcoEMS します。メッセージ Id|string||読み取り専用です。|  
|TibcoEMS します。優先順位|整数 (integer)|0 ~ 9||  
|TibcoEMS します。再配信|boolean||読み取り専用です。|  
|TibcoEMS .ReplyTo|string|変換先に似ています||  
|TibcoEMS します。タイムスタンプ|long||読み取り専用です。|  
  
 読み取り専用プロパティに Microsoft BizTalk Adapter for TIBCO EMS メッセージが配信されるときに、TIBCO Enterprise Message Service で設定されているこれらのプロパティです。 メッセージの割り当て図形の式のことができますが、値を変更しても、メッセージには影響しません。  
  
 EMS メッセージから BizTalk Server メッセージに移動する必要がありますを他のプロパティは、プロパティの DLL を作成し、プロジェクトで使用する必要があります。  
  
 次のサンプル プロパティ スキーマには、使用するオーケストレーション、`JMSXDeliveryCount`メッセージ プロパティ。  
  
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
  
 ターゲットの名前空間が使用します。BizTalk Server メッセージまたは EMS メッセージは、この名前空間を使用するプロパティのみがコピーされます。 メッセージ コンテキスト プロパティの詳細については、BizTalk Server ドキュメントを参照してください。  
  
## <a name="see-also"></a>参照  
[TIBCO EMS メッセージ コンテキスト プロパティ](../core/message-context-properties-in-biztalk-server.md)