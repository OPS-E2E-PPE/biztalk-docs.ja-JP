---
title: エラー報告を有効にする |Microsoft ドキュメント
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
ms.openlocfilehash: ca862a57bfd2389f3be2b7ff6932ed356232abc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241250"
---
# <a name="enabling-error-reporting"></a>エラー報告の有効化
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、強化されたエラーと警告を Windows イベント ビューアーに表示するかどうかを選択できます。  
  
 次の手順を実行すると、EDI のレポート機構または EDI エンジンによって生成されたエラーおよび警告の報告を有効または無効にできます。 このようなエラーおよび警告の報告は、アグリーメントの一部として、またはフォールバック アグリーメントの一部として有効にできます。 アグリーメントの一部としては、この報告は既定で有効になっています。 フォールバック アグリーメントの一部としては、この報告は既定で無効になっています。 ただし、によって生成されるシステム/処理エラー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イベント ビューアーに記録は常に (入力によって表示される`eventvwr`で、**実行** ダイアログ ボックス)、EDI エラーおよび警告が有効になっているかどうかどうか、します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-error-reporting-for-an-agreement"></a>アグリーメントのエラー報告を有効にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**、ノードをクリックして、**パーティ**ノード。  
  
2.  **パーティとビジネス プロファイル** ウィンドウで、エラーのログ記録とイベント ログに警告を有効にする X12 または EDIFACT アグリーメントを含むパーティをクリックします。  
  
    > [!NOTE]
    >  AS2 アグリーメントのエラーおよび警告をイベント ビューアーに記録することはできません。  
  
3.  **契約**セクションで、エラーのログ記録と警告を有効にして、をクリックする X12 または EDIFACT アグリーメントを右クリックして**プロパティ**です。  
  
4.  **共通のホスト設定**セクションで、**エラーをイベント ログに記録**または**警告イベント ログを記録**です。  
  
5.  をクリックして**OK**  をクリックしてまたは**適用**です。  
  
### <a name="to-enable-error-reporting-as-part-of-a-fallback-agreement"></a>フォールバック アグリーメントの一部としてのエラー報告を有効にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**パーティ**ノードの下、 **BizTalk グループ**ノードをクリックして**X12 フォールバック設定**または**EDIFACT フォールバックの設定**です。  
  
2.  **フォールバック設定の全般ページ** タブで、BizTalk EDI エンジンによって生成された警告または EDI エラーのログ記録を有効にする をクリックして**EDI エラーおよびログを Windows イベント ログEDIエンジンによって生成された警告**. エラー ログには、エラーのデータとコンテキスト情報が含まれます。  
  
    > [!NOTE]
    >  システム/処理エラーは、このチェック ボックスのオン/オフに関係なく、イベント ビューアーに記録されます。  
  
    > [!NOTE]
    >  選択する必要はありません、 **EDI レポートをアクティブ化**プロパティを選択するために、 **EDI エラーおよびログを Windows イベント ログの EDI エンジンによって生成された警告**プロパティです。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI 受信確認エラー コード](../core/edi-acknowledgment-error-codes.md)   
 [AS2 のイベント](../core/as2-events.md)