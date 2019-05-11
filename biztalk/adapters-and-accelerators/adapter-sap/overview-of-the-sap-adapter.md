---
title: SAP アダプターの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271b733430b1b31828903add62bd8d71318abafb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373144"
---
# <a name="overview-of-the-sap-adapter"></a><span data-ttu-id="e6863-102">SAP アダプターの概要</span><span class="sxs-lookup"><span data-stu-id="e6863-102">Overview of the SAP adapter</span></span>
<span data-ttu-id="e6863-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF サービスとしての SAP システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="e6863-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes the SAP system as a WCF service.</span></span> <span data-ttu-id="e6863-104">アダプター クライアントは、アダプターを使用した SOAP メッセージを交換することで、SAP システムの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6863-104">Adapter clients can perform operations on the SAP system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="e6863-105">アダプターは WCF メッセージを使用し、操作を実行する SAP システムに適切な呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="e6863-105">The adapter consumes the WCF message and makes appropriate calls to the SAP system to perform the operation.</span></span> <span data-ttu-id="e6863-106">アダプターは、SOAP メッセージの形式でクライアントに SAP システムからの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="e6863-106">The adapter returns the response from the SAP system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="e6863-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WSDL の形式でメッセージの SOAP の構造を記述する SAP アイテム (RFC、BAPI、IDOC) の表面のメタデータ。</span><span class="sxs-lookup"><span data-stu-id="e6863-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces metadata of SAP artifacts (RFC, BAPI, IDOC) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="e6863-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。</span><span class="sxs-lookup"><span data-stu-id="e6863-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="e6863-109">詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="e6863-109">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to the SAP System in Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="e6863-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Unicode RFC ライブラリを librfc32u.dll を他のサポートの Dll を使用するだけでなく、SAP システムとの通信に使用します。</span><span class="sxs-lookup"><span data-stu-id="e6863-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the Unicode RFC library, librfc32u.dll, to communicate with the SAP system, in addition to using other supporting DLLs.</span></span> <span data-ttu-id="e6863-111">アダプターを必要とする SAP Dll の完全な一覧を参照してください、 [BizTalk Adapter Pack のインストール ガイド](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap)します。</span><span class="sxs-lookup"><span data-stu-id="e6863-111">For a complete list of SAP DLLs that the adapter requires, see the [BizTalk Adapter Pack installation guide](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap).</span></span> <span data-ttu-id="e6863-112">使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の方法で、SAP システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="e6863-112">You can use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to communicate with the SAP system in the following ways:</span></span>  
  
- <span data-ttu-id="e6863-113">BizTalk アプリケーションを開発しています。</span><span class="sxs-lookup"><span data-stu-id="e6863-113">By developing BizTalk applications.</span></span> <span data-ttu-id="e6863-114">参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="e6863-114">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) for more information.</span></span>  
  
- <span data-ttu-id="e6863-115">使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="e6863-115">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="e6863-116">参照してください[WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="e6863-116">See [Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).</span></span>
  
- <span data-ttu-id="e6863-117">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6863-117">By using the WCF channel model.</span></span> <span data-ttu-id="e6863-118">参照してください[WCF チャネル モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="e6863-118">See [Develop SAP applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e6863-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e6863-119">In This Section</span></span>  
  
-   [<span data-ttu-id="e6863-120">アダプターは、SAP システムにどのように接続でしょうか。</span><span class="sxs-lookup"><span data-stu-id="e6863-120">How Does the Adapter Connect to an SAP System?</span></span>](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [<span data-ttu-id="e6863-121">アダプター メタデータのサーフェスの SAP のしくみですか。</span><span class="sxs-lookup"><span data-stu-id="e6863-121">How Does the Adapter Surface SAP Metadata?</span></span>](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [<span data-ttu-id="e6863-122">どのような操作は、アダプターを使用して実行しますか?</span><span class="sxs-lookup"><span data-stu-id="e6863-122">What Operations Can be Performed Using the Adapter?</span></span>](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [<span data-ttu-id="e6863-123">アダプターでサポートされているその他の機能</span><span class="sxs-lookup"><span data-stu-id="e6863-123">Other Features Supported by the Adapter</span></span>](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="e6863-124">参照</span><span class="sxs-lookup"><span data-stu-id="e6863-124">See Also</span></span>  
 [<span data-ttu-id="e6863-125">BizTalk Adapter for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="e6863-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)