---
title: A4SWIFT データベースのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e69325509131c6ea1674c3f6c3b6153f3ea2f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378660"
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="410fc-102">A4SWIFT データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="410fc-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="410fc-103">致命的な障害のリスクを軽減する BizTalk Server と A4SWIFT システムは、データベースを定期的にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="410fc-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="410fc-104">これらのデータベースには、BizTalk Server ソース システム、および A4SWIFT データベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="410fc-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="410fc-105">リスクを削減だけでなく大きなサイズに拡大できる A4SWIFT 履歴ファイルを削除することを実現これはもします。</span><span class="sxs-lookup"><span data-stu-id="410fc-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="410fc-106">BizTalk Server ソース システムで、データベースのバックアップの詳細については、BizTalk Server ヘルプで「し、復元する BizTalk Server データベースのバックアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410fc-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the BizTalk Server Help.</span></span> <span data-ttu-id="410fc-107">このトピックでは、BizTalk データベースをバックアップするために使用する BizTalk Server のバックアップ ジョブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="410fc-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="410fc-108">A4SWIFT データベースをバックアップする方法の詳細については、BizTalk Server ヘルプの「方法に戻るをカスタム データベース」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="410fc-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in BizTalk Server Help.</span></span> <span data-ttu-id="410fc-109">このトピックでは、カスタムの A4SWIFT データベースを含めるに BizTalk Server のバックアップ ジョブを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="410fc-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>