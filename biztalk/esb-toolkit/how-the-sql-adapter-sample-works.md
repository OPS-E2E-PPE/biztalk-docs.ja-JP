---
title: SQL アダプタのサンプルのしくみ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ff56f2f2f88d35290ffd897d107910e206ac98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294010"
---
# <a name="how-the-sql-adapter-sample-works"></a><span data-ttu-id="b44a3-102">SQL アダプタのサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="b44a3-102">How the SQL Adapter Sample Works</span></span>
<span data-ttu-id="b44a3-103">SQL Adapter サンプルは、ルーティング サービスとトランス フォームのメッセージング サービスで構成されているサンプルの双方向旅程を提供します。</span><span class="sxs-lookup"><span data-stu-id="b44a3-103">The SQL Adapter sample provides a sample two-way itinerary configured with the routing service and a transform messaging service.</span></span>  
  
 <span data-ttu-id="b44a3-104">ルーティングのサービスを構成するには、静的なリゾルバーは、Wcf-custom アダプター プロバイダーを使用して InsertProduct をという名前の GlobalBankESB データベース内で SQL ストアド プロシージャを実行する、メッセージをルーティングする必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="b44a3-104">The routing service is configured with a STATIC resolver, which specifies that the message should be routed to execute a SQL stored procedure within the GlobalBankESB database named InsertProduct using the WCF-Custom adapter provider.</span></span>  
  
 <span data-ttu-id="b44a3-105">変換サービスでは、受信メッセージを InsertProduct ストアド プロシージャによって受け入れられる形式に変換するマップを指定します。</span><span class="sxs-lookup"><span data-stu-id="b44a3-105">The transform service specifies a map that converts the incoming message to the format accepted by the InsertProduct stored procedure.</span></span>