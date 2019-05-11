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
ms.openlocfilehash: 0e4b12b84ed107c07055a75ace23fea368040935
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383618"
---
# <a name="how-to-turn-off-global-tracking"></a>グローバル追跡を無効にする方法
既定では、BizTalk Server をインストールするときに、グローバル追跡が有効にします。 BizTalk 追跡 (BizTalkDTADb) データベースのサイズとしてが増加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム上のデータを処理します。 BizTalk 追跡データベースのサイズには、ディスク パフォーマンスの低下が発生する場合は、追跡データベースからデータを削除できます。 一時的に、BizTalk 追跡データベースを削除することで対処はパフォーマンスの問題が発生した、不要になった追跡情報を収集する BizTalk を構成する場合は、グローバル追跡を無効にすることを検討する可能性があります。  
  
 グローバル追跡をオフにすると、全体の追跡インターセプターが無効にしますを理解することが重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 これは、BizTalk 追跡テーブル内のイベントは追跡しないことを意味します。 また、個々 のイベントの追跡をオフにすることができます。  
  
> [!NOTE]
>  ビジネス アクティビティ監視 (BAM) を使用している場合は、グローバル追跡を無効にした場合でも、専用の追跡ホストを維持する必要があります。 BAM イベントは、Tracking Data Decode Service (TDDS) を使用するためです。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a>グローバル追跡 (SQL Server 2008) をオフにするには  
  
1. BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL server で、をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。  
  
2. **サーバーへの接続**ダイアログ ボックスで、サーバー名と認証を確認し、順にクリックします**Connect**します。  
  
3. Microsoft SQL Server Management studio で**オブジェクト エクスプ ローラー**、展開\<*コンピューター名*\>、展開**データベース**の展開**BizTalkMgmtDb**、展開**テーブル**を右クリックして**adm_group**、 をクリックし、**テーブルを開く**します。  
  
4. テーブル ビューアーで水平方向にスクロールが見つかるまで**GlobalTrackingOption**します。  
  
5. **GlobalTrackingOption**列、値 1 から、この機能を無効にする場合は 0 に変更し、ENTER キーを押します。  
  
6. Microsoft SQL Server Management Studio を閉じます。  
  
   > [!NOTE]
   >  有効にする変更は、BizTalk ホストを再起動する必要があります。  
  
7. クリックして**開始**、 をクリックして**プログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
8. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**ホスト インスタンスの**します。  
  
9. 詳細ペインで、各ホストを右クリックし、**再起動**します。  
  
## <a name="see-also"></a>参照  
 [アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)   
 [BizTalk 追跡データベースからデータを手動で削除する方法](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)