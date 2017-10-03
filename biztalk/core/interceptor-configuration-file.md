---
title: "インターセプター構成ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490f5607-e7f6-4f7f-9121-1070db32a7cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb4a57272ebae5b831552d9446dbdbc937dca1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-configuration-file"></a><span data-ttu-id="548ee-102">インターセプタ構成ファイル</span><span class="sxs-lookup"><span data-stu-id="548ee-102">Interceptor Configuration File</span></span>
<span data-ttu-id="548ee-103">Windows Workflow Foundation 用の BAM インターセプタと Windows Communication Foundation 用の BAM インターセプタは、インターセプタ構成ファイルに基づいて、受信するイベントとデータ要素を決定します。</span><span class="sxs-lookup"><span data-stu-id="548ee-103">The BAM interceptors for Windows Workflow Foundation and Windows Communication Foundation rely on an interceptor configuration file to determine what events and date elements to intercept.</span></span> <span data-ttu-id="548ee-104">構成ファイルは、XML 形式であり、インターセプタ構成スキーマおよび Windows Workflow Foundation スキーマと Windows Communication Framework スキーマのどちらか一方 (ターゲットにするテクノロジに応じて) により定義されます。</span><span class="sxs-lookup"><span data-stu-id="548ee-104">The configuration file is XML and is defined by the interceptor configuration schema and either the Windows Workflow Foundation schema or the Windows Communication Framework schema depending upon which technology you are targeting.</span></span>  
  
 <span data-ttu-id="548ee-105">このセクションでは、インターセプタの要素や属性などの基本構成を中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="548ee-105">This section focuses on the base interceptor configuration including elements and attributes.</span></span> <span data-ttu-id="548ee-106">テクノロジ固有のインターセプタは他の機能も提供しますが、それらの機能については別のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="548ee-106">Additional functionality is provided by the technology-specific interceptors and are explained in separate sections.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="548ee-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="548ee-107">In This Section</span></span>  
  
-   [<span data-ttu-id="548ee-108">IntelliSense を使用して、インターセプター構成ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="548ee-108">Using IntelliSense to Create an Interceptor Configuration File</span></span>](../core/using-intellisense-to-create-an-interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="548ee-109">インターセプタ構成スキーマ</span><span class="sxs-lookup"><span data-stu-id="548ee-109">Interceptor Configuration Schema</span></span>](../core/interceptor-configuration-schema.md)  
  
-   [<span data-ttu-id="548ee-110">インターセプタ構成ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="548ee-110">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="548ee-111">参照</span><span class="sxs-lookup"><span data-stu-id="548ee-111">See Also</span></span>  
 <span data-ttu-id="548ee-112">[BAM WF インターセプタ](../core/bam-wf-interceptor.md) </span><span class="sxs-lookup"><span data-stu-id="548ee-112">[BAM WF Interceptor](../core/bam-wf-interceptor.md) </span></span>  
 [<span data-ttu-id="548ee-113">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="548ee-113">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)