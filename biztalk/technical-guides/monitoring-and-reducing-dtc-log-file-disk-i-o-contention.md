---
title: "ディスク I/O の競合を監視および DTC ログを削減できるファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca71b55c2f9e18875ef67e840e8dac18a81dddac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a><span data-ttu-id="391ad-102">監視と、DTC ログ ファイルのディスク I/O の競合を減らす</span><span class="sxs-lookup"><span data-stu-id="391ad-102">Monitoring and Reducing DTC Log File Disk I/O Contention</span></span>
<span data-ttu-id="391ad-103">分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクションに依存する環境でディスク I/O のボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="391ad-103">The Distributed Transaction Coordinator (DTC) log file can become a disk I/O bottleneck in transaction-intensive environments.</span></span> <span data-ttu-id="391ad-104">これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="391ad-104">This is especially true when using adapters that support transactions, such as SQL Server, MSMQ, or MQSeries, or in a multi-MessageBox environment.</span></span> <span data-ttu-id="391ad-105">トランザクション アダプターが DTC トランザクションを使用して、マルチ メッセージ ボックス環境 DTC トランザクションを広範に使用します。</span><span class="sxs-lookup"><span data-stu-id="391ad-105">Transactional adapters use DTC transactions, and multi-MessageBox environments make extensive use of DTC transactions.</span></span>  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a><span data-ttu-id="391ad-106">クラスター化および非クラスター化環境で使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="391ad-106">Monitoring Usage in Clustered and Non-Clustered Environments</span></span>  
 <span data-ttu-id="391ad-107">DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、するには、ディスク DTC ログ ファイルが SQL Server データベース サーバーに常駐するディスクの I/O の使用量を監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="391ad-107">To ensure that the DTC log file does not become a disk I/O bottleneck, you should monitor the disk I/O usage for the disk where the DTC log file resides on the SQL Server database server.</span></span>  
  
 <span data-ttu-id="391ad-108">SQL Server がクラスター化された環境では、これがありませんできるだけ多くの問題にならなければなので、ログ ファイルは既に共有ドライブが含まれ、複数のスピンドルを高速な SAN ドライブが場合があります。</span><span class="sxs-lookup"><span data-stu-id="391ad-108">In an environment where SQL Server is clustered, this is not as much of a concern because the log file will already be on a shared drive, which will likely be a fast SAN drive with multiple spindles.</span></span> <span data-ttu-id="391ad-109">それでもまだクラスター化されていない環境またはときに、DTC ログ ファイルは他の大量のディスク ファイルで共有ディスク上でボトルネックになるため、ディスク I/O の使用状況を監視してください。</span><span class="sxs-lookup"><span data-stu-id="391ad-109">You should nevertheless still monitor the disk I/O usage since it can become a bottleneck in non-clustered environments or when the DTC log file is on a shared disk with other disk-intensive files.</span></span>  
  
## <a name="troubleshooting-dtc"></a><span data-ttu-id="391ad-110">DTC のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="391ad-110">Troubleshooting DTC</span></span>  
 <span data-ttu-id="391ad-111">DTC のトラブルシューティングについては、"のトラブルシューティングの問題で MSDTC"BizTalk Server ヘルプを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)です。</span><span class="sxs-lookup"><span data-stu-id="391ad-111">For information about troubleshooting DTC, see "Troubleshooting Problems with MSDTC" in BizTalk Server Help at [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391ad-112">参照</span><span class="sxs-lookup"><span data-stu-id="391ad-112">See Also</span></span>  
 [<span data-ttu-id="391ad-113">チェックリスト: Windows Server の構成</span><span class="sxs-lookup"><span data-stu-id="391ad-113">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)