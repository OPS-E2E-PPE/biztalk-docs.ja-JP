---
title: "バージョン管理、サービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="versioning-the-service-oriented-solution"></a><span data-ttu-id="fee0d-102">バージョン管理、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="fee0d-102">Versioning the Service Oriented Solution</span></span>
<span data-ttu-id="fee0d-103">ソリューションのフロント エンドとして機能する 2 つのオーケストレーション**CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**、central、動作中のオーケストレーションを呼び出して**CustomerService**です。</span><span class="sxs-lookup"><span data-stu-id="fee0d-103">The two orchestrations that act as front ends to the solution, **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse**, call the central, working orchestration, **CustomerService**.</span></span> <span data-ttu-id="fee0d-104">オーケストレーションの呼び出しは、オーケストレーションを含むアセンブリのバージョン番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="fee0d-104">Orchestration calls depend on the version number of the assembly containing the orchestration.</span></span> <span data-ttu-id="fee0d-105">この 3 つのオーケストレーションはすべて同じアセンブリにあるので、バージョン管理の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="fee0d-105">Because all three orchestrations are in the same assembly, there are no versioning issues.</span></span>  
  
 <span data-ttu-id="fee0d-106">また、オーケストレーションによって実装されるビジネス プロセスは、すぐに終了する非常に期間が短い要求 - 応答プロセスです。</span><span class="sxs-lookup"><span data-stu-id="fee0d-106">In addition, the business process implemented by the orchestrations is a very short-lived request-response process that completes quickly.</span></span> <span data-ttu-id="fee0d-107">したがって、バージョン管理、ビジネス プロセスの質問がこのソリューションでは発生しません-別のアセンブリの異なるバージョンに異なるオーケストレーションはありません。</span><span class="sxs-lookup"><span data-stu-id="fee0d-107">Thus, the question of versioning the business process does not arise in this solution—there are no different orchestrations in different assemblies with different versions.</span></span>  
  
 <span data-ttu-id="fee0d-108">ただし、オーケストレーションは、スキーマ アセンブリのスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="fee0d-108">However, the orchestrations do use the schemas in the schema assembly.</span></span> <span data-ttu-id="fee0d-109">スキーマを変更して別のバージョンとしてコンパイルした場合、新しいバージョンのスキーマ アセンブリでオーケストレーションを再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee0d-109">If the schemas are revised and compiled into a different version, you must recompile the orchestrations with the newer version of the schema assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee0d-110">参照</span><span class="sxs-lookup"><span data-stu-id="fee0d-110">See Also</span></span>  
 [<span data-ttu-id="fee0d-111">指向ソリューションのサービスの開発</span><span class="sxs-lookup"><span data-stu-id="fee0d-111">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)