---
title: SAP アダプターの概要 |Microsoft ドキュメント
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
ms.openlocfilehash: 3031bdf1317d96f64f1ea247c6f8cbf83e1688c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963032"
---
# <a name="overview-of-the-sap-adapter"></a><span data-ttu-id="25361-102">SAP アダプターの概要</span><span class="sxs-lookup"><span data-stu-id="25361-102">Overview of the SAP adapter</span></span>
<span data-ttu-id="25361-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を WCF サービスとして SAP システムを公開します。</span><span class="sxs-lookup"><span data-stu-id="25361-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes the SAP system as a WCF service.</span></span> <span data-ttu-id="25361-104">アダプターのクライアントは、アダプターと SOAP メッセージを交換することで、SAP システムで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="25361-104">Adapter clients can perform operations on the SAP system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="25361-105">アダプターは WCF メッセージを処理して、操作を実行する SAP システムへの適切な呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="25361-105">The adapter consumes the WCF message and makes appropriate calls to the SAP system to perform the operation.</span></span> <span data-ttu-id="25361-106">アダプターは、SOAP メッセージの形式でクライアントに SAP システムからの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="25361-106">The adapter returns the response from the SAP system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="25361-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WSDL の形でメッセージの SOAP の構造を記述する SAP アイテム (RFC、BAPI、IDOC) のサーフェス メタデータ。</span><span class="sxs-lookup"><span data-stu-id="25361-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces metadata of SAP artifacts (RFC, BAPI, IDOC) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="25361-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアント操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。</span><span class="sxs-lookup"><span data-stu-id="25361-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="25361-109">詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="25361-109">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to the SAP System in Visual Studio](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="25361-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Unicode RFC ライブラリ、librfc32u.dll を使用してサポートするその他の Dll を使うことに加えて、SAP システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="25361-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the Unicode RFC library, librfc32u.dll, to communicate with the SAP system, in addition to using other supporting DLLs.</span></span> <span data-ttu-id="25361-111">アダプターを必要とする SAP Dll の完全な一覧を参照してください、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。</span><span class="sxs-lookup"><span data-stu-id="25361-111">For a complete list of SAP DLLs that the adapter requires, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide.</span></span> <span data-ttu-id="25361-112">インストール ガイドがインストールされている通常\<インストール ドライブ:\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="25361-112">The installation guide is typically installed at \<installation drive:\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span> <span data-ttu-id="25361-113">使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のように、SAP システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="25361-113">You can use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to communicate with the SAP system in the following ways:</span></span>  
  
-   <span data-ttu-id="25361-114">BizTalk アプリケーションを開発することによりします。</span><span class="sxs-lookup"><span data-stu-id="25361-114">By developing BizTalk applications.</span></span> <span data-ttu-id="25361-115">参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="25361-115">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md) for more information.</span></span>  
  
-   <span data-ttu-id="25361-116">使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="25361-116">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="25361-117">参照してください[WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="25361-117">See [Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).</span></span>
  
-   <span data-ttu-id="25361-118">WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="25361-118">By using the WCF channel model.</span></span> <span data-ttu-id="25361-119">参照してください[WCF チャネル モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="25361-119">See [Develop SAP applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="25361-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="25361-120">In This Section</span></span>  
  
-   [<span data-ttu-id="25361-121">アダプターは、SAP システムにどのように接続しますか。</span><span class="sxs-lookup"><span data-stu-id="25361-121">How Does the Adapter Connect to an SAP System?</span></span>](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [<span data-ttu-id="25361-122">画面の SAP メタデータのアダプターがどのようにしますか。</span><span class="sxs-lookup"><span data-stu-id="25361-122">How Does the Adapter Surface SAP Metadata?</span></span>](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [<span data-ttu-id="25361-123">どのような操作をアダプターであるを使用して実行しますか?</span><span class="sxs-lookup"><span data-stu-id="25361-123">What Operations Can be Performed Using the Adapter?</span></span>](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [<span data-ttu-id="25361-124">アダプターでサポートされているその他の機能</span><span class="sxs-lookup"><span data-stu-id="25361-124">Other Features Supported by the Adapter</span></span>](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="25361-125">参照</span><span class="sxs-lookup"><span data-stu-id="25361-125">See Also</span></span>  
 [<span data-ttu-id="25361-126">BizTalk Adapter for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="25361-126">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)