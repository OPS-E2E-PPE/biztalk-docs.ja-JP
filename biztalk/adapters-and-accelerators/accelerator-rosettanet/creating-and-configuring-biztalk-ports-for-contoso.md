---
title: 作成して、Contoso の BizTalk ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- private process tutorial, creating ports
- creating, ports
- configuring, ports
- private process tutorial, configuring ports
- ports, configuring
ms.assetid: 179af692-e14c-40da-9c43-1a7d0b6beb1f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e7453fb35758aaca4eea3d8b05be4a7a7584085
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996507"
---
# <a name="creating-and-configuring-biztalk-ports-for-contoso"></a><span data-ttu-id="d7dba-102">作成して、Contoso の BizTalk ポートの構成</span><span class="sxs-lookup"><span data-stu-id="d7dba-102">Creating and Configuring BizTalk Ports for Contoso</span></span>
<span data-ttu-id="d7dba-103">このセクションでは、Microsoft® BizTalk Server に現在のソリューションを統合します。</span><span class="sxs-lookup"><span data-stu-id="d7dba-103">In this section, you integrate your current solution into Microsoft® BizTalk Server.</span></span> <span data-ttu-id="d7dba-104">この統合を行う前に、グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストールし、構成データベースで構成します。</span><span class="sxs-lookup"><span data-stu-id="d7dba-104">Before you do this, you install your assembly in the Global Assembly Cache (GAC), and then configure it in the Configuration database.</span></span> <span data-ttu-id="d7dba-105">次に、SQL アダプターと HTTP アダプターを使用する送信ポートを作成および構成します。</span><span class="sxs-lookup"><span data-stu-id="d7dba-105">You then create and configure send ports using a SQL adapter and a HTTP adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7dba-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d7dba-106">In This Section</span></span>  
  
-   [<span data-ttu-id="d7dba-107">手順 1: Contoso アセンブリへの厳密な名前の割り当て</span><span class="sxs-lookup"><span data-stu-id="d7dba-107">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-assigning-a-strong-name-to-the-contoso-assembly.md)  
  
-   [<span data-ttu-id="d7dba-108">手順 2: Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成</span><span class="sxs-lookup"><span data-stu-id="d7dba-108">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)