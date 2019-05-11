---
title: SSOM:SharePoint Services アダプター Web サービス |Microsoft Docs
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
ms.openlocfilehash: 7c158608b9b34503496020d331c969b36f10a235
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398943"
---
# <a name="ssom-sharepoint-services-adapter-web-service"></a><span data-ttu-id="7bd33-102">SSOM:SharePoint Services アダプター Web サービス</span><span class="sxs-lookup"><span data-stu-id="7bd33-102">SSOM: SharePoint Services Adapter Web Service</span></span>
<span data-ttu-id="7bd33-103">使用して、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプターからメッセージを受信できます[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]にメッセージを送信および[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7bd33-103">Using the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter, you can receive messages from [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and send messages to [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7bd33-104">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]非推奨とされますが、使用して Web サービス アダプター、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]サービス側オブジェクト モデル (SSOM)。</span><span class="sxs-lookup"><span data-stu-id="7bd33-104">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service Adapter, which is deprecated, uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span> <span data-ttu-id="7bd33-105">Web サービスが [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] コンピューターにインストールされます。このコンピューターは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンピューターと同じでも別でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="7bd33-105">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span> <span data-ttu-id="7bd33-106">インストールすることをお勧め[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を別々 のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="7bd33-106">It is recommended to install [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on separate computers.</span></span>  
  
 <span data-ttu-id="7bd33-107">クライアント側オブジェクト モデル (CSOM) の使用をお勧め、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アダプター。</span><span class="sxs-lookup"><span data-stu-id="7bd33-107">We recommend using the Client Side Object Model (CSOM) of the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter.</span></span> <span data-ttu-id="7bd33-108">参照してください[CSOM:SharePoint Services アダプター](../core/csom-sharepoint-services-adapter.md)と[付録 b:Microsoft SharePoint アダプターのインストール](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)のインストールと構成オプション。</span><span class="sxs-lookup"><span data-stu-id="7bd33-108">See [CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md) and [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for installation and configuration options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bd33-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7bd33-109">In This Section</span></span>  
 [<span data-ttu-id="7bd33-110">Windows SharePoint Services アダプターについて </span><span class="sxs-lookup"><span data-stu-id="7bd33-110">What Is the Windows SharePoint Services Adapter?</span></span>](../core/what-is-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="7bd33-111">Windows SharePoint Services アダプターの設定と展開</span><span class="sxs-lookup"><span data-stu-id="7bd33-111">Setting Up and Deploying the Windows SharePoint Services Adapter</span></span>](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="7bd33-112">Windows SharePoint Services アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="7bd33-112">Configuring the Windows SharePoint Services Adapter</span></span>](../core/configuring-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="7bd33-113">Windows SharePoint Services アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="7bd33-113">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)