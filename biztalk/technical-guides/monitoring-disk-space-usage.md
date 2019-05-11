---
title: ディスク領域の使用状況の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12a0b8f020457679f2769e188e8c1936a1cb1869
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253347"
---
# <a name="monitoring-disk-space-usage"></a><span data-ttu-id="4c562-102">ディスク領域の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="4c562-102">Monitoring Disk Space Usage</span></span>
<span data-ttu-id="4c562-103">運用準備状況の監視プロセスの一部として[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のように使用されるディスク領域を監視します。</span><span class="sxs-lookup"><span data-stu-id="4c562-103">As part of the monitoring process for operational readiness of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], monitor the disk space usage as follows:</span></span>  

- <span data-ttu-id="4c562-104">**ディスクの決定に必要な領域。**</span><span class="sxs-lookup"><span data-stu-id="4c562-104">**Determine the disk space required.**</span></span>  

   <span data-ttu-id="4c562-105">送信/受信場所を使用して File または MSMQ を使用しているときの障害に対応するために使用可能な十分なディスク領域があることを確認します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または受信側システム。</span><span class="sxs-lookup"><span data-stu-id="4c562-105">When using File or MSMQ send / receive locations, ensure that there is ample disk space available to accommodate outages of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or of the receiving systems.</span></span> <span data-ttu-id="4c562-106">たとえば場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]キューにファイルを許可するには、十分なディスク領域があるかどうか、SAN の共有への書き込みファイルは、受信側のシステムが 2 日間がダウンします。</span><span class="sxs-lookup"><span data-stu-id="4c562-106">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is writing files to a share on a SAN and the receiving system is down for two days, determine whether there is enough disk space to allow the files to queue up.</span></span>  

- <span data-ttu-id="4c562-107">**BizTalk Server のバックアップ ファイルのディレクトリを定期的にクリーンアップします。**</span><span class="sxs-lookup"><span data-stu-id="4c562-107">**Clean up the BizTalk Server backup files directory periodically.**</span></span>  

   <span data-ttu-id="4c562-108">SQL Server エージェント ジョブから呼び出されるスクリプトを使用してこのクリーンアップを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4c562-108">You can perform this cleanup using a script called from a SQL Server Agent job.</span></span>  

- <span data-ttu-id="4c562-109">**BizTalk 追跡データベースのアーカイブ ファイル ディレクトリを定期的にクリーンアップします。**</span><span class="sxs-lookup"><span data-stu-id="4c562-109">**Clean up the BizTalk Tracking database archive files directory periodically.**</span></span>  

- <span data-ttu-id="4c562-110">**大規模な BizTalk Server データベース (.mdf) とトランザクション ログ (.ldf) ファイルをデータ フローのピーク時間帯に対応するために十分なディスク領域があることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="4c562-110">**Ensure that there is sufficient disk space available to accommodate larger BizTalk Server database (.mdf) and transaction log (.ldf) files during times of peak data flow.**</span></span>
