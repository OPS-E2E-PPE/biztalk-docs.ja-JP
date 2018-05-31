---
title: 作成する送信ポートと受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, receive ports
- adapters [JD Edwards OneWorld adapters], receive ports
- creating, receive ports [JD Edwards OneWorld adapters]
- send ports, creating [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], send ports
- adapters [JD Edwards OneWorld adapters], transport properties
- JD Edwards OneWorld adapters, send ports
- JD Edwards OneWorld adapters, transport properties
- receive ports, creating [JD Edwards OneWorld adapters]
- creating, send ports [JD Edwards OneWorld adapters]
ms.assetid: fb4ca8b1-40d9-4beb-a791-554086f8ca98
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4b117ca2d032ef1dc10731128acca903a51790
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014033"
---
# <a name="creating-send-and-receive-ports"></a>作成する送信ポートと受信ポート
次の手順を使用して、BizTalk Adapter for JD Edwards OneWorld 用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成します。  
  
## <a name="creating-a-port"></a>ポートを作成します。  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。  
  
3.  右クリック**送信ポート** をクリック**新規**、クリックして**静的な送信請求-応答ポート**です。  
  
4.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    -   **名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SSOSendToJDE OneWorld`)。  
  
    -   **型**ドロップダウン リストで、 **JDEdwards**です。  
  
    -   **送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。  
  
    -   **送信パイプライン** **microsoft.biztalk.defaultpipelines.xmltransmit**です。  
  
    -   **受信パイプライン** **microsoft.biztalk.defaultpiplelines.xmlreceive**です。  
  
5.  **[OK]** をクリックします。  
  
## <a name="creating-a-receive-port"></a>作成する、受信ポート  
  
#### <a name="to-create-a-receive-port"></a>受信ポートを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。  
  
3.  右クリック**受信ポート** をクリック**新規**、クリックして**一方向の受信ポート**です。  
  
     **一方向受信ポートのプロパティ**画面で、**名前**フィールドに「 `ReceiveFromHttp`、クリックしてして **[ok]** です。  
  
4.  次の情報を入力、**一方向受信ポートのプロパティ**ウィンドウ。  
  
    -   **名前**フィールドに「`ReceiveFromHTTP`です。  
  
    -   **トランスポートの種類** **HTTP**です。  
  
5.  [アドレス (URI)] の省略記号ボタン ([...]) をクリックします。  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  仮想ディレクトリと ISAPI 拡張 /mySSODemo/BTSHTTPReceive.dll を設定します。  
  
    2.  選択**関連付けハンドルを返す成功**です。  
  
    3.  選択**を使用してシングル サインオン**、順にクリック**OK**です。  
  
6.  **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerIsolatedHost**です。  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  **受信パイプライン** **microsoft.biztalk.defaultpiplelines.xmlreceive**をクリックし、 **ok**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)