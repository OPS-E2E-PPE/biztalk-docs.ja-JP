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
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a>監視と、DTC ログ ファイルのディスク I/O の競合を減らす
分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクションに依存する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用して、マルチ メッセージ ボックス環境 DTC トランザクションを広範に使用します。  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a>クラスター化および非クラスター化環境で使用状況の監視  
 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、するには、ディスク DTC ログ ファイルが SQL Server データベース サーバーに常駐するディスクの I/O の使用量を監視する必要があります。  
  
 SQL Server がクラスター化された環境では、これがありませんできるだけ多くの問題にならなければなので、ログ ファイルは既に共有ドライブが含まれ、複数のスピンドルを高速な SAN ドライブが場合があります。 それでもまだクラスター化されていない環境またはときに、DTC ログ ファイルは他の大量のディスク ファイルで共有ディスク上でボトルネックになるため、ディスク I/O の使用状況を監視してください。  
  
## <a name="troubleshooting-dtc"></a>DTC のトラブルシューティング  
 DTC のトラブルシューティングについては、"のトラブルシューティングの問題で MSDTC"BizTalk Server ヘルプを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)です。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: Windows Server の構成](../technical-guides/checklist-configuring-windows-server.md)