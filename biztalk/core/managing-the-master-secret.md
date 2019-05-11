---
title: マスター シークレットの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc7c0222a635b3b698adf899f98a8ff96e08de
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531135"
---
# <a name="managing-the-master-secret"></a><span data-ttu-id="91040-102">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="91040-102">Managing the Master Secret</span></span>
<span data-ttu-id="91040-103">マスター シークレットは、SSO データベースに格納されているすべての情報の暗号化に使用されるキーです。</span><span class="sxs-lookup"><span data-stu-id="91040-103">The master secret is the key used to encrypt all the information stored in the SSO database.</span></span> <span data-ttu-id="91040-104">マスター シークレット サーバーが失敗して、シークレットを紛失した、SSO データベースに格納されている情報を取得することができなきます。</span><span class="sxs-lookup"><span data-stu-id="91040-104">If the master secret server fails and you lose the secret, you will not be able to retrieve the information stored in the SSO database.</span></span> <span data-ttu-id="91040-105">そのため、生成するとすぐにマスター シークレットをバックアップする非常に重要ですが。</span><span class="sxs-lookup"><span data-stu-id="91040-105">Therefore, it is very important to back up the master secret as soon as you generate it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91040-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="91040-106">In This Section</span></span>  
  
-   [<span data-ttu-id="91040-107">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="91040-107">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="91040-108">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="91040-108">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="91040-109">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="91040-109">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="91040-110">マスター シークレット サーバーを移動する方法</span><span class="sxs-lookup"><span data-stu-id="91040-110">How to Move the Master Secret Server</span></span>](../core/how-to-move-the-master-secret-server.md)