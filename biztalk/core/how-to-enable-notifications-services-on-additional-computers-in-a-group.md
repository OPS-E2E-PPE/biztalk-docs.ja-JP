---
title: グループの他のコンピューターで通知サービスを有効にする方法 |Microsoft Docs
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
ms.openlocfilehash: 0fd8a1a49be2416fb8b7fe5d160dd5228a95e94f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983395"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>グループ内の別のコンピューターで通知サービスを有効にする方法
複数コンピューター環境で BAM を実行するときに、各コンピューターを実行するアクティビティを展開する BAM 管理ユーティリティで Notification Services を有効にする必要があります。  
  
 以下のシナリオについて考えてみます。  
  
- グループ A は、次のコンピューターで構成されます。  
  
  - コンピューター 1 は、BAM 管理コンピューターとして使用されます。  
  
  - コンピューター 2 は、BAM PIT およびスター スキーマ データベースをホストします。  
  
  - コンピューター 3 は、BAM アーカイブ データベースおよび分析データベースをホストします。  
  
  - コンピューター 4 は、BAM 警告データベースをホストします。  
  
  - コンピューター 5 は、それ以外の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースをホストします。  
  
- グループ B:  
  
  -   コンピューター 6 は、BAM 管理コンピューターとして使用され、すべてのデータベースをグループ A と共有します。  
  
  グループ B のコンピューターからグループ A のデータベースにアクティビティを展開するには、最初に、Notification Services をホストする [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に Notification Services を登録する必要があります。 Notification Services が登録されていない場合は、次のエラー メッセージが表示されます。  
  
  Deploying Alert...エラー: BAM を展開できませんでした。  
  
  警告は展開されませんでした。  
  
  呼び出しのターゲットが例外をスローしました。  
  
  指定した Notification Services のインスタンスのレジストリ エントリが見つかりませんでした。  
  
### <a name="to-register-notifications-services-additional-computers"></a>通知サービスの追加コンピューターを登録するには  
  
1.  コンピューター別のグループで、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をクリック**Microsoft SQL Server 2005**、 をクリック**構成ツール。**、 をクリックし、 **Notification Services コマンド プロンプト**します。  
  
2.  コマンド プロンプトで「: **nscontrol register 名前\<構成に選択した NS プレフィックス名\>-サーバー \<ns db の sql server\>** します。 これにより、Notification Services が適切なデータベースに接続できるようになります。この情報は、nscontrol により、サービス コンピューターのレジストリに格納されます。  
  
## <a name="see-also"></a>参照  
 [BAM ランタイムの設定を変更します。](../core/changing-bam-runtime-settings.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)