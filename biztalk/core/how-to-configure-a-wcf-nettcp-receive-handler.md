---
title: "Wcf-nettcp 受信ハンドラーを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69598bc1ce0bda41269fa91a0618fb040e741b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a>WCF-NetTcp 受信ハンドラーを構成する方法
WCF-NetTcp 受信ハンドラーを構成するには、次の手順を使用します。  
  
### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a>WCF-NetTcp 受信ハンドラーのグローバル変数を変更するには  
  
1.  BizTalk 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**Wcf-nettcp**、右側のペインで、構成する受信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **全般** タブで、をクリックして**プロパティ**の**受信ハンドラー**  タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**接続の最大数**|リスナーが保持することができる、アプリケーションによる受け入れを待機する接続の最大数を指定します。 この数を超えた場合、新しい受信接続は受け入れを待機する代わりに削除されます。<br /><br /> 既定値は、10 です。|  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [Wcf-nettcp アダプターを構成します。](../core/configuring-the-wcf-nettcp-adapter.md)   
 [WCF サービスの公開](../core/publishing-wcf-services.md)