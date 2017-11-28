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
ms.openlocfilehash: e4cd2cd1eadf3dc6f11a6e3178258caaaf88006d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="dbc9c-102">A4SWIFT データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="dbc9c-103">日常的に、致命的な障害のリスクを低減するため、BizTalk Server および A4SWIFT のシステムのデータベースをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="dbc9c-104">BizTalk Server ソース システム、および A4SWIFT データベースにこれらのデータベースがあります。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="dbc9c-105">に加えて、リスクを低減するには、これはすることもできます大きなサイズに拡大できる A4SWIFT 履歴ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="dbc9c-106">BizTalk Server ソース システム内のデータベースのバックアップの詳細についてを参照してください「および復元する BizTalk Server データベースのバックアップ」で、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span> <span data-ttu-id="dbc9c-107">このトピックでは、BizTalk データベースのバックアップを使用する BizTalk Server のバックアップ ジョブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="dbc9c-108">A4SWIFT データベースのバックアップの詳細については、トピックでは、「方法に戻るをカスタム データベース」を参照してください。[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span> <span data-ttu-id="dbc9c-109">このトピックでは、カスタムの A4SWIFT データベースを含めるに BizTalk Server のバックアップ ジョブを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbc9c-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>