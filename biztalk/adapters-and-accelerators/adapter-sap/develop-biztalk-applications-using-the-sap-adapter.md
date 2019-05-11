---
title: SAP アダプターを使用して BizTalk アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
ms.assetid: 4aa10897-a08e-4fc3-9c1f-40485d204273
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508a1050cde10e8407121036ee6e6f1038b00eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373518"
---
# <a name="develop-biztalk-applications-using-the-sap-adapter"></a><span data-ttu-id="b273a-102">SAP アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="b273a-102">Develop BizTalk applications using the SAP adapter</span></span>
<span data-ttu-id="b273a-103">BizTalk アプリケーションを開発する場合で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="b273a-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="b273a-104">スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、または、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b273a-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="b273a-105">CBR は、場所、SAP システムに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b273a-105">CBR can be used in scenarios where the messages being sent to the SAP system do not require any intensive processing.</span></span> <span data-ttu-id="b273a-106">たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b273a-106">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="b273a-107">、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b273a-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b273a-108">このセクションでは、BizTalk オーケストレーションを使用して、使用して SAP システムに対して操作を実行する方法の情報を提供します。、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b273a-108">This section provides information about using BizTalk orchestrations to perform operations on the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b273a-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] WCF バインドと対話できるアダプター。</span><span class="sxs-lookup"><span data-stu-id="b273a-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] adapter that can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b273a-110">使用する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="b273a-110">To use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="b273a-111">バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="b273a-111">For information about how to set binding properties, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b273a-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b273a-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b273a-113">SAP アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="b273a-113">Prerequisites to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
-   [<span data-ttu-id="b273a-114">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="b273a-114">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
  
-   [<span data-ttu-id="b273a-115">BizTalk Server を使用して SAP で Rfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="b273a-115">Invoke RFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-116">BizTalk Server を使用して SAP から受信 RFC 呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="b273a-116">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-117">BizTalk Server を使用して SAP の Trfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="b273a-117">Invoke tRFCs in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-118">BizTalk Server を使用して SAP から受信 tRFC 呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="b273a-118">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-inbound-trfc-calls-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-119">BizTalk Server を使用して SAP の BAPI トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b273a-119">Run BAPI Transactions in SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/run-bapi-transactions-in-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-120">BizTalk Server を使用して sap の Idoc を送信します。</span><span class="sxs-lookup"><span data-stu-id="b273a-120">Send IDOCs to SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/send-idocs-to-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-121">BizTalk Server を使用して SAP の Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="b273a-121">Receive IDOCs from SAP using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)  
  
-   [<span data-ttu-id="b273a-122">BizTalk Server を使用してトランザクション コンテキストでの SAP の Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="b273a-122">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b273a-123">参照</span><span class="sxs-lookup"><span data-stu-id="b273a-123">See Also</span></span>  
[<span data-ttu-id="b273a-124">SAP アプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="b273a-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)