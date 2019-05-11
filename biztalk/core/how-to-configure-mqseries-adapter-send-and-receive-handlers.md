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
ms.openlocfilehash: 5b2b40729dfd8e1f6e4077149a3c360dc35cc81e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341309"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>MQSeries アダプターを構成する方法は、送信し、受信ハンドラー
送信のいくつかのプロパティを構成し、BizTalk Server 管理コンソールで、MQSeries アダプターのハンドラーを受信できます。 プロセスが記載[MQSeries アダプター受信場所の構成、送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)大部分の送信ハンドラのプロパティの値を設定します。  

## <a name="to-configure-the-send-and-receive-handlers"></a>ハンドラーを受信および送信を構成するには  
 MSQeries アダプターのハンドラーを受信および送信の構成は、次の手順に従います。  

1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**を順にクリックします。展開**アダプター**します。  

3. 展開したアダプターの一覧で選択**MQSeries**します。 一覧は、右側のウィンドウで表示されるアダプター、MQSeries にバインドされているハンドラーを送受信します。  

4. 右側のウィンドウでは、右側のウィンドウでの受信ハンドラーまたは送信をダブルクリックします。  

5. **アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**します。  

6. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |           プロパティ            |                                    目的                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | **バッチ内の最大メッセージ数** | バッチのメッセージの最大数を設定します。 送信ハンドラーにのみ適用されます。 |
   |          **[サーバー]**           |      Windows の MQSeries Server を実行しているコンピューターの名前。       |


7. **[OK]** をクリックします。  

   > [!NOTE]
   >  受信場所および送信ポートのプロパティは、受信ハンドラーと送信ハンドラーの値をオーバーライドします。 受信場所または送信ポートのプロパティの値がない場合、アダプターは、受信ハンドラーと送信ハンドラーの値をそれぞれ使用します。  

8. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)