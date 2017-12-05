---
title: "エンコードされたメッセージの共通フォールバック プロパティの X12 および EDIFACT の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b99d6e60a2a5955a9f0873156dbc5f822b3d519
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a>X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成
フォールバック プロパティは、X12 (HIPAA を含む) でエンコードされたインターチェンジと EDIFACT でエンコードされたインターチェンジの両方に適用されます。 すべてのフォールバック アグリーメント プロパティと同じく、これらのプロパティは、受信メッセージまたは送信メッセージが解決されるアグリーメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が特定していない場合にのみ適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-common-global-properties"></a>共通グローバル プロパティを設定するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードをクリックして**X12 フォールバック設定**または**EDIFACT フォールバックの設定**です。  
  
2.  **フォールバック設定の全般ページ** タブで、**全般** ページで、次の操作します。  
  
    1.  をクリックして**フォールバックの設定を有効にする**を有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが受信または送信メッセージに対して解決されない場合は、フォールバック アグリーメント設定を使用します。  
  
        > [!IMPORTANT]
        >  このオプションをオンにしない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメントで設定されたプロパティを使用しません。  
  
    2.  をクリックして**EDI レポートをアクティブ化**すべての EDI メッセージのレポートをアクティブにします。 これにより、状態レポートの下部にあるリンクをクリックして表示される画面に表示されるメッセージ、**グループ ハブ**BizTalk Server 管理コンソールのウィンドウ。  
  
    3.  クリックした場合は**EDI レポートをアクティブ化**、 をクリックして**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。  
  
    4.  をクリックして**EDI エラーおよびログを Windows イベント ログの EDI エンジンによって生成された警告**コンテキストで、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) によって生成されるエラー/警告メッセージを記録するにはについて、Windows イベント ビューアーにします。 オフにすると、これらのエラー/警告メッセージは、イベント ビューアーには記録されません。  
  
        > [!NOTE]
        >  システム/処理エラーは、このチェック ボックスのオン/オフに関係なく、イベント ビューアーに記録されます。  
  
3.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [グローバルまたはフォールバック アグリーメントのプロパティの構成](../core/configuring-global-or-fallback-agreement-properties.md)