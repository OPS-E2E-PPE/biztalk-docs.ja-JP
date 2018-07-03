---
title: MQSeries アダプターの送信を構成し、ハンドラーを受信する方法 |Microsoft Docs
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
ms.openlocfilehash: 88c97b109146dadd1a5cc90710f00c9c8f6620f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988899"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>MQSeries アダプターを構成する方法は、送信し、受信ハンドラー
MQSeries アダプターの送信ハンドラーと受信ハンドラーの一部のプロパティは、BizTalk Server 管理コンソールを使用して構成できます。 プロセスが記載[MQSeries アダプター受信場所の構成、送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)大部分の送信ハンドラのプロパティの値を設定します。  

## <a name="to-configure-the-send-and-receive-handlers"></a>送信ハンドラーと受信ハンドラーを構成するには  
 MSQeries アダプターの送信ハンドラーと受信ハンドラーを構成するには、次の手順を実行します。  

1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**を順にクリックします。展開**アダプター**します。  

3. 展開したアダプターの一覧で選択**MQSeries**します。 右ペインには、MQSeries アダプターにバインドされている送信ハンドラーと受信ハンドラーの一覧が表示されます。  

4. 右ペインで、送信ハンドラーまたは受信ハンドラーをダブルクリックします。  

5. **アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**します。  

6. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |           プロパティ            |                                    目的                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | **バッチ内の最大メッセージ数** | バッチ内に含めるメッセージの最大数を設定します。 送信ハンドラーにのみ適用されます。 |
   |          **[サーバー]**           |      MQSeries Server for Windows が実行されているコンピューターの名前を指定します。       |


7. **[OK]** をクリックします。  

   > [!NOTE]
   >  受信場所のプロパティと送信ポートのプロパティは、受信ハンドラーの値と送信ハンドラーの値をオーバーライドします。 受信場所のプロパティまたは送信ポートのプロパティに値が設定されていない場合、アダプターでは、それぞれ受信ハンドラーの値と送信ハンドラーの値を使用します。  

8. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)