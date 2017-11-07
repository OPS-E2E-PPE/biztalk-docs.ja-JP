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
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="7e119-102">TIBCO Enterprise Message Service のメッセージ記述子のプロパティ</span><span class="sxs-lookup"><span data-stu-id="7e119-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>

## <a name="descriptor-properties-and-values"></a><span data-ttu-id="7e119-103">記述子のプロパティ、および値</span><span class="sxs-lookup"><span data-stu-id="7e119-103">Descriptor properties, and values</span></span>
<span data-ttu-id="7e119-104">次の表は、使用可能なメッセージ記述子 (TibcoEMSMD 構造) プロパティの完全なセットと、それらに対応する型と値を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e119-104">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="7e119-105">名前</span><span class="sxs-lookup"><span data-stu-id="7e119-105">Name</span></span>|<span data-ttu-id="7e119-106">型</span><span class="sxs-lookup"><span data-stu-id="7e119-106">Type</span></span>|<span data-ttu-id="7e119-107">値</span><span class="sxs-lookup"><span data-stu-id="7e119-107">Value</span></span>|<span data-ttu-id="7e119-108">注</span><span class="sxs-lookup"><span data-stu-id="7e119-108">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="7e119-109">TibcoEMS .CorrelationID</span><span class="sxs-lookup"><span data-stu-id="7e119-109">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="7e119-110">string</span><span class="sxs-lookup"><span data-stu-id="7e119-110">string</span></span>|||  
|<span data-ttu-id="7e119-111">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="7e119-111">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="7e119-112">string</span><span class="sxs-lookup"><span data-stu-id="7e119-112">string</span></span>|<span data-ttu-id="7e119-113">PERSISENT または NON-PERSISTENT のいずれか</span><span class="sxs-lookup"><span data-stu-id="7e119-113">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="7e119-114">TibcoEMS .Destination</span><span class="sxs-lookup"><span data-stu-id="7e119-114">TibcoEMS .Destination</span></span>|<span data-ttu-id="7e119-115">string</span><span class="sxs-lookup"><span data-stu-id="7e119-115">string</span></span>||<span data-ttu-id="7e119-116">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7e119-116">Read-only</span></span>|  
|<span data-ttu-id="7e119-117">TibcoEMS .Expiration</span><span class="sxs-lookup"><span data-stu-id="7e119-117">TibcoEMS .Expiration</span></span>|<span data-ttu-id="7e119-118">long</span><span class="sxs-lookup"><span data-stu-id="7e119-118">long</span></span>|||  
|<span data-ttu-id="7e119-119">TibcoEMS .MessageID</span><span class="sxs-lookup"><span data-stu-id="7e119-119">TibcoEMS .MessageID</span></span>|<span data-ttu-id="7e119-120">string</span><span class="sxs-lookup"><span data-stu-id="7e119-120">string</span></span>||<span data-ttu-id="7e119-121">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7e119-121">Read-only</span></span>|  
|<span data-ttu-id="7e119-122">TibcoEMS .Priority</span><span class="sxs-lookup"><span data-stu-id="7e119-122">TibcoEMS .Priority</span></span>|<span data-ttu-id="7e119-123">整数 (integer)</span><span class="sxs-lookup"><span data-stu-id="7e119-123">integer</span></span>|<span data-ttu-id="7e119-124">0 ～ 9</span><span class="sxs-lookup"><span data-stu-id="7e119-124">From 0 to 9</span></span>||  
|<span data-ttu-id="7e119-125">TibcoEMS .Redelivered</span><span class="sxs-lookup"><span data-stu-id="7e119-125">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="7e119-126">boolean</span><span class="sxs-lookup"><span data-stu-id="7e119-126">boolean</span></span>||<span data-ttu-id="7e119-127">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7e119-127">Read-only</span></span>|  
|<span data-ttu-id="7e119-128">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="7e119-128">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="7e119-129">string</span><span class="sxs-lookup"><span data-stu-id="7e119-129">string</span></span>|<span data-ttu-id="7e119-130">Destination と同様</span><span class="sxs-lookup"><span data-stu-id="7e119-130">Similar to Destination</span></span>||  
|<span data-ttu-id="7e119-131">TibcoEMS .Timestamp</span><span class="sxs-lookup"><span data-stu-id="7e119-131">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="7e119-132">long</span><span class="sxs-lookup"><span data-stu-id="7e119-132">long</span></span>||<span data-ttu-id="7e119-133">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7e119-133">Read-only</span></span>|  
  
 <span data-ttu-id="7e119-134">読み取り専用プロパティに Microsoft BizTalk Adapter for TIBCO EMS メッセージが配信されるときに、TIBCO Enterprise Message Service で設定されているこれらのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7e119-134">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="7e119-135">メッセージの割り当て図形の式でこの値を変更することはできますが、メッセージに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="7e119-135">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="7e119-136">EMS メッセージから BizTalk Server メッセージに移動する必要がある他のプロパティについては、プロパティの DLL を作成し、それをプロジェクトで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e119-136">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="7e119-137">次のサンプル プロパティ スキーマを使用すると、オーケストレーションで `JMSXDeliveryCount` メッセージ プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7e119-137">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
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
  
 <span data-ttu-id="7e119-138">必ずターゲットの名前空間を使用し、その名前空間を使用するプロパティのみを BizTalk Server メッセージまたは EMS メッセージにコピーします。</span><span class="sxs-lookup"><span data-stu-id="7e119-138">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="7e119-139">メッセージ コンテキストのプロパティの詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e119-139">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e119-140">参照</span><span class="sxs-lookup"><span data-stu-id="7e119-140">See Also</span></span>  
[<span data-ttu-id="7e119-141">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e119-141">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)