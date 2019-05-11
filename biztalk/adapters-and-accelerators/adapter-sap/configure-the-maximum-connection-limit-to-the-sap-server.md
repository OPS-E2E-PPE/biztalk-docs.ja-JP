---
title: SAP サーバーに最大接続数制限の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 858ed90e-b219-43cc-ad63-ae8e1eb2159a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4286fbbaeaca1aefaf6a7ea995a068eba25c0690
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373767"
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a><span data-ttu-id="5a7e3-102">SAP サーバーに最大接続数制限を構成します。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-102">Configure the Maximum Connection Limit to the SAP Server</span></span>
<span data-ttu-id="5a7e3-103">Data Provider for SAP では、プロバイダーによって内部的に開くことができる接続の最大数を制御するアダプターのクライアントが使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-103">The Data Provider for SAP enables adapter clients to control the maximum number of connections that can be opened by the provider internally.</span></span> <span data-ttu-id="5a7e3-104">これは、CPIC_MAX_CONV、環境変数を設定して制御できます。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-104">You can control this by setting the environment variable, CPIC_MAX_CONV.</span></span>  
  
 <span data-ttu-id="5a7e3-105">など CPIC_MAX_CONV が任意の数値に設定されている場合、いつでも開かれている RFC 接続の数はその数値に等しいまたはそれよりも小さいデータになります。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-105">For example, if CPIC_MAX_CONV is set to any numerical value, the number of RFC connections opened at any time will be less than or equal to that numerical value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a7e3-106">数値はこの値を設定するプロセスと appdomain で個別にすべてのサーバーに対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-106">The numerical value will be applicable for every server individually under the process/appdomain which sets this value.</span></span>  
  
 <span data-ttu-id="5a7e3-107">"X"プロセス レベルでの環境変数が設定であると、A と B の両方の接続の最大数、2 台のサーバーに接続する場合、アプリケーションでは、SAP のデータ プロバイダーを使用して、たとえば、A と B になります"x"それぞれします。</span><span class="sxs-lookup"><span data-stu-id="5a7e3-107">For example, if an application using Data provider for SAP, has set its environment variable at process level to “x” and connects to two different servers A and B, then the maximum number of connections for both A and B will be “x” respectively.</span></span>