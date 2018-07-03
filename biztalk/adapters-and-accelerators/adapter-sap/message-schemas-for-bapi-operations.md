---
title: BAPI 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPI operations, message schemas for
- BAPI operations, message structure for
- BAPI operations, message actions for
ms.assetid: ef4d88e8-f31a-4b68-a303-6885b6f8c083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 796e7beb428e6f9a4f0df63eff9cf45e9d5410bb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995219"
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="edb21-102">BAPI 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="edb21-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="edb21-103">次のセクションでは、メッセージ スキーマやメッセージのアクションでの Bapi を呼び出すために使用について説明します、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ビジネス オブジェクトのメソッドとして。</span><span class="sxs-lookup"><span data-stu-id="edb21-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="edb21-104">アダプターの RFC 操作として、Bapi を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="edb21-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="edb21-105">Rfc の呼び出しに使用するメッセージの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="edb21-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="edb21-106">常に、アダプターは、アダプターでの BAPI の起動方法に関係なく、SAP システムの RFC として、BAPI を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="edb21-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="edb21-107">方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Bapi を参照してください[SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="edb21-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  

## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="edb21-108">ビジネス オブジェクトの操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="edb21-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="edb21-109">次の表では、ビジネス オブジェクト メソッドとして BAPI を呼び出すために使用するメッセージ スキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="edb21-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  

|<span data-ttu-id="edb21-110">演算</span><span class="sxs-lookup"><span data-stu-id="edb21-110">Operation</span></span>|<span data-ttu-id="edb21-111">XML の構造体</span><span class="sxs-lookup"><span data-stu-id="edb21-111">XML Structure</span></span>|<span data-ttu-id="edb21-112">説明</span><span class="sxs-lookup"><span data-stu-id="edb21-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="edb21-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="edb21-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="edb21-114">SAP システムのビジネス オブジェクト メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="edb21-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="edb21-115">インポート、変更、およびテーブル パラメーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="edb21-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="edb21-116">[BUSOBJ_METHOD]応答</span><span class="sxs-lookup"><span data-stu-id="edb21-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="edb21-117">ビジネス オブジェクト メソッドの応答。</span><span class="sxs-lookup"><span data-stu-id="edb21-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="edb21-118">エクスポート、変更、およびテーブル パラメーターがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="edb21-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="edb21-119">**注**応答メッセージに表示しないテーブル パラメーターの既定では、します。</span><span class="sxs-lookup"><span data-stu-id="edb21-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="edb21-120">応答メッセージのテーブルのパラメーターが必要な場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="edb21-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  

 <span data-ttu-id="edb21-121">[バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.Sap/2007/03します。</span><span class="sxs-lookup"><span data-stu-id="edb21-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="edb21-122">[BUSOBJ_METHOD] ビジネス オブジェクト メソッドの名前を =たとえば、CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="edb21-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="edb21-123">[IN_PARAM_NAME] = BAPI インポートのパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="edb21-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  

 <span data-ttu-id="edb21-124">[OUT_PARAM_NAME] = BAPI エクスポートのパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="edb21-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  

 <span data-ttu-id="edb21-125">[INOUT_PARAM_NAME] パラメーターを変更する BAPI の名前を = です。</span><span class="sxs-lookup"><span data-stu-id="edb21-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  

 <span data-ttu-id="edb21-126">[TABLE_PARAM_NAME] = BAPI テーブル パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="edb21-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  

 <span data-ttu-id="edb21-127">[STRUCT_PARAM_NAME] = BAPI 構造体のパラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="edb21-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  

## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="edb21-128">ビジネス オブジェクトの操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="edb21-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="edb21-129">次の表では、ビジネス オブジェクト メソッドとして Bapi を呼び出すに使用されるメッセージのアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="edb21-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  


|        <span data-ttu-id="edb21-130">演算</span><span class="sxs-lookup"><span data-stu-id="edb21-130">Operation</span></span>         |                            <span data-ttu-id="edb21-131">メッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="edb21-131">Message Action</span></span>                             |                                                   <span data-ttu-id="edb21-132">例</span><span class="sxs-lookup"><span data-stu-id="edb21-132">Example</span></span>                                                    |
|--------------------------|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="edb21-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="edb21-133">[BUSOBJ_METHOD]</span></span>      |     <span data-ttu-id="edb21-134">[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="edb21-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>      |     http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2      |
| <span data-ttu-id="edb21-135">[BUSOBJ_METHOD]応答</span><span class="sxs-lookup"><span data-stu-id="edb21-135">[BUSOBJ_METHOD] Response</span></span> | <span data-ttu-id="edb21-136">[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="edb21-136">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span> | http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response |

 <span data-ttu-id="edb21-137">[バージョン] = メッセージ バージョン文字列。たとえば、http://Microsoft.LobServices.Sap/2007/03します。</span><span class="sxs-lookup"><span data-stu-id="edb21-137">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  

 <span data-ttu-id="edb21-138">[BUSOBJ_NAME]、ビジネス オブジェクトの名前を =たとえば、BUS2032 です。</span><span class="sxs-lookup"><span data-stu-id="edb21-138">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  

 <span data-ttu-id="edb21-139">[BUSOBJ_METHOD] ビジネス オブジェクトのメソッドを =たとえば、CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="edb21-139">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  

 <span data-ttu-id="edb21-140">[BAPI_RFC_NAME] BAPI; の名前を「RFC を =たとえば、BAPI_SALESORDER_CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="edb21-140">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  

## <a name="see-also"></a><span data-ttu-id="edb21-141">参照</span><span class="sxs-lookup"><span data-stu-id="edb21-141">See Also</span></span>  
 [<span data-ttu-id="edb21-142">メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="edb21-142">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)