---
title: シナリオ:2 つのバージョンのアプリケーションの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, multiple assemblies
- assemblies, multiple assemblies
- receive locations, examples
- assemblies, deploying
- assemblies, examples
ms.assetid: 3e79a7df-bf77-4a0b-86ec-359fcf3489b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f41365ef18d1d2612236ac1b745008ad90a5c60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308198"
---
# <a name="scenario-deploying-two-versions-of-an-application"></a><span data-ttu-id="61e6a-102">シナリオ:2 つのバージョンのアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="61e6a-102">Scenario: Deploying Two Versions of an Application</span></span>
<span data-ttu-id="61e6a-103">ここでは、BizTalk グループ内にアプリケーションの 2 つのバージョンを展開して、両方のバージョンを同時に実行できるようにするためのシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="61e6a-103">This topic describes the scenario of deploying two versions of an application within a BizTalk group, so that they can both run simultaneously.</span></span> <span data-ttu-id="61e6a-104">このシナリオでは、アプリケーションの新しいメジャー バージョンを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61e6a-104">In this scenario, you need to deploy a major new version of the application.</span></span> <span data-ttu-id="61e6a-105">これには、スキーマまたはプロトコルの変更 (事実上、新しいアプリケーションへの変更) が生じるため、パートナーはシステムとの通信方法を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61e6a-105">It requires partners to change their interaction with the system due to either schema or protocol change - essentially a new application.</span></span> <span data-ttu-id="61e6a-106">このシステムの切り替えはテスト済みですが、完全な運用システム規模ではテストされていません。</span><span class="sxs-lookup"><span data-stu-id="61e6a-106">The changeover to this system has been tested but not under the scale of a full production system.</span></span> <span data-ttu-id="61e6a-107">パートナーの 20% で新しいシステムをテストし、すべてのパートナーがそのシステムを使用するようになるまでその比率を徐々に増やしていくことができます。</span><span class="sxs-lookup"><span data-stu-id="61e6a-107">You want to pilot the new system with 20 percent of the partners, and gradually increase that percentage until all the partners are using it.</span></span>  
  
 <span data-ttu-id="61e6a-108">2 つのアプリケーションは 2 つの異なる受信場所でメッセージを受信するため、アプリケーションの新しいバージョンを使用して新しい URL にメッセージを送信し、新しいバーションでメッセージを処理するように、パートナーに依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61e6a-108">Because the two applications receive messages on two different receive locations, you must ask those partners that should use the new version of the application to send messages to the new URL, so that they will be processed by the new version.</span></span>  
  
 <span data-ttu-id="61e6a-109">次の図は、標準のアプリケーション並列展開を示しています。</span><span class="sxs-lookup"><span data-stu-id="61e6a-109">The following diagram shows a typical side-by-side application deployment.</span></span>  
  
 <span data-ttu-id="61e6a-110">![2 つのアセンブリ バージョンを一緒にデプロイ](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span><span class="sxs-lookup"><span data-stu-id="61e6a-110">![Two Assembly Versions Deployed Together](../core/media/sidebysideassemblyversions.gif "SideBySideAssemblyVersions")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e6a-111">参照</span><span class="sxs-lookup"><span data-stu-id="61e6a-111">See Also</span></span>  
 [<span data-ttu-id="61e6a-112">アプリケーションの展開および管理のシナリオ</span><span class="sxs-lookup"><span data-stu-id="61e6a-112">Application Deployment and Management Scenarios</span></span>](../core/application-deployment-and-management-scenarios.md)