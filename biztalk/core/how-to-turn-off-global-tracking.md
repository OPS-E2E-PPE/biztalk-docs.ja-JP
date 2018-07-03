---
title: グローバル追跡を無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e6ea49766bbb433c7fd142ee3c66ae1ee331292
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020578"
---
# <a name="how-to-turn-off-global-tracking"></a>グローバル追跡を無効にする方法
既定では、BizTalk Server をインストールするときに、グローバル追跡が有効にします。 システム上での [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によるデータ処理に伴って、BizTalk 追跡 (BizTalkDTADb) データベースのサイズが増加します。 BizTalk 追跡データベースのサイズの増加によってディスク パフォーマンスが低下する場合は、追跡データベースからデータを削除できます。 性能上の問題があり、BizTalk 追跡データベースを削除することで一時的に対処している場合、追跡情報を収集しないように BizTalk を構成するには、グローバル追跡を無効にすることを検討してください。  
  
 グローバル追跡を無効にすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループ全体の追跡インターセプターが無効になる点を理解しておくことが重要です。 これは、BizTalk が追跡テーブル内のイベントを追跡しないということを意味します。 または、個々のイベントの追跡を無効にすることもできます。  
  
> [!NOTE]
>  ビジネス アクティビティ監視 (BAM) を使用している場合は、グローバル追跡を無効にした場合でも専用の追跡ホストを保持する必要があります。 これは、BAM イベントが Tracking Data Decode Service (TDDS) を使用するためです。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a>グローバル追跡 (SQL Server 2008) をオフにするには  
  
1. BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL server で、をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2. **サーバーへの接続**ダイアログ ボックスで、サーバー名と認証を確認し、順にクリックします**Connect**します。  
  
3. Microsoft SQL Server Management studio で**オブジェクト エクスプ ローラー**、展開\<*コンピューター名*\>、展開**データベース**の展開**BizTalkMgmtDb**、展開**テーブル**を右クリックして**adm_group**、 をクリックし、**テーブルを開く**します。  
  
4. テーブル ビューアーで水平方向にスクロールが見つかるまで**GlobalTrackingOption**します。  
  
5. **GlobalTrackingOption**列、値 1 から、この機能を無効にする場合は 0 に変更し、ENTER キーを押します。  
  
6. Microsoft SQL Server Management Studio を終了します。  
  
   > [!NOTE]
   >  変更内容を有効にするには、BizTalk ホストを再起動する必要があります。  
  
7. クリックして**開始**、 をクリックして**プログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
8. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**ホスト インスタンスの**します。  
  
9. 詳細ペインで、各ホストを右クリックし、**再起動**します。  
  
## <a name="see-also"></a>参照  
 [アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)   
 [BizTalk 追跡データベースからデータを手動で削除する方法](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)