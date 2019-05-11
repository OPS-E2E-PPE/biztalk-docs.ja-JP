---
title: エラー報告の有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1131bbd5-7ab3-4422-b6df-747c722f0b2c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0040e467bf77de9b55333862dadd87ff940bbeba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389310"
---
# <a name="enabling-error-reporting"></a>エラー報告を有効にします。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows イベント ビューアーで強化されたエラーと警告を表示するかどうかを選択できます。  
  
 次の手順では、有効またはエラーと、EDI レポート機構または EDI エンジンによって生成される警告の報告を無効にします。 このようなエラーの報告またはアグリーメントの一部として、またはフォールバック アグリーメントの一部としての警告を有効にすることができます。 アグリーメントの一部として、この報告は既定で有効にします。 フォールバック アグリーメントの一部として、この報告は既定で無効になります。 ただし、システム/処理エラーがによって生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は常に、イベント ビューアーに記録 (入力によって表示される`eventvwr`で、**実行** ダイアログ ボックス) かどうか、EDI エラーおよび警告が有効かどうか。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-error-reporting-for-an-agreement"></a>アグリーメントのエラー報告を有効にするには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**ノード、をクリックして、**パーティ**ノード。  
  
2. **パーティとビジネス プロファイル**ウィンドウで、エラーのログ記録とイベント ログに警告を有効にする X12 または EDIFACT アグリーメントのパーティをクリックします。  
  
   > [!NOTE]
   >  エラーと警告を AS2 アグリーメントは、イベント ビューアーにログインすることはできません。  
  
3. **契約**セクションをクリックして、エラーのログ記録と、警告を有効にする X12 または EDIFACT アグリーメントを右クリックして**プロパティ**します。  
  
4. **共通のホスト設定**セクションで、**エラーをイベント ログに記録**または**イベント ログに警告を記録**します。  
  
5. クリックして**OK**  をクリックしてまたは**適用**します。  
  
### <a name="to-enable-error-reporting-as-part-of-a-fallback-agreement"></a>フォールバック アグリーメントの一部としてのエラー報告を有効にするには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードの下、 **BizTalk グループ**ノード、およびクリック**X12 フォールバックの設定**または**EDIFACT フォールバックの設定**します。  
  
2. **フォールバック設定の全般ページ** タブで、および警告の BizTalk EDI エンジンによって生成された EDI エラーのログ記録を有効にする をクリックして**ログ EDI エラーおよび警告の Windows イベント ログにEDIエンジンによって生成された**. エラー ログには、エラー データとコンテキスト情報が含まれます。  
  
   > [!NOTE]
   >  システム/処理エラーは、このチェック ボックスが選択されているかどうかを示す、イベント ビューアーに記録されます。  
  
   > [!NOTE]
   >  選択する必要はありません、 **EDI レポートをアクティブ**プロパティを選択するには、**ログ EDI エラーおよび警告の Windows イベント ログに EDI エンジンによって生成された**プロパティ。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 受信確認エラー コード](../core/edi-acknowledgment-error-codes.md)   
 [AS2 のイベント](../core/as2-events.md)