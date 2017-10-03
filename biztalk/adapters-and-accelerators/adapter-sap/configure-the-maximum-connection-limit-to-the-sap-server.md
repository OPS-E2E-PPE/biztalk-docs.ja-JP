---
title: "SAP サーバーに最大接続数を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 858ed90e-b219-43cc-ad63-ae8e1eb2159a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 853a3b78b82e242750e30099f847045ff590f125
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-maximum-connection-limit-to-the-sap-server"></a><span data-ttu-id="afab1-102">SAP サーバーに最大接続数を構成します。</span><span class="sxs-lookup"><span data-stu-id="afab1-102">Configure the Maximum Connection Limit to the SAP Server</span></span>
<span data-ttu-id="afab1-103">Data Provider 用 SAP では、プロバイダーによって内部的に開くことのできる接続の最大数を制御するアダプターのクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="afab1-103">The Data Provider for SAP enables adapter clients to control the maximum number of connections that can be opened by the provider internally.</span></span> <span data-ttu-id="afab1-104">これは、CPIC_MAX_CONV、環境変数を設定して制御できます。</span><span class="sxs-lookup"><span data-stu-id="afab1-104">You can control this by setting the environment variable, CPIC_MAX_CONV.</span></span>  
  
 <span data-ttu-id="afab1-105">たとえば、CPIC_MAX_CONV が任意の数値に設定されている場合、いつでも開く RFC 接続の数はその数値に等しいまたはそれよりも少なくなります。</span><span class="sxs-lookup"><span data-stu-id="afab1-105">For example, if CPIC_MAX_CONV is set to any numerical value, the number of RFC connections opened at any time will be less than or equal to that numerical value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afab1-106">数値はすべてのサーバーにある個別のプロセス/アプリケーション ドメインがこの値の設定の適用になります。</span><span class="sxs-lookup"><span data-stu-id="afab1-106">The numerical value will be applicable for every server individually under the process/appdomain which sets this value.</span></span>  
  
 <span data-ttu-id="afab1-107">"X"プロセス レベルでの環境変数が設定であると、A と B の両方の接続の最大数、2 台のサーバーに接続する場合、SAP 用データ プロバイダーを使用してアプリケーションをたとえば、A と B になります"x"それぞれします。</span><span class="sxs-lookup"><span data-stu-id="afab1-107">For example, if an application using Data provider for SAP, has set its environment variable at process level to “x” and connects to two different servers A and B, then the maximum number of connections for both A and B will be “x” respectively.</span></span>