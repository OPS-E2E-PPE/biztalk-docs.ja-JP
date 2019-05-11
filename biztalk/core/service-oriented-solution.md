---
title: サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solutions
- tutorials, legacy applications
- business solutions, back-end systems
- service solution tutorial
- tutorials, services
- Web services, tutorials
- Web services, business solutions
- tutorials, applications
- applications, tutorials
- applications, services
- legacy applications, tutorials
- service solutions, business solutions
- tutorials, Web services
- tutorials, service solutions
- business solutions, totorials
- business solutions, legacy applications
- back-end systems
- tutorials, business solutions
- legacy applications, business solutions
- business solutions, Web services
- business solutions, service solutions
ms.assetid: ce7cdf8d-ecaf-4a6a-9536-a9cf5d7f874f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53712039f5aa64f85fddd1d18af121abb3bb2dbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393279"
---
# <a name="service-oriented-solution"></a><span data-ttu-id="e76e8-102">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e76e8-102">Service Oriented Solution</span></span>
<span data-ttu-id="e76e8-103">サービス指向ソリューションでは、Web サービスとして、従来のアプリケーションにアクセスできる形式で提供されるサービスとしての BizTalk アプリケーションを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e76e8-103">The service oriented solution shows how to present a BizTalk application as a service that is available as a Web service and in forms accessible to legacy applications.</span></span> <span data-ttu-id="e76e8-104">ソリューションは、Web サービスとしてバックエンド プロセスと通信する方法と、複数のバックエンド システムからの応答を集計する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="e76e8-104">The solution also shows how to communicate with back-end processes as Web services, as well as how to aggregate responses from multiple back-end systems.</span></span>  
  
 <span data-ttu-id="e76e8-105">パターンとデザインの選択肢、構築、およびソリューションの実行に関する情報の詳細な説明については、ソリューションの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e76e8-105">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e76e8-106">パターンとこれらのセクションに記載されているガイダンスは、そのビジネス ソリューションの特定の種類の方法を説明するために、します。</span><span class="sxs-lookup"><span data-stu-id="e76e8-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="e76e8-107">パターンは、単純なメカニズムでは、特定の問題に適用するためのものし、は通常、その他のパターンと組み合わせてです。</span><span class="sxs-lookup"><span data-stu-id="e76e8-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="e76e8-108">アプリケーションに接続するのにはないです。</span><span class="sxs-lookup"><span data-stu-id="e76e8-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="e76e8-109">「現状有姿のコード例が提供されると、実稼働環境用のものではありません。</span><span class="sxs-lookup"><span data-stu-id="e76e8-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="e76e8-110">パターンの説明だけを目的とし、そのため、例外処理、ログ記録、セキュリティ、および検証などの余分なコードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="e76e8-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="e76e8-111">Microsoft では、「現状有姿コード例を運用環境にデプロイすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e76e8-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e76e8-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e76e8-112">In This Section</span></span>  
  
-   [<span data-ttu-id="e76e8-113">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e76e8-113">Understanding the Service Oriented Solution</span></span>](../core/understanding-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e76e8-114">開発、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="e76e8-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)  
  
-   [<span data-ttu-id="e76e8-115">指向ソリューションのサービスのデプロイ</span><span class="sxs-lookup"><span data-stu-id="e76e8-115">Deploying the Service Oriented Solution</span></span>](../core/deploying-the-service-oriented-solution.md)