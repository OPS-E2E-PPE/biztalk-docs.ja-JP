---
title: SQL アダプター サンプルのしくみ |Microsoft Docs
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
ms.openlocfilehash: 4e59df235628539786917d7aa483e23a18d7c87c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279068"
---
# <a name="how-the-sql-adapter-sample-works"></a><span data-ttu-id="b5d42-102">SQL アダプター サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="b5d42-102">How the SQL Adapter Sample Works</span></span>
<span data-ttu-id="b5d42-103">SQL Adapter サンプルは、ルーティング サービスとトランス フォームのメッセージング サービスで構成されているサンプルの双方向旅程を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5d42-103">The SQL Adapter sample provides a sample two-way itinerary configured with the routing service and a transform messaging service.</span></span>  
  
 <span data-ttu-id="b5d42-104">ルーティングのサービスを構成するには、静的なリゾルバーは、という名前の WCF カスタム アダプターのプロバイダーを使用して InsertProduct GlobalBankESB データベース内の SQL ストアド プロシージャを実行するメッセージをルーティングする必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5d42-104">The routing service is configured with a STATIC resolver, which specifies that the message should be routed to execute a SQL stored procedure within the GlobalBankESB database named InsertProduct using the WCF-Custom adapter provider.</span></span>  
  
 <span data-ttu-id="b5d42-105">変換サービスでは、受信メッセージを InsertProduct ストアド プロシージャによって受け入れられる形式に変換するマップを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5d42-105">The transform service specifies a map that converts the incoming message to the format accepted by the InsertProduct stored procedure.</span></span>