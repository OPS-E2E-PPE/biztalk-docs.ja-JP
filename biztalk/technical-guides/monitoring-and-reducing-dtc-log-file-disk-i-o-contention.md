---
title: 監視と軽減 DTC ログ ファイルのディスク I/O の競合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31168bd5b5643c6f60dec408c46e520d55b9a976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379420"
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a><span data-ttu-id="e248b-102">監視と、DTC ログ ファイルディスク I/O 競合の削減</span><span class="sxs-lookup"><span data-stu-id="e248b-102">Monitoring and Reducing DTC Log File Disk I/O Contention</span></span>
<span data-ttu-id="e248b-103">分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクション処理を要する環境でディスク I/O のボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="e248b-103">The Distributed Transaction Coordinator (DTC) log file can become a disk I/O bottleneck in transaction-intensive environments.</span></span> <span data-ttu-id="e248b-104">これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="e248b-104">This is especially true when using adapters that support transactions, such as SQL Server, MSMQ, or MQSeries, or in a multi-MessageBox environment.</span></span> <span data-ttu-id="e248b-105">トランザクション アダプターが DTC トランザクションを使用し、メッセージ ボックスの複数の環境によって、DTC トランザクションを広範に使用します。</span><span class="sxs-lookup"><span data-stu-id="e248b-105">Transactional adapters use DTC transactions, and multi-MessageBox environments make extensive use of DTC transactions.</span></span>  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a><span data-ttu-id="e248b-106">クラスター化および非クラスター化環境での使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="e248b-106">Monitoring Usage in Clustered and Non-Clustered Environments</span></span>  
 <span data-ttu-id="e248b-107">DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、ディスクの SQL Server データベース サーバーでは、DTC ログ ファイルが存在する場所、ディスク I/O の使用量を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e248b-107">To ensure that the DTC log file does not become a disk I/O bottleneck, you should monitor the disk I/O usage for the disk where the DTC log file resides on the SQL Server database server.</span></span>  
  
 <span data-ttu-id="e248b-108">SQL Server がクラスター化された環境でない問題の多くが複数のスピンドルを備えた高速な SAN ドライブ、共有ドライブ ログ ファイルが既に存在するためです。</span><span class="sxs-lookup"><span data-stu-id="e248b-108">In an environment where SQL Server is clustered, this is not as much of a concern because the log file will already be on a shared drive, which will likely be a fast SAN drive with multiple spindles.</span></span> <span data-ttu-id="e248b-109">非クラスター化の環境または DTC ログ ファイルが他のハード ディスク ファイルと共有ディスクであるときにボトルネックになるためそれでもまだディスク I/O の使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="e248b-109">You should nevertheless still monitor the disk I/O usage since it can become a bottleneck in non-clustered environments or when the DTC log file is on a shared disk with other disk-intensive files.</span></span>  
  
## <a name="troubleshooting-dtc"></a><span data-ttu-id="e248b-110">DTC のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e248b-110">Troubleshooting DTC</span></span>  
 <span data-ttu-id="e248b-111">DTC のトラブルシューティング方法の詳細については、"のトラブルシューティングの問題で MSDTC"で BizTalk Server のヘルプを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)します。</span><span class="sxs-lookup"><span data-stu-id="e248b-111">For information about troubleshooting DTC, see "Troubleshooting Problems with MSDTC" in BizTalk Server Help at [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e248b-112">参照</span><span class="sxs-lookup"><span data-stu-id="e248b-112">See Also</span></span>  
 [<span data-ttu-id="e248b-113">チェックリスト:Windows Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="e248b-113">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)