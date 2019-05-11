---
title: 送信を作成して、受信ポート |Microsoft Docs
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
ms.openlocfilehash: 808c3d7295031832852ca40596a77a369aedb507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353574"
---
# <a name="creating-send-and-receive-ports"></a>送信を作成して、受信ポート
次の手順を使用して作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信および受信ポートを BizTalk adapter for JD Edwards OneWorld します。  
  
## <a name="creating-a-port"></a>ポートを作成します。  
  
#### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、送信ポートを作成するアプリケーションです。  
  
3.  右クリック**送信ポート**クリック**新規**、順にクリックします**静的な送信請求-応答ポート**します。  
  
4.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
    -   **名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SSOSendToJDE OneWorld`)。  
  
    -   **型**ドロップダウン リストで、 **JDEdwards**します。  
  
    -   **送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。  
  
    -   **送信パイプライン**、 **[microsoft.biztalk.defaultpipelines.xmltransmit]** します。  
  
    -   **受信パイプライン**、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  
  
5.  **[OK]** をクリックします。  
  
## <a name="creating-a-receive-port"></a>作成、受信ポート  
  
#### <a name="to-create-a-receive-port"></a>受信ポートを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、送信ポートを作成するアプリケーションです。  
  
3.  右クリック**受信ポート**クリック**新規**、順にクリックします**一方向の受信ポート**します。  
  
     **一方向受信ポートのプロパティ**画面で、**名前**フィールドに「 `ReceiveFromHttp`、順にクリックします**OK**します。  
  
4.  次の情報を入力、**一方向受信ポートのプロパティ**ウィンドウ。  
  
    -   **名前**フィールドに「`ReceiveFromHTTP`します。  
  
    -   **トランスポートの種類**、 **HTTP**します。  
  
5.  アドレス (URI) で省略記号 (...) ボタンをクリックします。  
  
     ![](../core/media/siebeladapter-32-ssodemo-httptransport.gif "SiebelAdapter_32_SSODemo_HTTPTransport")  
  
    1.  仮想ディレクトリと ISAPI 拡張、/mySSODemo/BTSHTTPReceive.dll を設定します。  
  
    2.  選択**成功した場合の戻り値の関連付けハンドル**します。  
  
    3.  選択**使用してシングル サインオン**、順にクリックします**OK**します。  
  
6.  **受信ハンドラー**ドロップダウン リストで、 **BizTalkServerIsolatedHost**します。  
  
     ![](../core/media/siebeladapter-33-ssodemo-receivelocationproperty.gif "SiebelAdapter_33_SSODemo_ReceiveLocationProperty")  
  
7.  **受信パイプライン**を選択します**microsoft.biztalk.defaultpiplelines.xmlreceive**、 をクリックし、 **OK**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)