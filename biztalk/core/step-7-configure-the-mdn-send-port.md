---
title: '手順 7: MDN 送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e65ac8f264e1d8784c97645383b055391397da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987747"
---
# <a name="step-7-configure-the-mdn-send-port"></a>手順 7: MDN 送信ポートを構成します。
![手順 11 の 7](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")  
  
 この手順で設定する動的送信ポートに非同期 MDN を送信する、 \\_MDNToFabrikam フォルダー。 この送信ポートは、AS2Send 送信パイプラインを使用して送信 MDN 応答を生成します。 これは、動的送信ポートであるためにはアドレスを使用、メッセージのヘッダーの Receipt-delivery-option 行にするメッセージをルーティングする、 \\_MDNToFabrikam フォルダー。 そのアドレスは Fabrikam 仮想ディレクトリです。 その仮想ディレクトリに関連付けられている Default.aspx.cs ファィルは、.msg 拡張子を使用して MDN を構築し、このファイルを送信先のフォルダに送信します。送信先のフォルダも Receipt-Delivery-Option に指定されています。  
  
> [!NOTE]
>  また、メッセージ設定をアグリーメント設定でオーバーライドすることで、別のアドレスに MDN を送信するようアグリーメントを構成することもできます。 詳細については、「  
  
 この例で、MDN は動的送信ポートを使用して送信されます。しかし、静的送信ポートを使用して MDN を静的アドレスに送信することもできます。 詳細については、次を参照してください。 [AS2 経由での非同期 Mdn の静的送信ポートを構成する](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)と[AS2 経由での非同期 Mdn の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a>Send_Async_MDN 送信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**送信ポート**、 をポイント**新規**、 をクリックし、**動的の一方向送信ポート**.  
  
2. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**Send_Async_MDN**します。  
  
3. 選択**AS2Send**の**送信パイプライン**します。  
  
   > [!NOTE]
   >  MDN には EDI 処理が不要であるため、AS2Send パイプラインが使用されます。  
  
4. クリックして**フィルター**コンソール ツリーでします。 フィルター ペインで選択**EdiIntAS.IsAS2AsynchronousMdn**の**プロパティ**、 **==** の**演算子**、しを入力します**True**の**値**します。  
  
   > [!NOTE]
   >  このフィルタにより、動的送信ポートは MessageBox から非同期の MDN のみを抽出するようになります。  
  
5. **[OK]** をクリックします。  
  
6. **送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**Send_Async_MDN**、順にクリックします**開始**します。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**Send_Async_997**) を 997 受信確認を Fabrikam に返信」の説明に従って[手順 8: 997 送信ポート構成](../core/step-8-configure-the-997-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 経由での非同期 Mdn の静的送信ポートを構成します。](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)   
 [AS2 経由でのメッセージの動的送信ポートの構成](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)