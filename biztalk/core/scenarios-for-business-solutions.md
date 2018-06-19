---
title: ビジネス ソリューションのシナリオ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business solutions, tutorials
- tutorials, applications
- applications, tutorials
- applications, business solutions
- tutorials, business solutions
- solutions, tutorials
ms.assetid: f6239905-a1bf-4223-bdca-6677f2d6049b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 024f3a1f0422b6e7adf338610e1bbdb1fdc9857a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269122"
---
# <a name="scenarios-for-business-solutions"></a><span data-ttu-id="62f9a-102">ビジネス ソリューションのシナリオ</span><span class="sxs-lookup"><span data-stu-id="62f9a-102">Scenarios for Business Solutions</span></span>
<span data-ttu-id="62f9a-103">このセクションでは、2 つの完全なモデル BizTalk アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62f9a-103">This section describes two complete, model BizTalk applications.</span></span> <span data-ttu-id="62f9a-104">各アプリケーションは、特定のビジネス パターンを表し、その他の構成要素である統合パターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="62f9a-104">Each application represents a particular business pattern and demonstrates other constituent integration patterns.</span></span>  
  
 <span data-ttu-id="62f9a-105">各セクションでは、アプリケーションの概要、アプリケーションの開発過程におけるパターンやデザインに関する意思決定について説明する開発者向けガイド、およびアプリケーションを構築して実行するための展開情報を示します。</span><span class="sxs-lookup"><span data-stu-id="62f9a-105">Each section presents an overview of the application, a developer's guide that describes the patterns and design decisions reached in the course of developing the application, and deployment information for building and running the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62f9a-106">以下のセクションで示すパターンやガイダンスは、特定の種類のビジネス ソリューションに対するアプローチを示すためのものです。</span><span class="sxs-lookup"><span data-stu-id="62f9a-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="62f9a-107">パターンは、特定の問題に適用することを目的とした単純なメカニズムで、通常は他のパターンと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="62f9a-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="62f9a-108">これらのパターンは、アプリケーションに組み込んで使用することを意図したものではありません。</span><span class="sxs-lookup"><span data-stu-id="62f9a-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="62f9a-109">コード例は、無保証で提供されており、実稼動環境で使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="62f9a-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="62f9a-110">これはパターンを示すことだけを目的としているため、例外処理、ログ、セキュリティ、検証などのためのコードは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="62f9a-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="62f9a-111">マイクロソフトは、無保証のコード例を実稼動環境に展開した場合の動作を保証しません。</span><span class="sxs-lookup"><span data-stu-id="62f9a-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62f9a-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62f9a-112">In This Section</span></span>  
  
-   [<span data-ttu-id="62f9a-113">サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="62f9a-113">Service Oriented Solution</span></span>](../core/service-oriented-solution.md)  
  
-   [<span data-ttu-id="62f9a-114">ビジネス プロセス管理ソリューション</span><span class="sxs-lookup"><span data-stu-id="62f9a-114">Business Process Management Solution</span></span>](../core/business-process-management-solution.md)