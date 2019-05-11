---
title: SAP アダプターによってサポートされる操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, performing operations
ms.assetid: 4b676336-526d-42b9-9ff2-1a4f27df1a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b42afcdc1c42febe208230307f6d4cd7cbede5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372041"
---
# <a name="what-operations-are-supported-by-the-sap-adapter"></a><span data-ttu-id="7bd2c-102">SAP アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="7bd2c-102">What operations are supported by the SAP adapter</span></span>
<span data-ttu-id="7bd2c-103">アダプター クライアントは、BizTalk プロジェクトを作成して、WCF チャネル モデルを使用して、または WCF サービス モデルを使用して、SAP システムの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-103">Adapter clients can perform operations on the SAP system by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="7bd2c-104">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アプリケーションは、それを呼び出すことができ、アプリケーションで呼び出すことができます、さらに、操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-104">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="7bd2c-105">これらの操作は、チャネル経由で SOAP メッセージを送信することによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="7bd2c-106">応答が必要な場合、同じチャネル経由で SOAP メッセージで返されます。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="7bd2c-107">メッセージの構造とそれぞれの操作に関連付けられている SOAP アクションについては、次を参照してください。[メッセージと BizTalk adapter for mySAP Business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
 <span data-ttu-id="7bd2c-108">このセクションで、SAP システムを使用してサポートされる操作について説明します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7bd2c-108">This section provides information about the operations supported on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bd2c-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7bd2c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7bd2c-110">SAP で Rfc に対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd2c-110">Operations on RFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [<span data-ttu-id="7bd2c-111">SAP の Trfc に対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd2c-111">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [<span data-ttu-id="7bd2c-112">Sap Bapi に対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd2c-112">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [<span data-ttu-id="7bd2c-113">Sap Idoc に対する操作</span><span class="sxs-lookup"><span data-stu-id="7bd2c-113">Operations on IDOCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)