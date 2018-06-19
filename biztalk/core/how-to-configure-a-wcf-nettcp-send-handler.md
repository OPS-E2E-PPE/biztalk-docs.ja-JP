---
title: Wcf-nettcp 送信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02451dba6755e4db0c10d7cce20141468a67694f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247914"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a>WCF-NetTcp 送信ハンドラーを構成する方法
WCF-NetTcp 送信ハンドラーを構成するには、次の手順を使用します。  
  
### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a>WCF-NetTcp 送信ハンドラーのグローバル変数を変更するには  
  
1.  BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、送信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **全般** タブで、をクリックして**プロパティ**です。 **送信ハンドラー**  タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続の最大数**|接続プール内にキャッシュされている各エンドポイントの最大送信接続数を指定します。 これによって、一意のリモート エンドポイントのそれぞれに対してキャッシュされる接続数が制限されます。 この値は、一意のリモート エンドポイントに対してキャッシュされることを想定している最大接続数よりも大きい値に設定する必要があります。 アクティブな送信接続数がこの最大値を超えると、サービスが、この送信ハンドラーで実行されている WCF-NetTcp 送信ポートに応答していないように見える場合があります。<br /><br /> 既定値は、10 です。|  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [WCF サービスの使用](../core/consuming-wcf-services.md)   
 [Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md)