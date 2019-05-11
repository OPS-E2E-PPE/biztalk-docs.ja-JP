---
title: 公開済み Web サービスを ASP.NET 4.0 を有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5613e22070b4103eb3744ebb8b7a0d008ca6df1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337973"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a><span data-ttu-id="689ff-102">公開済み Web サービスの ASP.NET 4.0 を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="689ff-102">How to Enable ASP.NET 4.0 for Published Web Services</span></span>
<span data-ttu-id="689ff-103">IIS で ASP.Net のバージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="689ff-103">Set the ASP.Net version in IIS.</span></span>

<span data-ttu-id="689ff-104">BizTalk Server Web サービス公開ウィザードは、.NET Framework に含まれているを ASP.NET で提供される機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="689ff-104">The BizTalk Server Web Services Publishing Wizard relies on functionality provided with ASP.NET, which is included with the .NET Framework.</span></span> <span data-ttu-id="689ff-105">ASP.Net のバージョンは、選択した .NET CLR バージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="689ff-105">The ASP.Net versions are included with the .NET CLR version you choose.</span></span> 

<span data-ttu-id="689ff-106">このトピックでは、.NET CLR バージョンを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="689ff-106">This topic shows you how to change the .NET CLR version.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="689ff-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="689ff-107">Prerequisites</span></span>

<span data-ttu-id="689ff-108">IIS に含まれて、 **Web サーバー (IIS)** オペレーティング システムの役割です。</span><span class="sxs-lookup"><span data-stu-id="689ff-108">IIS is included with the **Web Server (IIS)** role in the operating system.</span></span> <span data-ttu-id="689ff-109">この役割をインストールするときにも、ASP.NET の新しいバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="689ff-109">When you install this role, also select the newer version of ASP.NET.</span></span> 
  
## <a name="update-an-application-pool"></a><span data-ttu-id="689ff-110">アプリケーション プールを更新します。</span><span class="sxs-lookup"><span data-stu-id="689ff-110">Update an application pool</span></span>
  
1.  <span data-ttu-id="689ff-111">開いている**インターネット インフォメーション サービス (IIS) マネージャー**:</span><span class="sxs-lookup"><span data-stu-id="689ff-111">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="689ff-112">**サーバー マネージャー\*\*\*\*ツール**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-112">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="689ff-113">選択**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-113">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="689ff-114">サーバー名を展開し、選択**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-114">Expand the server name, and select **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="689ff-115">アプリケーション プールを選択し、開く、**基本設定**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-115">Select the app pool, and open the **Basic Settings**.</span></span>  
  
4. <span data-ttu-id="689ff-116">設定、 **.NET CLR バージョン**以降のバージョン、および選択を**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="689ff-116">Set the **.NET CLR version** to the newer version, and select **OK** to save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="689ff-117">Web.config ファイルのバージョンを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="689ff-117">You can also change the version in the web.config file.</span></span>
 
## <a name="allow-the-aspnet-extension"></a><span data-ttu-id="689ff-118">ASP.Net の拡張子を許可します。</span><span class="sxs-lookup"><span data-stu-id="689ff-118">Allow the ASP.Net extension</span></span>
  
1.  <span data-ttu-id="689ff-119">開いている**インターネット インフォメーション サービス (IIS) マネージャー**:</span><span class="sxs-lookup"><span data-stu-id="689ff-119">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="689ff-120">**サーバー マネージャー\*\*\*\*ツール**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-120">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="689ff-121">選択**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-121">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="689ff-122">サーバー名を選択し、ダブルクリック**ISAPI および CGI の制限**です。</span><span class="sxs-lookup"><span data-stu-id="689ff-122">Select the server name, and double-click **ISAPI and CGI Restrictions**.</span></span>  
  
3. <span data-ttu-id="689ff-123">ASP.NET は確認**許可**32 ビットおよび 64 ビット バージョン。</span><span class="sxs-lookup"><span data-stu-id="689ff-123">Confirm ASP.NET is **Allowed** for the 32-bit and 64-bit versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="689ff-124">参照</span><span class="sxs-lookup"><span data-stu-id="689ff-124">See Also</span></span>  
 [<span data-ttu-id="689ff-125">Web サービスを公開するための計画</span><span class="sxs-lookup"><span data-stu-id="689ff-125">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)