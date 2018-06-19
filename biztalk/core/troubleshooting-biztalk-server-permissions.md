---
title: BizTalk Server のアクセス許可のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e47bd1fc-2edf-4525-97dd-4bd9d3e2d6ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb280141b6817a622c84c16a3b66df289472cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280082"
---
# <a name="troubleshooting-biztalk-server-permissions"></a><span data-ttu-id="03903-102">BizTalk Server のアクセス許可に関するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="03903-102">Troubleshooting BizTalk Server Permissions</span></span>
<span data-ttu-id="03903-103">通常、BizTalk Server のアクセス許可に関する問題は、次のカテゴリのいずれかに分類されます。</span><span class="sxs-lookup"><span data-stu-id="03903-103">Permissions problems in BizTalk Server typically fall into one of the following categories:</span></span>  
  
-   <span data-ttu-id="03903-104">SQL Server 権限</span><span class="sxs-lookup"><span data-stu-id="03903-104">SQL Server permissions</span></span>  
  
-   <span data-ttu-id="03903-105">BizTalk Server の複数サーバー環境での Active Directory アクセス許可</span><span class="sxs-lookup"><span data-stu-id="03903-105">Active Directory permissions on multiserver installations of BizTalk Server</span></span>  
  
-   <span data-ttu-id="03903-106">Web サービスのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="03903-106">Web services permissions</span></span>  
  
-   <span data-ttu-id="03903-107">IIS のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="03903-107">IIS permissions</span></span>  
  
 <span data-ttu-id="03903-108">このトピックでは、権限の問題を最小限に抑えるための一般的なガイドラインを提供し、特定のシナリオをトラブルシューティングするための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="03903-108">This topic provides some general guidelines for avoiding permissions problems and troubleshooting steps for specific scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03903-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="03903-109">In This Section</span></span>  
  
-   [<span data-ttu-id="03903-110">SQL Server のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="03903-110">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)  
  
-   [<span data-ttu-id="03903-111">マルチ サーバーの BizTalk 環境に Active Directory アクセス許可を実装するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="03903-111">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>](../core/implement-active-directory-permissions-on-multi-server-biztalk-installations.md)  
  
-   [<span data-ttu-id="03903-112">Web サービスのアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="03903-112">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)  
  
-   [<span data-ttu-id="03903-113">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="03903-113">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)