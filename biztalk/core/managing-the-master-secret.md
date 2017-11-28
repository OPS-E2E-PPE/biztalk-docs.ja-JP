---
title: "マスタ シークレットの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2505fa6f5ec1abc04ded45e7701fd4e5212f889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-master-secret"></a><span data-ttu-id="daa64-102">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="daa64-102">Managing the Master Secret</span></span>
<span data-ttu-id="daa64-103">マスタ シークレットは、SSO データベースに格納されているすべての情報を暗号化するために使用されるキーです。</span><span class="sxs-lookup"><span data-stu-id="daa64-103">The master secret is the key used to encrypt all the information stored in the SSO database.</span></span> <span data-ttu-id="daa64-104">マスタ シークレット サーバーに障害が発生してマスタ シークレットが失われると、SSO データベースに格納されている情報を取得できなくなります。</span><span class="sxs-lookup"><span data-stu-id="daa64-104">If the master secret server fails and you lose the secret, you will not be able to retrieve the information stored in the SSO database.</span></span> <span data-ttu-id="daa64-105">そのため、マスタ シークレットは作成したらすぐにバックアップすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="daa64-105">Therefore, it is very important to back up the master secret as soon as you generate it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="daa64-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="daa64-106">In This Section</span></span>  
  
-   [<span data-ttu-id="daa64-107">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="daa64-107">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="daa64-108">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="daa64-108">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="daa64-109">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="daa64-109">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="daa64-110">マスター シークレット サーバーを移動する方法</span><span class="sxs-lookup"><span data-stu-id="daa64-110">How to Move the Master Secret Server</span></span>](../core/how-to-move-the-master-secret-server.md)