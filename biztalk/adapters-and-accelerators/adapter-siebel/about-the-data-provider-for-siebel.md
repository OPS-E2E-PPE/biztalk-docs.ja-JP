---
title: Data Provider 用 Siebel に関する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217762"
---
# <a name="about-the-data-provider-for-siebel"></a><span data-ttu-id="73951-102">Data Provider 用 Siebel について</span><span class="sxs-lookup"><span data-stu-id="73951-102">About the Data Provider for Siebel</span></span>
## <a name="overview"></a><span data-ttu-id="73951-103">概要</span><span class="sxs-lookup"><span data-stu-id="73951-103">Overview</span></span>
<span data-ttu-id="73951-104">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]の上に構築された、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="73951-104">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is built on top of the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span> <span data-ttu-id="73951-105">使用することができます、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]に。</span><span class="sxs-lookup"><span data-stu-id="73951-105">You can use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] to:</span></span>  
  
-   <span data-ttu-id="73951-106">Siebel システムへの接続に、ADO.NET クライアントを記述します。</span><span class="sxs-lookup"><span data-stu-id="73951-106">Write an ADO.NET client to connect to the Siebel system.</span></span> <span data-ttu-id="73951-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]プロバイダーとのインターフェイスを有効にする特定のクラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="73951-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
-   <span data-ttu-id="73951-108">Siebel ビジネス コンポーネントで SELECT クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="73951-108">Run a SELECT query on a Siebel business component</span></span>
  
-   <span data-ttu-id="73951-109">Siebel ビジネス サービスで EXEC クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="73951-109">Run an EXEC query on a Siebel business service</span></span>
  
-   <span data-ttu-id="73951-110">使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="73951-110">Use the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Integration Services (SSIS)</span></span>
  
<span data-ttu-id="73951-111">[Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用して](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)が上の情報に役立つ優れたリソース。</span><span class="sxs-lookup"><span data-stu-id="73951-111">[Use  the .NET Framework Data Provider for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md) is a great resource for information on:</span></span>  
  
-   <span data-ttu-id="73951-112">ADO.NET インターフェイスを拡張して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73951-112">The ADO.NET interfaces extended by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]</span></span>  
  
-   <span data-ttu-id="73951-113">Siebel システムへの接続への接続文字列</span><span class="sxs-lookup"><span data-stu-id="73951-113">The connection string to connect to a Siebel system</span></span>  
  
-   <span data-ttu-id="73951-114">選択と EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="73951-114">Syntax for the SELECT and EXEC statements</span></span>  
  
-   <span data-ttu-id="73951-115">使用して、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]と SSIS</span><span class="sxs-lookup"><span data-stu-id="73951-115">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS</span></span>  
  
## <a name="limitations"></a><span data-ttu-id="73951-116">制限事項</span><span class="sxs-lookup"><span data-stu-id="73951-116">Limitations</span></span>
<span data-ttu-id="73951-117">次はの既知の制限、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="73951-117">The following are known limitations of the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:</span></span>  
  
-   <span data-ttu-id="73951-118">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしている別名テーブルでの名前、WHERE 句ではなく、SELECT 句でします。</span><span class="sxs-lookup"><span data-stu-id="73951-118">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports alias names for tables in the SELECT clause, but not in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="73951-119">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]特殊文字が含まれている列名を持つテーブルの作成に失敗"]"です。</span><span class="sxs-lookup"><span data-stu-id="73951-119">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to create a table with column names that have the special character, "]".</span></span> <span data-ttu-id="73951-120">特殊文字をエスケープするには、別の終わり角かっこを含むです。</span><span class="sxs-lookup"><span data-stu-id="73951-120">You can escape the special character by including another closing square bracket.</span></span> <span data-ttu-id="73951-121">そのため、含めるように"]"の代わりに"]"です。</span><span class="sxs-lookup"><span data-stu-id="73951-121">So, you should include"]]" instead of "]".</span></span>  
  
-   <span data-ttu-id="73951-122">基になる Siebel クライアント API によるタイムアウトの処理に関する問題のため、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73951-122">Due to issues with timeout handling by the underlying Siebel client API, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="73951-123">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]非同期コマンドの動作をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="73951-123">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
-   <span data-ttu-id="73951-124">SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 8000 以上の文字の値が含まれている列のデータの取得に失敗します。</span><span class="sxs-lookup"><span data-stu-id="73951-124">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="73951-125">これに基づいて、SSIS の制限のため次に示します。</span><span class="sxs-lookup"><span data-stu-id="73951-125">This is due to an SSIS restriction according to which:</span></span>  
  
    -   <span data-ttu-id="73951-126">SSIS 変数内の 4,000 文字より大きい値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="73951-126">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
    -   <span data-ttu-id="73951-127">4000 のワイド文字を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73951-127">Values greater than 4000 wide characters are not supported.</span></span>  
  
    -   <span data-ttu-id="73951-128">1 バイト文字で 8000 を超える値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73951-128">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
-   <span data-ttu-id="73951-129">EXEC 操作が使用中に機能しなくなります、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] SQL Server Integration Services (SSIS) にします。</span><span class="sxs-lookup"><span data-stu-id="73951-129">The EXEC operation will not be functional while using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] with SQL Server Integration Services (SSIS).</span></span> <span data-ttu-id="73951-130">そのため、たとえば、アダプター クライアントできなくで Siebel ビジネス サービスを実行する (を使用して[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) と SSIS のデータ プロバイダーを使用しているときにします。</span><span class="sxs-lookup"><span data-stu-id="73951-130">So, for example, adapter clients will not be able to execute a business service in Siebel (using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) while using the data providers with SSIS.</span></span> 

## <a name="see-also"></a><span data-ttu-id="73951-131">参照</span><span class="sxs-lookup"><span data-stu-id="73951-131">See also</span></span>
[<span data-ttu-id="73951-132">Siebel アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="73951-132">Limitations of the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[<span data-ttu-id="73951-133">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73951-133">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)