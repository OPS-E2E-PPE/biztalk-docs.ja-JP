---
title: 特別な操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, special operations surfaced by the SAP adapter
ms.assetid: 8725fe63-6ff4-49c8-b386-d4c67e2be440
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 424a3721b2ff12fb14be18c7d11a46de9a116338
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372963"
---
# <a name="special-operations"></a><span data-ttu-id="47042-102">特別な操作</span><span class="sxs-lookup"><span data-stu-id="47042-102">Special Operations</span></span>
<span data-ttu-id="47042-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスのいくつかの特別な操作です。</span><span class="sxs-lookup"><span data-stu-id="47042-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several special operations.</span></span> <span data-ttu-id="47042-104">これらの操作は、SAP システムの成果物には基づいていません。</span><span class="sxs-lookup"><span data-stu-id="47042-104">These operations are not based on SAP system artifacts.</span></span> <span data-ttu-id="47042-105">アダプターのクライアント アプリケーションの機能を提供するは表示されます。</span><span class="sxs-lookup"><span data-stu-id="47042-105">They are surfaced to provide functionality for adapter client applications.</span></span> <span data-ttu-id="47042-106">特別な操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="47042-106">The special operations are:</span></span>  
  
- <span data-ttu-id="47042-107">**RfcGetAttributes**します。</span><span class="sxs-lookup"><span data-stu-id="47042-107">**RfcGetAttributes**.</span></span> <span data-ttu-id="47042-108">この操作は、RFC ノードの下に表示され、RFC SDK の機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="47042-108">This operation is surfaced under the RFC node and exposes functionality of the RFC SDK.</span></span> <span data-ttu-id="47042-109">RFC 接続に関する次の情報が提供します。</span><span class="sxs-lookup"><span data-stu-id="47042-109">It provides the following information about the RFC connection:</span></span>  
  
  - <span data-ttu-id="47042-110">システム ID</span><span class="sxs-lookup"><span data-stu-id="47042-110">The system ID</span></span>  
  
  - <span data-ttu-id="47042-111">パートナーのコード ページ</span><span class="sxs-lookup"><span data-stu-id="47042-111">The partner code page</span></span>  
  
  - <span data-ttu-id="47042-112">言語</span><span class="sxs-lookup"><span data-stu-id="47042-112">The language</span></span>  
  
    <span data-ttu-id="47042-113">そのメッセージのスキーマを含む RfcGetAttributes 操作に関する詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="47042-113">For more information about the RfcGetAttributes operation including its message schema, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
- <span data-ttu-id="47042-114">**RfcConfirmTransID**します。</span><span class="sxs-lookup"><span data-stu-id="47042-114">**RfcConfirmTransID**.</span></span> <span data-ttu-id="47042-115">この操作は、TRFC ノードの下に表示され、RFC SDK の機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="47042-115">This operation is surfaced under the TRFC node and exposes RFC SDK functionality.</span></span> <span data-ttu-id="47042-116">SAP システムでの SAP トランザクション Id を確認するのにには、この操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="47042-116">You use this operation to confirm SAP transaction IDs on the SAP system.</span></span>  
  
   <span data-ttu-id="47042-117">RfcConfirmTransID 操作を使用して、そのメッセージ スキーマの詳細についてを参照してください。 詳細について[SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="47042-117">For more information about how to use the RfcConfirmTransID operation and about its message schema, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
- <span data-ttu-id="47042-118">**文字列の SapAdapterUtilities.ConvertGuidToTid(Guid)** します。</span><span class="sxs-lookup"><span data-stu-id="47042-118">**string SapAdapterUtilities.ConvertGuidToTid(Guid)**.</span></span> <span data-ttu-id="47042-119">これは、SAP アダプターのアセンブリによって公開されるパブリック メソッドです。</span><span class="sxs-lookup"><span data-stu-id="47042-119">This is a public method exposed by the SAP adapter assembly.</span></span> <span data-ttu-id="47042-120">(その操作がないアダプターします。)指定された GUID にマップされている ID (TID) SAP トランザクションを返します。</span><span class="sxs-lookup"><span data-stu-id="47042-120">(It is not an operation surfaced by the adapter.) It returns the SAP transaction ID (TID) mapped to the specified GUID.</span></span>  
  
   <span data-ttu-id="47042-121">内部的には、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] GUID に SAP システムに関する SAP トランザクション ID (TID) 作業 (LUW) の論理単位を識別するをマップします。</span><span class="sxs-lookup"><span data-stu-id="47042-121">Internally, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] maps the SAP transaction ID (TID) that identifies a logical unit of work (LUW) on the SAP system to a GUID.</span></span> <span data-ttu-id="47042-122">この GUID がクライアントに公開アダプター、tRFC (LUW) をコミットできるように、SAP システムでは、その TID を確認する RfcConfirmTransID 操作を呼び出すことによって。</span><span class="sxs-lookup"><span data-stu-id="47042-122">This GUID is exposed to adapter clients, so that they can commit a tRFC (LUW) by invoking the RfcConfirmTransID operation to confirm its TID on the SAP system.</span></span>  
  
   <span data-ttu-id="47042-123">ただし、一部のシナリオに関連付けられた、tRFC TID を必要があります。</span><span class="sxs-lookup"><span data-stu-id="47042-123">However, for some scenarios, you may need the TID that is associated with a tRFC.</span></span> <span data-ttu-id="47042-124">たとえば、特定の問題をトラブルシューティングする SAP システムで LUW たい場合があります。</span><span class="sxs-lookup"><span data-stu-id="47042-124">For example, you may want to identify the LUW on the SAP system to troubleshoot an issue.</span></span> <span data-ttu-id="47042-125">このようなシナリオを呼び出すことができます**ConvertGuidToTid**します。</span><span class="sxs-lookup"><span data-stu-id="47042-125">For these scenarios you can call **ConvertGuidToTid**.</span></span> <span data-ttu-id="47042-126">使用する**ConvertGuidToTid**コードをプロジェクトに SAP アダプターのアセンブリへの参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47042-126">To use **ConvertGuidToTid** in your code, you must add a reference to the SAP adapter assembly to your project.</span></span>  
  
   <span data-ttu-id="47042-127">Trfc を呼び出す方法の詳細については、次を参照してください。 [SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="47042-127">For more information about invoking tRFCs, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span> <span data-ttu-id="47042-128">次の例を呼び出す方法を示しています。 **ConvertGuidToTid**します。</span><span class="sxs-lookup"><span data-stu-id="47042-128">The following example shows how to invoke **ConvertGuidToTid**.</span></span>  
  
  ```  
  // messageGuid is the GUID associated with a tRFC or IDOC  
  
  string tid = SapAdapterUtilities.ConvertGuidToTid(messageGuid);  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="47042-129">参照</span><span class="sxs-lookup"><span data-stu-id="47042-129">See Also</span></span>  
 [<span data-ttu-id="47042-130">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="47042-130">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)