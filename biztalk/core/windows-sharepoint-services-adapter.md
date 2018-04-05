---
title: Windows SharePoint Services アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters
ms.assetid: cbfc9bf3-912d-4849-ba8c-07a116888bbd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f1365b11ce93717223ec35e395165e8d0e551
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter"></a><span data-ttu-id="7b0d3-102">Windows SharePoint Services アダプタ</span><span class="sxs-lookup"><span data-stu-id="7b0d3-102">Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="7b0d3-103">Microsoft Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプターを使用すると、BizTalk Server を Windows SharePoint Services および Microsoft Office InfoPath と密接に統合できます。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Microsoft Windows SharePoint Services provides a tighter integration of BizTalk Server with Windows SharePoint Services and Microsoft Office.</span></span> <span data-ttu-id="7b0d3-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションで Windows SharePoint Services アダプターを使用した場合、次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-104">Using the Windows SharePoint Services adapter in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution provides you with the following capabilities:</span></span>  
  
-   <span data-ttu-id="7b0d3-105">Windows SharePoint Services 経由の入力メッセージと出力メッセージへの簡単なアクセス。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-105">Easy access to input and output messages through Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="7b0d3-106">Microsoft Office InfoPath などの Office アプリケーションを使用した XML メッセージの編集機能。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-106">The ability to edit XML messages by using Office applications such as Microsoft Office InfoPath.</span></span>  
  
-   <span data-ttu-id="7b0d3-107">InfoPath との XML メッセージの双方向の変換。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-107">Two-way transformations of XML messages to and from InfoPath.</span></span>  
  
 <span data-ttu-id="7b0d3-108">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-108">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter consists of the following components:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b0d3-109">CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプター</span><span class="sxs-lookup"><span data-stu-id="7b0d3-109">CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter</span></span>|<span data-ttu-id="7b0d3-110">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] クライアント側オブジェクト モデル (CSOM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-110">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="7b0d3-111">このアダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-111">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="7b0d3-112">追加のインストール手順はありません。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-112">There are no additional installation steps.</span></span><br /><br /> <span data-ttu-id="7b0d3-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール***自動的に***、SharePoint クライアント オブジェクト モデル、再頒布可能でもあるで利用可能なインストール[http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)です。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-113">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation ***automatically*** installs the SharePoint Client Object Model Redistributable, which is also available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>|  
|<span data-ttu-id="7b0d3-114">SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サービス</span><span class="sxs-lookup"><span data-stu-id="7b0d3-114">SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service</span></span>|<span data-ttu-id="7b0d3-115">**使用しません**。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-115">**Deprecated**.</span></span> <span data-ttu-id="7b0d3-116">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] サービス側オブジェクト モデル (SSOM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-116">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="7b0d3-117">Web サービスがインストールされている、 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 、コンピューターと同じコンピューター上にあることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または別のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-117">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="7b0d3-118">Web サービスをインストールするには、実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]へのインストール、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]コンピューターとチェック**Windows SharePoint Services アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-118">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span>|  
  
 <span data-ttu-id="7b0d3-119">[付録 b: Microsoft SharePoint アダプターをインストールして](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)について詳しく説明、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-119">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides more information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b0d3-120">現時点では、フェデレーション認証はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-120">Currently, federated authentication is not supported.</span></span> <span data-ttu-id="7b0d3-121">ユーザー名とパスワードのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7b0d3-121">Only Username and Password are supported.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b0d3-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7b0d3-122">In This Section</span></span>  
  
-   [<span data-ttu-id="7b0d3-123">SharePoint Services アダプターの CSOM:</span><span class="sxs-lookup"><span data-stu-id="7b0d3-123">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="7b0d3-124">SSOM: SharePoint Services アダプター Web サービス</span><span class="sxs-lookup"><span data-stu-id="7b0d3-124">SSOM: SharePoint Services Adapter Web Service</span></span>](../core/ssom-sharepoint-services-adapter-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b0d3-125">参照</span><span class="sxs-lookup"><span data-stu-id="7b0d3-125">See Also</span></span>  
 <span data-ttu-id="7b0d3-126">[アダプターを使用します。](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="7b0d3-126">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="7b0d3-127">BizTalk Server アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="7b0d3-127">Developing BizTalk Server Applications</span></span>](../core/developing-biztalk-server-applications.md)