---
title: "SAP アダプターによってどのような操作がサポートされている |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters, performing operations
ms.assetid: 4b676336-526d-42b9-9ff2-1a4f27df1a78
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee217572e0bf56e7a4f7e4810421befeb08bfc3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sap-adapter"></a><span data-ttu-id="eae9d-102">どのような操作、SAP アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eae9d-102">What operations are supported by the SAP adapter</span></span>
<span data-ttu-id="eae9d-103">アダプターのクライアントは、BizTalk プロジェクトを作成することで、WCF チャネル モデルを使用して、または WCF サービス モデルを使用して、SAP システムでの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="eae9d-103">Adapter clients can perform operations on the SAP system by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="eae9d-104">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アプリケーションがそれで呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="eae9d-104">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="eae9d-105">これらの操作がチャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eae9d-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="eae9d-106">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="eae9d-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="eae9d-107">メッセージの構造および各操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="eae9d-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
 <span data-ttu-id="eae9d-108">このセクションでは、SAP システムを使用して、サポートされる操作に関する情報を提供、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="eae9d-108">This section provides information about the operations supported on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eae9d-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eae9d-109">In This Section</span></span>  
  
-   [<span data-ttu-id="eae9d-110">SAP Rfc に対する操作</span><span class="sxs-lookup"><span data-stu-id="eae9d-110">Operations on RFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [<span data-ttu-id="eae9d-111">SAP の tRFCs に対する操作</span><span class="sxs-lookup"><span data-stu-id="eae9d-111">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [<span data-ttu-id="eae9d-112">SAP での Bapi の操作</span><span class="sxs-lookup"><span data-stu-id="eae9d-112">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [<span data-ttu-id="eae9d-113">SAP での Idoc に対する操作</span><span class="sxs-lookup"><span data-stu-id="eae9d-113">Operations on IDOCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)