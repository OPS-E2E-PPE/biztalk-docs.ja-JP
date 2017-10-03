---
title: "ディスク領域使用率の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ae87de0b00e70ae03a30dd8ef20ede4a972388d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-disk-space-usage"></a><span data-ttu-id="1e369-102">ディスク領域使用率の監視</span><span class="sxs-lookup"><span data-stu-id="1e369-102">Monitoring Disk Space Usage</span></span>
<span data-ttu-id="1e369-103">運用の準備の監視プロセスの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のように使用されるディスク領域を監視します。</span><span class="sxs-lookup"><span data-stu-id="1e369-103">As part of the monitoring process for operational readiness of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], monitor the disk space usage as follows:</span></span>  
  
-   <span data-ttu-id="1e369-104">**ディスクの判断に必要な領域。**</span><span class="sxs-lookup"><span data-stu-id="1e369-104">**Determine the disk space required.**</span></span>  
  
     <span data-ttu-id="1e369-105">File または MSMQ を使用して、送信/受信場所、ときにの障害に対応できる十分なディスク領域があることを確認してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または受信側システムです。</span><span class="sxs-lookup"><span data-stu-id="1e369-105">When using File or MSMQ send / receive locations, ensure that there is ample disk space available to accommodate outages of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or of the receiving systems.</span></span> <span data-ttu-id="1e369-106">たとえば場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SAN の共有への書き込みファイルは、受信側システム ダウン 2 日間、ファイルをキューに登録できるようにするには、十分なディスク領域があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1e369-106">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is writing files to a share on a SAN and the receiving system is down for two days, determine whether there is enough disk space to allow the files to queue up.</span></span>  
  
-   <span data-ttu-id="1e369-107">**BizTalk Server のバックアップ ファイルのディレクトリを定期的にクリーンアップします。**</span><span class="sxs-lookup"><span data-stu-id="1e369-107">**Clean up the BizTalk Server backup files directory periodically.**</span></span>  
  
     <span data-ttu-id="1e369-108">SQL Server エージェント ジョブから呼び出されるスクリプトを使用してこのクリーンアップを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1e369-108">You can perform this cleanup using a script called from a SQL Server Agent job.</span></span>  
  
-   <span data-ttu-id="1e369-109">**BizTalk 追跡データベースのアーカイブ ファイル ディレクトリを定期的にクリーンアップします。**</span><span class="sxs-lookup"><span data-stu-id="1e369-109">**Clean up the BizTalk Tracking database archive files directory periodically.**</span></span>  
  
-   <span data-ttu-id="1e369-110">**ピーク時のデータ フローの時間帯に大規模な BizTalk Server データベース (.mdf) とトランザクション ログ (.ldf) ファイルに対応する十分なディスク領域があることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="1e369-110">**Ensure that there is sufficient disk space available to accommodate larger BizTalk Server database (.mdf) and transaction log (.ldf) files during times of peak data flow.**</span></span>