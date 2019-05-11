---
title: インターセプタの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37d00104-daf6-42b0-a022-25d572170fe6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e976157821cf5047dc6353d0afb5a6eba0429bad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331741"
---
# <a name="interceptor-operations"></a><span data-ttu-id="62b8c-102">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="62b8c-102">Interceptor Operations</span></span>
<span data-ttu-id="62b8c-103">このセクションには、共通のインターセプター構成ファイルの操作に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="62b8c-103">This section contains information about common interceptor configuration file operations.</span></span> <span data-ttu-id="62b8c-104">これらの操作は、Windows Workflow Foundation (WF) および Windows Communication Framework (WCF) インターセプタおよび Common Interceptor Framework 上に構築されたその他のすべてのインターセプターを利用できます。</span><span class="sxs-lookup"><span data-stu-id="62b8c-104">These operations are available to Windows Workflow Foundation (WF) and Windows Communication Framework (WCF) interceptors and to any other interceptors built on top of the Common Interceptor Framework.</span></span> <span data-ttu-id="62b8c-105">WCF と WF インターセプターは、取得し、インターセプターのデータを操作するため、追加のドメイン固有の操作を定義することで、これらの演算子によって提供される一般的な機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="62b8c-105">Both the WF and WCF interceptors extend the common functionality provided by these operators by defining additional, domain-specific operations for retrieving and manipulating interceptor data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62b8c-106">操作名は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="62b8c-106">Operation names are case sensitive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62b8c-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62b8c-107">In This Section</span></span>  
  
-   [<span data-ttu-id="62b8c-108">And</span><span class="sxs-lookup"><span data-stu-id="62b8c-108">And</span></span>](../core/and.md)  
  
-   [<span data-ttu-id="62b8c-109">Concatenate</span><span class="sxs-lookup"><span data-stu-id="62b8c-109">Concatenate</span></span>](../core/concatenate.md)  
  
-   [<span data-ttu-id="62b8c-110">定数</span><span class="sxs-lookup"><span data-stu-id="62b8c-110">Constant</span></span>](../core/constant.md)  
  
-   <span data-ttu-id="62b8c-111">[[等しい]](../core/equals.md)</span><span class="sxs-lookup"><span data-stu-id="62b8c-111">[Equals](../core/equals.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b8c-112">参照</span><span class="sxs-lookup"><span data-stu-id="62b8c-112">See Also</span></span>  
 <span data-ttu-id="62b8c-113">[操作](../core/interceptor-operations.md) </span><span class="sxs-lookup"><span data-stu-id="62b8c-113">[Operations](../core/interceptor-operations.md) </span></span>  
 <span data-ttu-id="62b8c-114">[Windows Workflow Foundation での操作](../core/operations-in-windows-workflow-foundation.md) </span><span class="sxs-lookup"><span data-stu-id="62b8c-114">[Operations in Windows Workflow Foundation](../core/operations-in-windows-workflow-foundation.md) </span></span>  
 [<span data-ttu-id="62b8c-115">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="62b8c-115">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)