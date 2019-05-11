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
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="3761c-102">TIBCO Enterprise Message Service のメッセージ記述子のプロパティ</span><span class="sxs-lookup"><span data-stu-id="3761c-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>

## <a name="descriptor-properties-and-values"></a><span data-ttu-id="3761c-103">記述子のプロパティと値</span><span class="sxs-lookup"><span data-stu-id="3761c-103">Descriptor properties, and values</span></span>
<span data-ttu-id="3761c-104">次の表では、使用可能なメッセージ記述子 (TibcoEMSMD 構造) プロパティと、対応する型と値の完全なセットを示します。</span><span class="sxs-lookup"><span data-stu-id="3761c-104">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="3761c-105">名前</span><span class="sxs-lookup"><span data-stu-id="3761c-105">Name</span></span>|<span data-ttu-id="3761c-106">型</span><span class="sxs-lookup"><span data-stu-id="3761c-106">Type</span></span>|<span data-ttu-id="3761c-107">値</span><span class="sxs-lookup"><span data-stu-id="3761c-107">Value</span></span>|<span data-ttu-id="3761c-108">メモ</span><span class="sxs-lookup"><span data-stu-id="3761c-108">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="3761c-109">TibcoEMS します。関連付け Id</span><span class="sxs-lookup"><span data-stu-id="3761c-109">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="3761c-110">string</span><span class="sxs-lookup"><span data-stu-id="3761c-110">string</span></span>|||  
|<span data-ttu-id="3761c-111">TibcoEMS します。DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="3761c-111">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="3761c-112">string</span><span class="sxs-lookup"><span data-stu-id="3761c-112">string</span></span>|<span data-ttu-id="3761c-113">PERSISENT または NON-PERSISTENT のいずれか</span><span class="sxs-lookup"><span data-stu-id="3761c-113">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="3761c-114">TibcoEMS します。変換先</span><span class="sxs-lookup"><span data-stu-id="3761c-114">TibcoEMS .Destination</span></span>|<span data-ttu-id="3761c-115">string</span><span class="sxs-lookup"><span data-stu-id="3761c-115">string</span></span>||<span data-ttu-id="3761c-116">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3761c-116">Read-only</span></span>|  
|<span data-ttu-id="3761c-117">TibcoEMS します。有効期限</span><span class="sxs-lookup"><span data-stu-id="3761c-117">TibcoEMS .Expiration</span></span>|<span data-ttu-id="3761c-118">long</span><span class="sxs-lookup"><span data-stu-id="3761c-118">long</span></span>|||  
|<span data-ttu-id="3761c-119">TibcoEMS します。メッセージ Id</span><span class="sxs-lookup"><span data-stu-id="3761c-119">TibcoEMS .MessageID</span></span>|<span data-ttu-id="3761c-120">string</span><span class="sxs-lookup"><span data-stu-id="3761c-120">string</span></span>||<span data-ttu-id="3761c-121">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3761c-121">Read-only</span></span>|  
|<span data-ttu-id="3761c-122">TibcoEMS します。優先順位</span><span class="sxs-lookup"><span data-stu-id="3761c-122">TibcoEMS .Priority</span></span>|<span data-ttu-id="3761c-123">整数 (integer)</span><span class="sxs-lookup"><span data-stu-id="3761c-123">integer</span></span>|<span data-ttu-id="3761c-124">0 ~ 9</span><span class="sxs-lookup"><span data-stu-id="3761c-124">From 0 to 9</span></span>||  
|<span data-ttu-id="3761c-125">TibcoEMS します。再配信</span><span class="sxs-lookup"><span data-stu-id="3761c-125">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="3761c-126">boolean</span><span class="sxs-lookup"><span data-stu-id="3761c-126">boolean</span></span>||<span data-ttu-id="3761c-127">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3761c-127">Read-only</span></span>|  
|<span data-ttu-id="3761c-128">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="3761c-128">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="3761c-129">string</span><span class="sxs-lookup"><span data-stu-id="3761c-129">string</span></span>|<span data-ttu-id="3761c-130">変換先に似ています</span><span class="sxs-lookup"><span data-stu-id="3761c-130">Similar to Destination</span></span>||  
|<span data-ttu-id="3761c-131">TibcoEMS します。タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="3761c-131">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="3761c-132">long</span><span class="sxs-lookup"><span data-stu-id="3761c-132">long</span></span>||<span data-ttu-id="3761c-133">読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="3761c-133">Read-only</span></span>|  
  
 <span data-ttu-id="3761c-134">読み取り専用プロパティに Microsoft BizTalk Adapter for TIBCO EMS メッセージが配信されるときに、TIBCO Enterprise Message Service で設定されているこれらのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="3761c-134">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="3761c-135">メッセージの割り当て図形の式のことができますが、値を変更しても、メッセージには影響しません。</span><span class="sxs-lookup"><span data-stu-id="3761c-135">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="3761c-136">EMS メッセージから BizTalk Server メッセージに移動する必要がありますを他のプロパティは、プロパティの DLL を作成し、プロジェクトで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3761c-136">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="3761c-137">次のサンプル プロパティ スキーマには、使用するオーケストレーション、`JMSXDeliveryCount`メッセージ プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3761c-137">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
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
  
 <span data-ttu-id="3761c-138">ターゲットの名前空間が使用します。BizTalk Server メッセージまたは EMS メッセージは、この名前空間を使用するプロパティのみがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3761c-138">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="3761c-139">メッセージ コンテキスト プロパティの詳細については、BizTalk Server ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3761c-139">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3761c-140">参照</span><span class="sxs-lookup"><span data-stu-id="3761c-140">See Also</span></span>  
[<span data-ttu-id="3761c-141">TIBCO EMS メッセージ コンテキスト プロパティ</span><span class="sxs-lookup"><span data-stu-id="3761c-141">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)