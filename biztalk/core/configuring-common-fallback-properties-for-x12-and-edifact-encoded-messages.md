---
title: エンコードされたメッセージの共通フォールバック プロパティの X12 および EDIFACT の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7393d6ac-b901-43ef-a8d6-c5b0b3033257
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6f15f3ae839be446cfb10581a3514cc9093d641
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356130"
---
# <a name="configuring-common-fallback-properties-for-x12-and-edifact-encoded-messages"></a>X12 および EDIFACT でエンコードされたメッセージの共通フォールバック プロパティの構成
フォールバック プロパティは、X12 (HIPAA を含む)、および EDIFACT エンコード インターチェンジの両方に適用されます。 これらのプロパティはすべてのフォールバック アグリーメント プロパティを持つ場合にのみを適用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するアグリーメントが決定されていないに、受信メッセージまたは送信メッセージが解決されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-set-common-global-properties"></a>共通グローバル プロパティを設定するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノード、およびクリック**X12 フォールバックの設定**または**EDIFACT フォールバックの設定**します。  
  
2. **フォールバック設定の 全般 ページ** タブで、**全般**ページで、次の操作を行います。  
  
   1. クリックして**フォールバックの設定を有効にする**有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントが受信または送信メッセージに対して解決されない場合は、フォールバック アグリーメント設定を使用します。  
  
      > [!IMPORTANT]
      >  このオプションがチェックされていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はフォールバック アグリーメントで設定されたプロパティを使用しません。  
  
   2. クリックして**EDI レポートをアクティブ**すべての EDI メッセージのレポートをアクティブにします。 これにより、状態レポートの下部にあるリンクをクリックして表示される画面に、メッセージが表示されます、**グループ ハブ**BizTalk Server 管理コンソールのウィンドウ。  
  
   3. クリックした場合は**EDI レポートをアクティブ**、 をクリックして**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。  
  
   4. クリックして**ログ EDI エラーおよび警告の Windows イベント ログに EDI エンジンによって生成された**コンテキストで、EDI エンジン (EDI パイプライン、バッチ処理オーケストレーション、ルーティング オーケストレーションなど) によって生成されるエラー/警告メッセージを記録するにはWindows イベント ビューアーにします。 オフの場合、これらのエラー/警告メッセージは、イベント ビューアーに記録されません。  
  
      > [!NOTE]
      >  システム/処理エラーは、このチェック ボックスが選択されているかどうかを示す、イベント ビューアーに記録されます。  
  
3. クリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**を検証し、変更を確定し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [グローバルまたはフォールバック アグリーメントのプロパティの構成](../core/configuring-global-or-fallback-agreement-properties.md)