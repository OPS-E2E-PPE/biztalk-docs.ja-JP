---
title: '手順 2: 変更または作成、送信および受信ポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa94183f0eb83dc51fc0add22ba50484f7282fb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a>手順 2: 変更または作成、送信および受信ポート
ファイルの送信ポートと受信ポートをバッチにする必要がありますでチュートリアルをバッチ処理/です。 クリックした場合、 **Launch Tutorial**の Enterprise Edition のインストールの最後にあるボタン[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]これらのポートが自動的に作成: Tutorial_BTAHL7Drop をという名前の送信ポートと受信ポートを Tutorial_BTAHL7PickUp をという名前です。 これらのポートがあれば、Tutorial_BTAHL7Drop の送信ポートを変更する必要があります。  
  
 場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップしなかったいない作成、送信および受信ポート、このトピックでは「を作成する、BIBOTutorialPickup 受信ポート」の手順を参照しておよびし、このトピックでも「を作成する、BIBOTutorialDrop 送信ポート」の手順を参照してください。  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a>Tutorial_BTAHL7Drop 送信ポートを変更するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**です。  
  
3.  をクリックして**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、クリックして**プロパティ**です。  
  
4.  コンソール ツリーでクリックして**フィルター**です。  
  
5.  **フィルター**ウィンドウの選択] の 2 番目の行で、 **BTAHL7Schemas.MessageClass**の**プロパティ**[ **==**の**演算子**、および種類**MessageClass2X**の**値**です。 **Enter**をクリックします。  
  
6.  設定**Group By**上、 **BTS です。ReceivePortName**の行を**または**、順にクリック**OK**です。  
  
7.  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理 ウィンドウで展開**プラットフォームの設定**、展開と**ホスト インスタンス**です。 右クリック **BizTalkServerApplication**, 、クリックして **再起動**します。  
  
    > [!NOTE]
    >  Standard Edition をインストールした場合のみ、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、しなかった場合、または、 **Launch Tutorial**を設定するときにボタン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a>Tutorial_BTAHL7Pickup 受信ポートと受信場所を作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**です。  
  
3.  右クリック **受信ポート**, 、 をポイント **新規**, 、クリックして **一方向の受信ポート**します。  
  
4.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_BTAHL7PickUp**です。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
6.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
7.  [受信ポート] ダイアログ ボックスのをクリックして**Tutorial_BTAHL7PickUp**、クリックして**OK**です。  
  
8.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_FileReceiveLoc**です。  
  
9. **トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。  
  
10. クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
11. ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|参照 **\<***ドライブ***\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7PickUp for**. **注:**これは、パス、ファイル システムまたはパブリック共有上の場所にどこから[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は、ファイルを取得します。|  
    |**ファイル マスク**|型 **\*.txt**です。|  
  
12. **[OK]**をクリックします。  
  
13. 受信場所のプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信ハンドラー**|保持**BizTalkServerApplication**として選択します。|  
    |**受信パイプライン**|選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。|  
  
14. **[OK]**をクリックします。  
  
15. BizTalk エクスプ ローラーで右クリック**Tutorial_FileReceiveLoc**、クリックして**を有効にする**です。  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a>Tutorial_BTAHL7Drop 送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_BTAHL7Drop**です。|  
    |**型**|選択**ファイル**ドロップダウン リストからです。|  
    |**構成します。**|をクリックして**構成**を開くには、 **FILE トランスポートのプロパティ** ダイアログ ボックス。|  
  
3.  ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール先フォルダー**|参照 **\<***ドライブ***:\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BTAHL7Drop for**. **注:**これは、ファイル システムまたはパブリックの共有の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイルを記述します。|  
    |**[ファイル名]**|型**%MessageID%.txt** (拡張機能は、txt、xml ではないことに注意してください)。|  
  
4.  **[OK]**をクリックします。  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**ドロップダウン リストからです。  
  
6.  コンソール ツリーでクリックして **フィルター**, 、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。ReceivePortName**ドロップダウン リストからです。|  
    |**演算子**|ままにして**==**演算子とします。|  
    |**値**|型**Tutorial_BTAHL7PickUp**です。|  
    |**グループ化**|選択**または**ドロップダウン リストからです。|  
    |**プロパティ**|選択**BTAHL7Schemas.MessageClass**です。|  
    |**演算子**|ままにして**==**演算子とします。|  
    |**値**|型**MessageClass2X**です。|  
  
7.  **Enter**をクリックします。 ダイアログ ボックスの下部にあるペインでフィルター式が正しいことを確認してください。  
  
8.  **[OK]**をクリックします。  
  
9. 管理コンソールで、をクリックして**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、クリックして**開始**です。  
  
10. 展開**プラットフォームの設定**、クリックして**ホスト インスタンス**です。 右クリック **BizTalkServerApplication**, 、クリックして **再起動**します。  
  
 進みます[手順 3: バッチ処理をテスト/シナリオをバッチ](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)です。