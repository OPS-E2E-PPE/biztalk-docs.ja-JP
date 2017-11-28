---
title: "ビジネス プロセス管理ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business solutions, tutorials
- tutorials, orchestrations
- errors, tutorials
- business solutions, process management solutions
- process management solutions
- process management solutions, applications
- process management solutions, business solutions
- tutorials, applications
- tutorials, errors
- tutorials, process management solutions
- applications, tutorials
- tutorials, business solutions
- process management solutions, tutorials
- orchestrations, interrupting
- orchestrations, tutorials
- applications, process management solutions
ms.assetid: 30ebd248-7e31-4608-ae50-4fc6703ae613
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f37fa7691a3e780c0f972e1070a8bf639c4addcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="business-process-management-solution"></a><span data-ttu-id="eb7c7-102">ビジネス プロセス管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="eb7c7-102">Business Process Management Solution</span></span>
<span data-ttu-id="eb7c7-103">ビジネス プロセス管理ソリューションは、サービス注文処理のようなビジネス プロセスを管理する BizTalk アプリケーションを設計する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-103">The Business Process Management solution shows how to design a BizTalk application to manage a business process such as service order processing.</span></span> <span data-ttu-id="eb7c7-104">プロセス マネージャを構築する方法を示し、プロセスを独立した段階に分ける方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-104">The solution demonstrates how to construct a process manager and provides guidance about dividing a process into distinct stages.</span></span> <span data-ttu-id="eb7c7-105">また、割り込み可能なオーケストレーションを構築する方法、および拡張的で洗練された例外処理についても説明します。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-105">The solution also describes how to construct interruptible orchestrations as well as extensive, sophisticated exception handling.</span></span>  
  
 <span data-ttu-id="eb7c7-106">次のセクションには、このソリューションの概要、パターンおよびデザインの選択肢の詳細な説明、ソリューションの構築および実行に関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-106">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb7c7-107">以下のセクションで示すパターンやガイダンスは、特定の種類のビジネス ソリューションに対するアプローチを示すためのものです。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-107">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="eb7c7-108">パターンは、特定の問題に適用することを目的とした単純なメカニズムで、通常は他のパターンと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-108">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="eb7c7-109">これらのパターンは、アプリケーションに組み込んで使用することを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-109">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="eb7c7-110">コード例は、無保証で提供されており、実稼動環境で使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-110">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="eb7c7-111">これはパターンを示すことだけを目的としているため、例外処理、ログ、セキュリティ、検証などのためのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-111">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="eb7c7-112">マイクロソフトは、無保証のコード例を実稼動環境に展開した場合の動作を保証しません。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-112">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb7c7-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eb7c7-113">In This Section</span></span>  
  
-   [<span data-ttu-id="eb7c7-114">ビジネス プロセス管理ソリューションを理解します。</span><span class="sxs-lookup"><span data-stu-id="eb7c7-114">Understanding the Business Process Management Solution</span></span>](../core/understanding-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="eb7c7-115">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="eb7c7-115">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
-   [<span data-ttu-id="eb7c7-116">ビジネス プロセス管理ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="eb7c7-116">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)