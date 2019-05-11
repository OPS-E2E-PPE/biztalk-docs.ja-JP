---
title: バージョン管理、サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34896f02ac6335c8f5041ca959b25fe9ab2716c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393733"
---
# <a name="versioning-the-service-oriented-solution"></a><span data-ttu-id="dcde6-102">バージョン管理、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="dcde6-102">Versioning the Service Oriented Solution</span></span>
<span data-ttu-id="dcde6-103">ソリューションのフロント エンドとして機能する 2 つのオーケストレーション**CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**、中央の動作中のオーケストレーションを呼び出す**CustomerService**します。</span><span class="sxs-lookup"><span data-stu-id="dcde6-103">The two orchestrations that act as front ends to the solution, **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse**, call the central, working orchestration, **CustomerService**.</span></span> <span data-ttu-id="dcde6-104">オーケストレーションの呼び出しは、オーケストレーションを含むアセンブリのバージョン番号に依存します。</span><span class="sxs-lookup"><span data-stu-id="dcde6-104">Orchestration calls depend on the version number of the assembly containing the orchestration.</span></span> <span data-ttu-id="dcde6-105">すべての 3 つのオーケストレーションは、同じアセンブリにあるために、バージョン管理の問題はありません。</span><span class="sxs-lookup"><span data-stu-id="dcde6-105">Because all three orchestrations are in the same assembly, there are no versioning issues.</span></span>  
  
 <span data-ttu-id="dcde6-106">さらに、オーケストレーションによって実装されるビジネス プロセスは、すぐに終了する非常に短時間の要求-応答プロセスです。</span><span class="sxs-lookup"><span data-stu-id="dcde6-106">In addition, the business process implemented by the orchestrations is a very short-lived request-response process that completes quickly.</span></span> <span data-ttu-id="dcde6-107">したがって、バージョン管理、ビジネス プロセスの質問がこのソリューションでは発生しません-さまざまなバージョンでさまざまなアセンブリ内の別のオーケストレーションがありません。</span><span class="sxs-lookup"><span data-stu-id="dcde6-107">Thus, the question of versioning the business process does not arise in this solution—there are no different orchestrations in different assemblies with different versions.</span></span>  
  
 <span data-ttu-id="dcde6-108">ただし、オーケストレーションでは、スキーマ アセンブリでスキーマを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="dcde6-108">However, the orchestrations do use the schemas in the schema assembly.</span></span> <span data-ttu-id="dcde6-109">場合は、スキーマが変更され、別のバージョンにコンパイル、スキーマ アセンブリの新しいバージョンでオーケストレーションを再コンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcde6-109">If the schemas are revised and compiled into a different version, you must recompile the orchestrations with the newer version of the schema assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcde6-110">参照</span><span class="sxs-lookup"><span data-stu-id="dcde6-110">See Also</span></span>  
 [<span data-ttu-id="dcde6-111">開発、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="dcde6-111">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)