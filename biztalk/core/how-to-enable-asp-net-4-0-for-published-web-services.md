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
ms.openlocfilehash: e68b8eef114828ad181e83ce0c7acd70a5545e0d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254082"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a><span data-ttu-id="a1424-102">公開済み Web サービスの ASP.NET 4.0 を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a1424-102">How to Enable ASP.NET 4.0 for Published Web Services</span></span>
<span data-ttu-id="a1424-103">IIS で ASP.Net のバージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1424-103">Set the ASP.Net version in IIS.</span></span>

<span data-ttu-id="a1424-104">BizTalk Server Web サービス公開ウィザードは、.NET Framework に含まれているを ASP.NET で提供される機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="a1424-104">The BizTalk Server Web Services Publishing Wizard relies on functionality provided with ASP.NET, which is included with the .NET Framework.</span></span> <span data-ttu-id="a1424-105">ASP.Net のバージョンは、選択した .NET CLR バージョンに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1424-105">The ASP.Net versions are included with the .NET CLR version you choose.</span></span> 

<span data-ttu-id="a1424-106">このトピックでは、.NET CLR バージョンを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a1424-106">This topic shows you how to change the .NET CLR version.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a1424-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a1424-107">Prerequisites</span></span>

<span data-ttu-id="a1424-108">IIS に含まれて、 **Web サーバー (IIS)** オペレーティング システムの役割です。</span><span class="sxs-lookup"><span data-stu-id="a1424-108">IIS is included with the **Web Server (IIS)** role in the operating system.</span></span> <span data-ttu-id="a1424-109">この役割をインストールするときにも、ASP.NET の新しいバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1424-109">When you install this role, also select the newer version of ASP.NET.</span></span> 
  
## <a name="update-an-application-pool"></a><span data-ttu-id="a1424-110">アプリケーション プールを更新します。</span><span class="sxs-lookup"><span data-stu-id="a1424-110">Update an application pool</span></span>
  
1.  <span data-ttu-id="a1424-111">開いている**インターネット インフォメーション サービス (IIS) マネージャー**:</span><span class="sxs-lookup"><span data-stu-id="a1424-111">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="a1424-112">**サーバー マネージャー****ツール**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-112">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="a1424-113">選択**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-113">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="a1424-114">サーバー名を展開し、選択**アプリケーション プール**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-114">Expand the server name, and select **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="a1424-115">アプリケーション プールを選択し、開く、**基本設定**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-115">Select the app pool, and open the **Basic Settings**.</span></span>  
  
4. <span data-ttu-id="a1424-116">設定、 **.NET CLR バージョン**以降のバージョン、および選択を**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a1424-116">Set the **.NET CLR version** to the newer version, and select **OK** to save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="a1424-117">Web.config ファイルのバージョンを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1424-117">You can also change the version in the web.config file.</span></span>
 
## <a name="allow-the-aspnet-extension"></a><span data-ttu-id="a1424-118">ASP.Net の拡張子を許可します。</span><span class="sxs-lookup"><span data-stu-id="a1424-118">Allow the ASP.Net extension</span></span>
  
1.  <span data-ttu-id="a1424-119">開いている**インターネット インフォメーション サービス (IIS) マネージャー**:</span><span class="sxs-lookup"><span data-stu-id="a1424-119">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="a1424-120">**サーバー マネージャー****ツール**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-120">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="a1424-121">選択**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-121">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="a1424-122">サーバー名を選択し、ダブルクリック**ISAPI および CGI の制限**です。</span><span class="sxs-lookup"><span data-stu-id="a1424-122">Select the server name, and double-click **ISAPI and CGI Restrictions**.</span></span>  
  
3. <span data-ttu-id="a1424-123">ASP.NET は確認**許可**32 ビットおよび 64 ビット バージョン。</span><span class="sxs-lookup"><span data-stu-id="a1424-123">Confirm ASP.NET is **Allowed** for the 32-bit and 64-bit versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1424-124">参照</span><span class="sxs-lookup"><span data-stu-id="a1424-124">See Also</span></span>  
 [<span data-ttu-id="a1424-125">Web サービスを公開するための計画</span><span class="sxs-lookup"><span data-stu-id="a1424-125">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)