---
title: ビジネス プロセス管理ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9002d3fbd74ad6ceff649c59fa642447178d9b02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358115"
---
# <a name="business-process-management-solution"></a><span data-ttu-id="4247a-102">ビジネス プロセス管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="4247a-102">Business Process Management Solution</span></span>
<span data-ttu-id="4247a-103">ビジネス プロセス管理ソリューションでは、サービスの注文処理などのビジネス プロセスを管理する BizTalk アプリケーションを設計する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4247a-103">The Business Process Management solution shows how to design a BizTalk application to manage a business process such as service order processing.</span></span> <span data-ttu-id="4247a-104">ソリューションでは、プロセス マネージャを構築する方法について説明し、プロセスを段階に分ける方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4247a-104">The solution demonstrates how to construct a process manager and provides guidance about dividing a process into distinct stages.</span></span> <span data-ttu-id="4247a-105">ソリューションには、広範な高度な例外処理と同様に割り込み可能なオーケストレーションを構築する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="4247a-105">The solution also describes how to construct interruptible orchestrations as well as extensive, sophisticated exception handling.</span></span>  
  
 <span data-ttu-id="4247a-106">パターンとデザインの選択肢、構築、およびソリューションの実行に関する情報の詳細な説明については、ソリューションの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="4247a-106">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4247a-107">パターンとこれらのセクションに記載されているガイダンスは、そのビジネス ソリューションの特定の種類の方法を説明するために、します。</span><span class="sxs-lookup"><span data-stu-id="4247a-107">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="4247a-108">パターンは、単純なメカニズムでは、特定の問題に適用するためのものし、は通常、その他のパターンと組み合わせてです。</span><span class="sxs-lookup"><span data-stu-id="4247a-108">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="4247a-109">アプリケーションに接続するのにはないです。</span><span class="sxs-lookup"><span data-stu-id="4247a-109">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="4247a-110">「現状有姿のコード例が提供されると、実稼働環境用のものではありません。</span><span class="sxs-lookup"><span data-stu-id="4247a-110">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="4247a-111">パターンの説明だけを目的とし、そのため、例外処理、ログ記録、セキュリティ、および検証などの余分なコードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="4247a-111">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="4247a-112">Microsoft では、「現状有姿コード例を運用環境にデプロイすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4247a-112">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4247a-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4247a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="4247a-114">ビジネス プロセス管理ソリューションを理解します。</span><span class="sxs-lookup"><span data-stu-id="4247a-114">Understanding the Business Process Management Solution</span></span>](../core/understanding-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="4247a-115">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="4247a-115">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
-   [<span data-ttu-id="4247a-116">ビジネス プロセス管理ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="4247a-116">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)