---
title: グループ内の他のコンピューター上の通知サービスを有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9787c5ac1371f6743285a151e5666d12b592a300
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969256"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>グループ内の別のコンピューターで通知サービスを有効にする方法
複数コンピューター環境で BAM を実行するときに、各コンピューターを実行するアクティビティを展開する BAM 管理ユーティリティで Notification Services を有効にする必要があります。  
  
 以下のシナリオについて考えてみます。  
  
-   グループ A は、次のコンピューターで構成されます。  
  
    -   コンピューター 1 は、BAM 管理コンピューターとして使用されます。  
  
    -   コンピューター 2 は、BAM PIT およびスター スキーマ データベースをホストします。  
  
    -   コンピューター 3 は、BAM アーカイブ データベースおよび分析データベースをホストします。  
  
    -   コンピューター 4 は、BAM 警告データベースをホストします。  
  
    -   コンピューター 5 は、それ以外の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをホストします。  
  
-   グループ B:  
  
    -   コンピューター 6 は、BAM 管理コンピューターとして使用され、すべてのデータベースをグループ A と共有します。  
  
 グループ B のコンピューターからグループ A のデータベースにアクティビティを展開するには、最初に、Notification Services をホストする [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に Notification Services を登録する必要があります。 Notification Services が登録されていない場合は、次のエラー メッセージが表示されます。  
  
 Deploying Alert...エラー: BAM 展開に失敗しました。  
  
 警告は展開されませんでした。  
  
 呼び出しのターゲットが例外をスローしました。  
  
 指定した Notification Services のインスタンスのレジストリ エントリが見つかりませんでした。  
  
### <a name="to-register-notifications-services-additional-computers"></a>通知サービスの追加コンピューターを登録するには  
  
1.  コンピューターで別のグループで、をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2005**をクリックして**の構成ツール**、クリックして**Notification Services コマンド プロンプト**です。  
  
2.  コマンド プロンプトで次のように入力します。: **nscontrol register 名前\<NS プレフィックス名の構成時に選択\>-サーバー \<ns db sql server\>** です。 これにより、Notification Services が適切なデータベースに接続できるようになります。この情報は、nscontrol により、サービス コンピューターのレジストリに格納されます。  
  
## <a name="see-also"></a>参照  
 [BAM ランタイムの設定を変更します。](../core/changing-bam-runtime-settings.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)