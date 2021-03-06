---
title: 手順 6:EDI AS2 を構成する受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d72735d128a2afbad003eacb0662dba3c98fde0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244312"
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a>手順 6:EDI AS2 を構成する受信場所
![手順 11 の 6](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")  
  
 セットアップでは、一方向の受信を Fabrikam パーティから EDI メッセージを受け取る場所。 これは、受信場所は、AS2EdiReceive 受信パイプラインを受信 EDI および AS2 メッセージを処理します。 メッセージは、BTSHTTPReceive.dll ISAPI 拡張機能を使用して、Contoso 仮想ディレクトリ経由で sender.exe アプリケーションによって受信場所に送信されします。  
  
 このチュートリアルでは、MDN 応答を非同期に送信に動的送信ポートを設定します。 このシナリオで、一方向受信ポートのみが必要です。 ただし、同期 MDN を指定する AS2 メッセージを送信する Sender.exe を変更することもできます。 双方向を作成する必要がありますし、要求応答の受信 MDN を返すためのポート。 詳細については、のソリューションのテスト"するには」セクションを参照してください。[チュートリアル (AS2)。同期 MDN による AS2 経由での EDI の受信](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-biztalk-http-receive-location"></a>BizTalk HTTP 受信場所を作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**.  
  
2. 受信ポートに名前を付けます**Receive_AS2**します。  
  
3. をクリックして**受信場所**コンソール ツリーをクリックで**新規**します。  
  
4. **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所**Receive_AS2**を選択します**HTTP**の**型**、し、クリックして**構成**します。  
  
5. **HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。 **[OK]** をクリックします。  
  
6. 選択**AS2EdiReceive**の**受信パイプライン**します。 をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
   > [!NOTE]
   >  AS2EdiReceive 受信パイプラインは AS2 のデコードと EDI の逆アセンブルを実行します。  
  
7. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**[BizTalk アプリケーション 1] ノードを右クリックして**Receive_AS2**、 をクリックし、**を有効にする**.  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**Send_Asynch_MDN**)」の説明に従って、非同期 MDN を Fabrikam に送信するポートを送信[手順 7。MDN の送信ポート構成](../core/step-7-configure-the-mdn-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [AS2 経由でのメッセージの受信ポートの構成](../core/configuring-a-receive-port-for-messages-over-as2.md)