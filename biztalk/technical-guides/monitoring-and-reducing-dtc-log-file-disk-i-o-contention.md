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
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a>監視と、DTC ログ ファイルディスク I/O 競合の削減
分散トランザクション コーディネーター (DTC) ログ ファイルは、トランザクション処理を要する環境でディスク I/O のボトルネックになります。 これは、トランザクション、またはマルチ メッセージ ボックス環境で SQL Server、MSMQ、MQSeries などをサポートするアダプターを使用する場合に特に当てはまります。 トランザクション アダプターが DTC トランザクションを使用し、メッセージ ボックスの複数の環境によって、DTC トランザクションを広範に使用します。  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a>クラスター化および非クラスター化環境での使用状況の監視  
 DTC ログ ファイルがディスク I/O のボトルネックにならないことを確認するには、ディスクの SQL Server データベース サーバーでは、DTC ログ ファイルが存在する場所、ディスク I/O の使用量を監視する必要があります。  
  
 SQL Server がクラスター化された環境でない問題の多くが複数のスピンドルを備えた高速な SAN ドライブ、共有ドライブ ログ ファイルが既に存在するためです。 非クラスター化の環境または DTC ログ ファイルが他のハード ディスク ファイルと共有ディスクであるときにボトルネックになるためそれでもまだディスク I/O の使用状況を監視します。  
  
## <a name="troubleshooting-dtc"></a>DTC のトラブルシューティング  
 DTC のトラブルシューティング方法の詳細については、"のトラブルシューティングの問題で MSDTC"で BizTalk Server のヘルプを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)します。  
  
## <a name="see-also"></a>参照  
 [チェックリスト:Windows Server を構成します。](../technical-guides/checklist-configuring-windows-server.md)