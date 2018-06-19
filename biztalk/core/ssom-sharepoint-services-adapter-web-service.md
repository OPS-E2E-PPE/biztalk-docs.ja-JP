---
title: 'SSOM: SharePoint Services アダプター Web サービス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 064d97b0-eb4b-4943-af01-5ca11e5f7029
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362af6cb7d2deca1afe02e7b871d07849ac3671
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276850"
---
# <a name="ssom-sharepoint-services-adapter-web-service"></a><span data-ttu-id="bdfe8-102">SSOM: SharePoint Services アダプター Web サービス</span><span class="sxs-lookup"><span data-stu-id="bdfe8-102">SSOM: SharePoint Services Adapter Web Service</span></span>
<span data-ttu-id="bdfe8-103">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターを使用して、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] からメッセージを受信し、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-103">Using the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter, you can receive messages from [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and send messages to [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bdfe8-104">廃止された [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web サービス アダプターは、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] サービス側オブジェクト モデル (SSOM) を採用しています。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-104">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service Adapter, which is deprecated, uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span> <span data-ttu-id="bdfe8-105">Web サービスがインストールされている、 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 、コンピューターと同じコンピューター上にあることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または別のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-105">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span> <span data-ttu-id="bdfe8-106">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は別々のコンピューターにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-106">It is recommended to install [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on separate computers.</span></span>  
  
 <span data-ttu-id="bdfe8-107">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アダプターのクライアント側オブジェクト モデル (CSOM) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-107">We recommend using the Client Side Object Model (CSOM) of the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter.</span></span> <span data-ttu-id="bdfe8-108">参照してください[CSOM: SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)と[付録 b: Microsoft SharePoint アダプターをインストールして](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)のインストールと構成オプション。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-108">See [CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md) and [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for installation and configuration options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdfe8-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bdfe8-109">In This Section</span></span>  
 [<span data-ttu-id="bdfe8-110">Windows SharePoint Services アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-110">What Is the Windows SharePoint Services Adapter?</span></span>](../core/what-is-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="bdfe8-111">設定して、Windows SharePoint Services アダプターの展開</span><span class="sxs-lookup"><span data-stu-id="bdfe8-111">Setting Up and Deploying the Windows SharePoint Services Adapter</span></span>](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="bdfe8-112">Windows SharePoint Services アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-112">Configuring the Windows SharePoint Services Adapter</span></span>](../core/configuring-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="bdfe8-113">Windows SharePoint Services アダプタのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="bdfe8-113">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)