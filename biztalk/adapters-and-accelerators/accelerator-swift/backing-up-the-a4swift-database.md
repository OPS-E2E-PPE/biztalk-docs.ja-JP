---
title: "A4SWIFT データベースのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4102d459d5b579491f42747f1d3fe0dd3d381b71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="b3a57-102">A4SWIFT データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="b3a57-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="b3a57-103">日常的に、致命的な障害のリスクを低減するため、BizTalk Server および A4SWIFT のシステムのデータベースをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b3a57-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="b3a57-104">BizTalk Server ソース システム、および A4SWIFT データベースにこれらのデータベースがあります。</span><span class="sxs-lookup"><span data-stu-id="b3a57-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="b3a57-105">に加えて、リスクを低減するには、これはすることもできます大きなサイズに拡大できる A4SWIFT 履歴ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3a57-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="b3a57-106">BizTalk Server 送信元システムで、データベースのバックアップの詳細については、BizTalk Server ヘルプの「および復元する BizTalk Server データベースのバックアップ」」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a57-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the BizTalk Server Help.</span></span> <span data-ttu-id="b3a57-107">このトピックでは、BizTalk データベースのバックアップを使用する BizTalk Server のバックアップ ジョブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3a57-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="b3a57-108">A4SWIFT データベースをバックアップする方法については、BizTalk Server ヘルプの「方法に戻るをカスタム データベース」のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a57-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in BizTalk Server Help.</span></span> <span data-ttu-id="b3a57-109">このトピックでは、カスタムの A4SWIFT データベースを含めるに BizTalk Server のバックアップ ジョブを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b3a57-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>