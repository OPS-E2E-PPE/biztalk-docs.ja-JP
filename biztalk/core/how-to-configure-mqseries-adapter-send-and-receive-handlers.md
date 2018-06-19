---
title: 受信ハンドラーを MQSeries アダプターの送信を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1e933f62adaf4e17fae5334e65f50610fb6f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248234"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>MQSeries アダプターを構成する方法は、送信し、受信ハンドラー
MQSeries アダプターの送信ハンドラーと受信ハンドラーの一部のプロパティは、BizTalk Server 管理コンソールを使用して構成できます。 処理に示す[方法を構成する MQSeries アダプターの受信場所と送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)ほとんど送信ハンドラのプロパティの値を設定します。  
  
## <a name="to-configure-the-send-and-receive-handlers"></a>送信ハンドラーと受信ハンドラーを構成するには  
 MSQeries アダプターの送信ハンドラーと受信ハンドラーを構成するには、次の手順を実行します。  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**をクリックして展開**アダプター**です。  
  
3.  展開したアダプターの一覧で選択**MQSeries**です。 右ペインには、MQSeries アダプターにバインドされている送信ハンドラーと受信ハンドラーの一覧が表示されます。  
  
4.  右ペインで、送信ハンドラーまたは受信ハンドラーをダブルクリックします。  
  
5.  **アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**です。  
  
6.  **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**バッチ内の最大メッセージ数**|バッチ内に含めるメッセージの最大数を設定します。 送信ハンドラーにのみ適用されます。|  
    |**[サーバー]**|MQSeries Server for Windows が実行されているコンピューターの名前を指定します。|  
  
7.  **[OK]** をクリックします。  
  
    > [!NOTE]
    >  受信場所のプロパティと送信ポートのプロパティは、受信ハンドラーの値と送信ハンドラーの値より優先されます。 受信場所のプロパティまたは送信ポートのプロパティに値が設定されていない場合、アダプターでは、それぞれ受信ハンドラーの値と送信ハンドラーの値を使用します。  
  
8.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)