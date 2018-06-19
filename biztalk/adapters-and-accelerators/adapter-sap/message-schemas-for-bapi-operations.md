---
title: BAPI 操作のメッセージ スキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 999e60a7e2cac827031ea2a19f9482d9da0baaa6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217450"
---
# <a name="message-schemas-for-bapi-operations"></a><span data-ttu-id="52d2b-102">BAPI 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="52d2b-102">Message Schemas for BAPI Operations</span></span>
<span data-ttu-id="52d2b-103">次の説明は、メッセージ スキーマやメッセージのアクションでの Bapi の呼び出しに使用、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]ビジネス オブジェクトのメソッドとして。</span><span class="sxs-lookup"><span data-stu-id="52d2b-103">The following sections describe the message schemas and message actions used to invoke BAPIs on the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as methods of business objects.</span></span> <span data-ttu-id="52d2b-104">Bapi のアダプターでの RFC 操作として呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="52d2b-104">You can also invoke BAPIs as RFC operations on the adapter.</span></span> <span data-ttu-id="52d2b-105">Rfc 呼び出しに使用されるメッセージの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-105">For more information about the messages used to invoke RFCs, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span> <span data-ttu-id="52d2b-106">常に、アダプターは、アダプターでの BAPI の起動方法に関係なく、SAP システムで RFC として、BAPI を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="52d2b-106">Regardless of how you invoke a BAPI on the adapter, the adapter always invokes the BAPI as an RFC on the SAP system.</span></span> <span data-ttu-id="52d2b-107">方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポートの Bapi を参照してください[SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-107">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="message-structure-for-business-object-operations"></a><span data-ttu-id="52d2b-108">ビジネス オブジェクトの操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="52d2b-108">Message Structure for Business Object Operations</span></span>  
 <span data-ttu-id="52d2b-109">次の表は、ビジネス オブジェクトのメソッドとして BAPI を呼び出すために使用するメッセージ スキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="52d2b-109">The following table shows the message schemas used to invoke a BAPI as a business object method.</span></span>  
  
|<span data-ttu-id="52d2b-110">操作</span><span class="sxs-lookup"><span data-stu-id="52d2b-110">Operation</span></span>|<span data-ttu-id="52d2b-111">XML データ構造</span><span class="sxs-lookup"><span data-stu-id="52d2b-111">XML Structure</span></span>|<span data-ttu-id="52d2b-112">Description</span><span class="sxs-lookup"><span data-stu-id="52d2b-112">Description</span></span>|  
|---------------|-------------------|-----------------|  
|<span data-ttu-id="52d2b-113">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="52d2b-113">[BUSOBJ_METHOD]</span></span>|`<[BUSOBJ_METHOD] xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <IN1_PARAM_NAME>v1</IN1_PARAM_NAME>   <IN2_PARAM_NAME>v2</IN2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]>`|<span data-ttu-id="52d2b-114">SAP システムでビジネス オブジェクト メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="52d2b-114">Invoke a business object method on an SAP system.</span></span><br /><br /> <span data-ttu-id="52d2b-115">インポート、変更、およびテーブルのパラメーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="52d2b-115">Import, changing, and table parameters are supported.</span></span>|  
|<span data-ttu-id="52d2b-116">[BUSOBJ_METHOD]応答</span><span class="sxs-lookup"><span data-stu-id="52d2b-116">[BUSOBJ_METHOD] Response</span></span>|`<[BUSOBJ_METHOD]Response xmlns="[VERSION]/Bapi/[BUSOBJ]/">   <OUT1_PARAM_NAME>v1</OUT1_PARAM_NAME>   <OUT2_PARAM_NAME>v2</OUT2_PARAM_NAME>   …   <INOUT1_PARAM_NAME>v3</INOUT1_PARAM_NAME>   <INOUT2_PARAM_NAME>v4</INOUT2_PARAM_NAME>   …   <TABLE1_PARAM_NAME xmlns="[VERSION]/Types/Rfc/">     <STRUCT1_PARAM_NAME>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </STRUCT1_PARAM_NAME>     …   </TABLE1_PARAM_NAME>   … </[BUSOBJ_METHOD]Response>`|<span data-ttu-id="52d2b-117">ビジネス オブジェクト メソッドの応答です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-117">Business object method response.</span></span><br /><br /> <span data-ttu-id="52d2b-118">エクスポート、変更すると、およびテーブル パラメーターはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="52d2b-118">Export, changing, and table parameters are supported.</span></span><br /><br /> <span data-ttu-id="52d2b-119">**注**応答メッセージに表示されませんテーブル パラメーター既定では、します。</span><span class="sxs-lookup"><span data-stu-id="52d2b-119">**Note** By default, table parameters are not surfaced in the response message.</span></span> <span data-ttu-id="52d2b-120">応答メッセージ内のテーブルのパラメーターを必要とする場合は、要求メッセージ内で空のテーブルのパラメーターを渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="52d2b-120">If you require table parameters in response message, you must pass empty table parameters in the request message.</span></span>|  
  
 <span data-ttu-id="52d2b-121">[バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-121">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="52d2b-122">[BUSOBJ_METHOD]、ビジネス オブジェクトのメソッドの名前を =たとえば、CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-122">[BUSOBJ_METHOD] = The name of a business object method; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="52d2b-123">[IN_PARAM_NAME] BAPI インポートのパラメーターの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-123">[IN_PARAM_NAME] =The name of a BAPI import parameter.</span></span>  
  
 <span data-ttu-id="52d2b-124">[OUT_PARAM_NAME] BAPI エクスポート パラメーターの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-124">[OUT_PARAM_NAME] = The name of a BAPI export parameter.</span></span>  
  
 <span data-ttu-id="52d2b-125">[INOUT_PARAM_NAME] パラメーターを変更する BAPI の名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-125">[INOUT_PARAM_NAME] = The name of a BAPI changing parameter.</span></span>  
  
 <span data-ttu-id="52d2b-126">[TABLE_PARAM_NAME] BAPI テーブル パラメーターの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-126">[TABLE_PARAM_NAME] = The name of a BAPI table parameter.</span></span>  
  
 <span data-ttu-id="52d2b-127">[STRUCT_PARAM_NAME] BAPI 構造パラメーターの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-127">[STRUCT_PARAM_NAME] = The name of a BAPI structure parameter.</span></span>  
  
## <a name="message-actions-for-business-object-operations"></a><span data-ttu-id="52d2b-128">ビジネス オブジェクトの操作のメッセージの動作</span><span class="sxs-lookup"><span data-stu-id="52d2b-128">Message Actions for Business Object Operations</span></span>  
 <span data-ttu-id="52d2b-129">次の表は、ビジネス オブジェクト メソッドとしての Bapi の呼び出しに使用されるメッセージのアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="52d2b-129">The following table shows the message actions that are used to invoke BAPIs as business object methods.</span></span>  
  
|<span data-ttu-id="52d2b-130">操作</span><span class="sxs-lookup"><span data-stu-id="52d2b-130">Operation</span></span>|<span data-ttu-id="52d2b-131">メッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="52d2b-131">Message Action</span></span>|<span data-ttu-id="52d2b-132">例</span><span class="sxs-lookup"><span data-stu-id="52d2b-132">Example</span></span>|  
|---------------|--------------------|-------------|  
|<span data-ttu-id="52d2b-133">[BUSOBJ_METHOD]</span><span class="sxs-lookup"><span data-stu-id="52d2b-133">[BUSOBJ_METHOD]</span></span>|<span data-ttu-id="52d2b-134">[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span><span class="sxs-lookup"><span data-stu-id="52d2b-134">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]</span></span>|<span data-ttu-id="52d2b-135">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span><span class="sxs-lookup"><span data-stu-id="52d2b-135">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2</span></span>|  
|<span data-ttu-id="52d2b-136">[BUSOBJ_METHOD]応答</span><span class="sxs-lookup"><span data-stu-id="52d2b-136">[BUSOBJ_METHOD] Response</span></span>|<span data-ttu-id="52d2b-137">[バージョン]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="52d2b-137">[VERSION]/Bapi/[BUSOBJ_NAME]/[BUSOBJ_METHOD]/[BAPI_RFC_NAME]/response</span></span>|<span data-ttu-id="52d2b-138">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response</span><span class="sxs-lookup"><span data-stu-id="52d2b-138">http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2/response</span></span>|  
  
 <span data-ttu-id="52d2b-139">[バージョン]、メッセージのバージョン文字列を =たとえば、http://Microsoft.LobServices.Sap/2007/03 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-139">[VERSION] = The message version string; for example, http://Microsoft.LobServices.Sap/2007/03.</span></span>  
  
 <span data-ttu-id="52d2b-140">[BUSOBJ_NAME]、ビジネス オブジェクトの名前を =たとえば、BUS2032 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-140">[BUSOBJ_NAME] = The name of the business object; for example, BUS2032.</span></span>  
  
 <span data-ttu-id="52d2b-141">[BUSOBJ_METHOD] ビジネス オブジェクトのメソッドを =たとえば、CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-141">[BUSOBJ_METHOD] = The method of the business object; for example, CREATEFROMDAT2.</span></span>  
  
 <span data-ttu-id="52d2b-142">[BAPI_RFC_NAME] BAPI; の名前を RFC を =たとえば、BAPI_SALESORDER_CREATEFROMDAT2 です。</span><span class="sxs-lookup"><span data-stu-id="52d2b-142">[BAPI_RFC_NAME] = The RFC name for the BAPI; for example, BAPI_SALESORDER_CREATEFROMDAT2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d2b-143">参照</span><span class="sxs-lookup"><span data-stu-id="52d2b-143">See Also</span></span>  
 [<span data-ttu-id="52d2b-144">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="52d2b-144">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)