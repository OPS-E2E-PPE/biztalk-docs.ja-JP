---
title: サービス指向ソリューション |Microsoft ドキュメント
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
ms.openlocfilehash: 5a1c69d537469cc1c2a4d9d93cde37014b31daa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271370"
---
# <a name="service-oriented-solution"></a><span data-ttu-id="0a726-102">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="0a726-102">Service Oriented Solution</span></span>
<span data-ttu-id="0a726-103">サービス指向ソリューションでは、Web サービスとして利用可能なサービスとして、レガシ アプリケーションにアクセスできる形式で、BizTalk アプリケーションを提供する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0a726-103">The service oriented solution shows how to present a BizTalk application as a service that is available as a Web service and in forms accessible to legacy applications.</span></span> <span data-ttu-id="0a726-104">このソリューションは、Web サービスとしてバックエンド プロセスと通信する方法だけでなく、複数のバックエンド システムからの応答を集計する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="0a726-104">The solution also shows how to communicate with back-end processes as Web services, as well as how to aggregate responses from multiple back-end systems.</span></span>  
  
 <span data-ttu-id="0a726-105">次のセクションには、このソリューションの概要、パターンおよびデザインの選択肢の詳細な説明、ソリューションの構築および実行に関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0a726-105">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a726-106">以下のセクションで示すパターンやガイダンスは、特定の種類のビジネス ソリューションに対するアプローチを示すためのものです。</span><span class="sxs-lookup"><span data-stu-id="0a726-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="0a726-107">パターンは、特定の問題に適用することを目的とした単純なメカニズムで、通常は他のパターンと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="0a726-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="0a726-108">これらのパターンは、アプリケーションに組み込んで使用することを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="0a726-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="0a726-109">コード例は、無保証で提供されており、実稼動環境で使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="0a726-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="0a726-110">これはパターンを示すことだけを目的としているため、例外処理、ログ、セキュリティ、検証などのためのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0a726-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="0a726-111">マイクロソフトは、無保証のコード例を実稼動環境に展開した場合の動作を保証しません。</span><span class="sxs-lookup"><span data-stu-id="0a726-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a726-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0a726-112">In This Section</span></span>  
  
-   [<span data-ttu-id="0a726-113">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="0a726-113">Understanding the Service Oriented Solution</span></span>](../core/understanding-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0a726-114">指向ソリューションのサービスの開発</span><span class="sxs-lookup"><span data-stu-id="0a726-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0a726-115">指向ソリューションのサービスの展開</span><span class="sxs-lookup"><span data-stu-id="0a726-115">Deploying the Service Oriented Solution</span></span>](../core/deploying-the-service-oriented-solution.md)