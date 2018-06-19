---
title: インターセプタの操作 |Microsoft ドキュメント
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
ms.openlocfilehash: dd67f5e6245d4b16c83e030b3c9149c77b791153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257154"
---
# <a name="interceptor-operations"></a><span data-ttu-id="43989-102">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="43989-102">Interceptor Operations</span></span>
<span data-ttu-id="43989-103">このセクションでは、インターセプタ構成ファイルの一般的な操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="43989-103">This section contains information about common interceptor configuration file operations.</span></span> <span data-ttu-id="43989-104">これらの操作は、Windows Workflow Foundation (WF) および Windows Communication Foundation (WCF) のインターセプタと、Common Interceptor Framework を基に構築されたその他のすべてのインターセプタで使用できます。</span><span class="sxs-lookup"><span data-stu-id="43989-104">These operations are available to Windows Workflow Foundation (WF) and Windows Communication Framework (WCF) interceptors and to any other interceptors built on top of the Common Interceptor Framework.</span></span> <span data-ttu-id="43989-105">WF インターセプタおよび WCF インターセプタでは、インターセプタ データを取得して操作するための追加のドメイン固有の操作を定義することにより、これらの操作によって提供される共通の機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="43989-105">Both the WF and WCF interceptors extend the common functionality provided by these operators by defining additional, domain-specific operations for retrieving and manipulating interceptor data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43989-106">操作名の大文字と小文字は区別されます。</span><span class="sxs-lookup"><span data-stu-id="43989-106">Operation names are case sensitive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43989-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43989-107">In This Section</span></span>  
  
-   [<span data-ttu-id="43989-108">そして</span><span class="sxs-lookup"><span data-stu-id="43989-108">And</span></span>](../core/and.md)  
  
-   [<span data-ttu-id="43989-109">連結</span><span class="sxs-lookup"><span data-stu-id="43989-109">Concatenate</span></span>](../core/concatenate.md)  
  
-   [<span data-ttu-id="43989-110">定数</span><span class="sxs-lookup"><span data-stu-id="43989-110">Constant</span></span>](../core/constant.md)  
  
-   <span data-ttu-id="43989-111">[[等しい]](../core/equals.md)</span><span class="sxs-lookup"><span data-stu-id="43989-111">[Equals](../core/equals.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43989-112">参照</span><span class="sxs-lookup"><span data-stu-id="43989-112">See Also</span></span>  
 <span data-ttu-id="43989-113">[操作](../core/interceptor-operations.md) </span><span class="sxs-lookup"><span data-stu-id="43989-113">[Operations](../core/interceptor-operations.md) </span></span>  
 <span data-ttu-id="43989-114">[Windows Workflow Foundation での操作](../core/operations-in-windows-workflow-foundation.md) </span><span class="sxs-lookup"><span data-stu-id="43989-114">[Operations in Windows Workflow Foundation](../core/operations-in-windows-workflow-foundation.md) </span></span>  
 [<span data-ttu-id="43989-115">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="43989-115">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)