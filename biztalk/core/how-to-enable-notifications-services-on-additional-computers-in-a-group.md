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
ms.openlocfilehash: 97319d9bef68aa29be1c8de04b1f876a1bb778d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337991"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>グループ内の別のコンピューターで通知サービスを有効にする方法
複数コンピューター環境で BAM を実行するときに、各コンピューターを実行するアクティビティを展開する BAM 管理ユーティリティで Notification Services を有効にする必要があります。  
  
 次のシナリオを考えてみましょう。  
  
- グループ A は、次のコンピューターで構成されます。  
  
  - コンピューター 1 は、BAM 管理コンピューターとして使用されます。  
  
  - コンピューター 2 は、BAM PIT およびスター スキーマ データベースをホストします。  
  
  - コンピューター 3 では、BAM アーカイブ、および分析データベースをホストします。  
  
  - コンピューター 4 は、BAM 警告データベースをホストします。  
  
  - 残りの部分をホストするコンピューター 5[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
- グループ b:  
  
  -   コンピューター 6 は、グループ A のすべてのデータベースを共有、BAM 管理コンピューターとして使用されます。  
  
  グループ B のコンピューターからグループ A 内のデータベースにアクティビティを展開できるようにするで Notification Services を最初に登録する必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]通知サービスをホストします。 Notification Services が登録されていない場合は、次のエラーを受け取ります。  
  
  アラートをデプロイしています.ERROR:BAM の展開に失敗しました。  
  
  警告は展開されませんでした。  
  
  呼び出しのターゲットによって例外がスローされました。  
  
  Notification Services の指定したインスタンスのレジストリ エントリが見つかりませんでした。  
  
### <a name="to-register-notifications-services-additional-computers"></a>通知サービスの追加のコンピューターを登録するには  
  
1.  コンピューター別のグループで、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をクリック**Microsoft SQL Server 2005**、 をクリック**構成ツール。**、 をクリックし、 **Notification Services コマンド プロンプト**します。  
  
2.  コマンド プロンプトで「: **nscontrol register 名前\<構成に選択した NS プレフィックス名\>-サーバー \<ns db の sql server\>** します。 これにより、Notification Services が適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンできます。  
  
## <a name="see-also"></a>参照  
 [BAM ランタイムの設定を変更します。](../core/changing-bam-runtime-settings.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)