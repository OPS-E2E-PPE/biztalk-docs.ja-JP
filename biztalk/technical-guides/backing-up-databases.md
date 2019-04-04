---
title: データベースのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0524a8f0-15a3-4731-a7bd-c0c935fff6c8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b3d3e488c1bae99e343f5ff6d5a15b826138459
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980067"
---
# <a name="backing-up-databases"></a>データベースのバックアップ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数データベース間で分散トランザクションを使用して、BizTalk Server のバックアップ ジョブは、すべての同期のバックアップを作成します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 これは、マークされたデータベースの「完全」復旧モデルでトランザクションを使用して実現されます。 バックアップするデータベース間での一貫性が必要です。 詳細については、次を参照してください。 ["マークされたトランザクション、完全バックアップ、およびログ バックアップ"](http://go.microsoft.com/fwlink/?LinkId=151565) (<http://go.microsoft.com/fwlink/?LinkId=151565>) で、BizTalk Server のドキュメント。  
  
## <a name="advantages-of-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server のジョブの利点  
 BizTalk Server のバックアップ ジョブはバックアップするためだけにサポートされているメソッド、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]バックアップ ジョブを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境でデータベースがサポートされていません。  
  
 場合、バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブが実行されない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース トランザクション ログが際限なく大きくなります。 バックアップ ジョブには、無限に大きくように、トランザクション ログが切り捨てられます。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース トランザクション ログは増大し続けるが書くことがある時点で、ディスクに格納します。  
  
> [!NOTE]
>  バックアップの両方を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブとログ配布は現在、完全に記載されているし、のみを実行するためのメソッドをサポートされている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースのバックアップと復元。  
  
## <a name="guidelines-for-the-backup-biztalk-server-job"></a>バックアップ BizTalk Server のジョブに関するガイドライン  
 全体を復元する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を定期的にします。 SQL server だけでなくこれが含まれています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースも実行しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 文書化し、実際に障害が発生する前に、これらの手順を練習する必要があります。  
  
> [!NOTE]
>  バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブでは、古いバックアップ ファイルは削除されません。 定義し、古いバックアップ ファイルをアーカイブして、バックアップ ジョブを使用するバックアップ ディレクトリからに移動するプロセスを整備する必要があります。  
  
## <a name="additional-resources"></a>その他のリソース  
 次のトピックを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
- 特定の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バックアップし復元のタスクを参照してください[「チェックリスト:: バックアップと復元」](http://go.microsoft.com/fwlink/?LinkId=154070) (<http://go.microsoft.com/fwlink/?LinkId=154070>)。  
  
- バックアップと復元の概要については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください["し、復元する BizTalk Server のバックアップ"](http://go.microsoft.com/fwlink/?LinkId=154071) (<http://go.microsoft.com/fwlink/?LinkId=154071>)。  
  
- BizTalk Server のバックアップ ジョブを構成する方法の詳細については、["方法を構成、Backup BizTalk Server ジョブ"](http://go.microsoft.com/fwlink/?LinkId=154072) (http://go.microsoft.com/fwlink/?LinkId=154072)を参照してください。  
  
## <a name="see-also"></a>参照  
 [ディザスター リカバリーのための BizTalk Server ログ配布の使用](../technical-guides/using-biztalk-server-log-shipping-for-disaster-recovery.md)