---
title: リソースの管理 |Microsoft Docs
description: Btstask または BizTalk 管理コンソールを使用して、アセンブリ、スクリプト、証明書、バインド ファイル、および BizTalk Server で複数の操作
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9aad282dfb444c2947afca3cefc0a96cd806826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015115"
---
# <a name="manage-resources"></a><span data-ttu-id="f3f40-103">リソースを管理します。</span><span class="sxs-lookup"><span data-stu-id="f3f40-103">Manage Resources</span></span>

## <a name="overview"></a><span data-ttu-id="f3f40-104">概要</span><span class="sxs-lookup"><span data-stu-id="f3f40-104">Overview</span></span>
<span data-ttu-id="f3f40-105">ここでは、BizTalk グループに BizTalk Server リソースを展開した後、BizTalk Server 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk Server リソースを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3f40-105">The topics in this section provide instructions on how to use the BizTalk Server Administration console or the BTSTask command-line tool to manage BizTalk Server resources after they have been deployed into a BizTalk group.</span></span> <span data-ttu-id="f3f40-106">リソースには、次の種類のアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3f40-106">Resources include the following types of artifacts:</span></span>  
  
-   <span data-ttu-id="f3f40-107">BizTalk アセンブリ</span><span class="sxs-lookup"><span data-stu-id="f3f40-107">BizTalk Assemblies</span></span>  
  
-   <span data-ttu-id="f3f40-108">処理前および処理後のスクリプト</span><span class="sxs-lookup"><span data-stu-id="f3f40-108">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="f3f40-109">.NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="f3f40-109">.NET assemblies</span></span>  
  
-   <span data-ttu-id="f3f40-110">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f3f40-110">COM components</span></span>  
  
-   <span data-ttu-id="f3f40-111">証明書</span><span class="sxs-lookup"><span data-stu-id="f3f40-111">Certificates</span></span>  
  
-   <span data-ttu-id="f3f40-112">アドホック ファイル</span><span class="sxs-lookup"><span data-stu-id="f3f40-112">Ad hoc files</span></span>  
  
-   <span data-ttu-id="f3f40-113">BAM 定義</span><span class="sxs-lookup"><span data-stu-id="f3f40-113">BAM definitions</span></span>  
  
-   <span data-ttu-id="f3f40-114">バインド ファイル</span><span class="sxs-lookup"><span data-stu-id="f3f40-114">Binding files</span></span>  
  
-   <span data-ttu-id="f3f40-115">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="f3f40-115">Virtual directories</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3f40-116">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3f40-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="f3f40-117">WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f40-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="f3f40-118">どのような場合においても、同じ名前の複数のリソースを BizTalk Server グループに追加しないでください。</span><span class="sxs-lookup"><span data-stu-id="f3f40-118">Do not add multiple resources with the same name, regardless of case, to a BizTalk Server group.</span></span> <span data-ttu-id="f3f40-119">BizTalk Server 管理データベースの格納先 SQL Server の構成で、バイナリ照合順序が使用され、大文字と小文字の区別がサポートされている場合でも、同じ名前の複数のリソースを BizTalk Server グループに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3f40-119">Adding multiple resources with the same name to a BizTalk Server group is not supported, even when the BizTalk Server management database is housed on a SQL Server that is configured to use binary collation and supports case sensitivity.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f3f40-120">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f3f40-120">Next steps</span></span>
  
-   [<span data-ttu-id="f3f40-121">BizTalk アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="f3f40-121">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)  
  
-   [<span data-ttu-id="f3f40-122">処理前および処理後のスクリプトの管理</span><span class="sxs-lookup"><span data-stu-id="f3f40-122">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [<span data-ttu-id="f3f40-123">.NET アセンブリ、証明書、およびその他のリソースの管理</span><span class="sxs-lookup"><span data-stu-id="f3f40-123">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [<span data-ttu-id="f3f40-124">リソースの更新</span><span class="sxs-lookup"><span data-stu-id="f3f40-124">Refresh a Resource</span></span>](../core/how-to-refresh-a-resource.md)