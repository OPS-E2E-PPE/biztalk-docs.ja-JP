---
title: "TIBCO Enterprise Message Service メッセージ記述子プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message descriptor properties
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c75875c44c4d082089fc9394fef390a0f91571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="e63d6-102">TIBCO Enterprise Message Service のメッセージ記述子のプロパティ</span><span class="sxs-lookup"><span data-stu-id="e63d6-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>
<span data-ttu-id="e63d6-103">次の表は、使用可能なメッセージ記述子 (TibcoEMSMD 構造) プロパティの完全なセットと、それらに対応する型と値を示しています。</span><span class="sxs-lookup"><span data-stu-id="e63d6-103">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="e63d6-104">名前</span><span class="sxs-lookup"><span data-stu-id="e63d6-104">Name</span></span>|<span data-ttu-id="e63d6-105">型</span><span class="sxs-lookup"><span data-stu-id="e63d6-105">Type</span></span>|<span data-ttu-id="e63d6-106">値</span><span class="sxs-lookup"><span data-stu-id="e63d6-106">Value</span></span>|<span data-ttu-id="e63d6-107">注</span><span class="sxs-lookup"><span data-stu-id="e63d6-107">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="e63d6-108">TibcoEMS .CorrelationID</span><span class="sxs-lookup"><span data-stu-id="e63d6-108">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="e63d6-109">string</span><span class="sxs-lookup"><span data-stu-id="e63d6-109">string</span></span>|||  
|<span data-ttu-id="e63d6-110">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="e63d6-110">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="e63d6-111">string</span><span class="sxs-lookup"><span data-stu-id="e63d6-111">string</span></span>|<span data-ttu-id="e63d6-112">PERSISENT または NON-PERSISTENT のいずれか</span><span class="sxs-lookup"><span data-stu-id="e63d6-112">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="e63d6-113">TibcoEMS .Destination</span><span class="sxs-lookup"><span data-stu-id="e63d6-113">TibcoEMS .Destination</span></span>|<span data-ttu-id="e63d6-114">string</span><span class="sxs-lookup"><span data-stu-id="e63d6-114">string</span></span>||<span data-ttu-id="e63d6-115">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="e63d6-115">Read-only</span></span>|  
|<span data-ttu-id="e63d6-116">TibcoEMS .Expiration</span><span class="sxs-lookup"><span data-stu-id="e63d6-116">TibcoEMS .Expiration</span></span>|<span data-ttu-id="e63d6-117">long</span><span class="sxs-lookup"><span data-stu-id="e63d6-117">long</span></span>|||  
|<span data-ttu-id="e63d6-118">TibcoEMS .MessageID</span><span class="sxs-lookup"><span data-stu-id="e63d6-118">TibcoEMS .MessageID</span></span>|<span data-ttu-id="e63d6-119">string</span><span class="sxs-lookup"><span data-stu-id="e63d6-119">string</span></span>||<span data-ttu-id="e63d6-120">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="e63d6-120">Read-only</span></span>|  
|<span data-ttu-id="e63d6-121">TibcoEMS .Priority</span><span class="sxs-lookup"><span data-stu-id="e63d6-121">TibcoEMS .Priority</span></span>|<span data-ttu-id="e63d6-122">整数 (integer)</span><span class="sxs-lookup"><span data-stu-id="e63d6-122">integer</span></span>|<span data-ttu-id="e63d6-123">0 ～ 9</span><span class="sxs-lookup"><span data-stu-id="e63d6-123">From 0 to 9</span></span>||  
|<span data-ttu-id="e63d6-124">TibcoEMS .Redelivered</span><span class="sxs-lookup"><span data-stu-id="e63d6-124">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="e63d6-125">boolean</span><span class="sxs-lookup"><span data-stu-id="e63d6-125">boolean</span></span>||<span data-ttu-id="e63d6-126">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="e63d6-126">Read-only</span></span>|  
|<span data-ttu-id="e63d6-127">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="e63d6-127">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="e63d6-128">string</span><span class="sxs-lookup"><span data-stu-id="e63d6-128">string</span></span>|<span data-ttu-id="e63d6-129">Destination と同様</span><span class="sxs-lookup"><span data-stu-id="e63d6-129">Similar to Destination</span></span>||  
|<span data-ttu-id="e63d6-130">TibcoEMS .Timestamp</span><span class="sxs-lookup"><span data-stu-id="e63d6-130">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="e63d6-131">long</span><span class="sxs-lookup"><span data-stu-id="e63d6-131">long</span></span>||<span data-ttu-id="e63d6-132">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="e63d6-132">Read-only</span></span>|  
  
 <span data-ttu-id="e63d6-133">読み取り専用プロパティに Microsoft BizTalk Adapter for TIBCO EMS メッセージが配信されるときに、TIBCO Enterprise Message Service で設定されているこれらのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e63d6-133">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="e63d6-134">メッセージの割り当て図形の式でこの値を変更することはできますが、メッセージに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e63d6-134">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="e63d6-135">EMS メッセージから BizTalk Server メッセージに移動する必要がある他のプロパティについては、プロパティの DLL を作成し、それをプロジェクトで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e63d6-135">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="e63d6-136">次のサンプル プロパティ スキーマを使用すると、オーケストレーションで `JMSXDeliveryCount` メッセージ プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e63d6-136">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
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
  
 <span data-ttu-id="e63d6-137">必ずターゲットの名前空間を使用し、その名前空間を使用するプロパティのみを BizTalk Server メッセージまたは EMS メッセージにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e63d6-137">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="e63d6-138">メッセージ コンテキストのプロパティの詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e63d6-138">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e63d6-139">参照</span><span class="sxs-lookup"><span data-stu-id="e63d6-139">See Also</span></span>  
 [<span data-ttu-id="e63d6-140">メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="e63d6-140">Message Context Properties</span></span>](../core/message-context-properties2.md)