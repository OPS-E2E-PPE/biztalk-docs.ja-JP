---
title: '手順 6: 受信確認のバッチの送信ポートを作成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 958746634776e9b01c32ff2425122312bc7a841c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960952"
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a>手順 6: 受信確認のバッチの送信ポートを作成します。
この手順では、送信元パーティを作成する受信確認のバッチを配信する送信ポートを作成します。 これは、ファイル アダプターの種類に静的な一方向のポートです。 ここで、ソース (\Tutorial_BatchACKDrop) のファイルのフォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチ ファイルが削除されます。 ポートで送信する受信確認のバッチの種類を示すポートのフィルターを定義するとします。 フィルターは、Tutorial_BatchSource と OutboundBatch のメッセージの種類のソースを指定します。  
  
### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a>受信確認のバッチの送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_BatchSource**です。|  
    |**型**|選択**ファイル**ドロップダウン リストからです。|  
    |**構成します。**|をクリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。|  
  
3.  ファイル トランスポートのプロパティ ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**インストール先フォルダー**|参照 **\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BatchACKDropのアクセラレータ**. これは、ファイル システムまたはパブリックの共有の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチを含んでいるファイルを記述します。|  
    |**[ファイル名]**|型 **%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。|  
    |**[コピー モード]**|選択**新規作成**です。|  
  
4.  **[OK]** をクリックします。  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
6.  コンソール ツリーでクリックして **フィルター**, 、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|下のフィールドをクリックして**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストからです。|  
    |**演算子**|ままにして **==** 演算子とします。|  
    |**値**|型**Tutorial_BatchSource**です。|  
    |**グループ化**|選択**と**ドロップダウン リストからです。|  
    |**プロパティ**|選択**BTAHL7Schemas.BTAHL7MessageType**です。|  
    |**演算子**|ままにして **==** 演算子とします。|  
    |**値**|型**OutboundBatch**です。|  
  
7.  **Enter**キーを押します。 クリックしてダイアログ ボックスの下部にあるペインで、フィルター式の入力が正しいことを確認してください**OK**です。  
  
8.  BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchSource**、順にクリック**開始**です。  
  
### <a name="to-associate-the-send-port-with-the-source-party"></a>送信元パーティに送信ポートを関連付ける  
  
1.  BizTalk 管理コンソールで、をクリックして**パーティ**です。 右クリック**Tutorial_BatchSource**、クリックして**プロパティ**です。  
  
2.  [パーティのプロパティ] ダイアログ ボックスで、**送信ポート**コンソール ツリーでします。 **送信ポート** **Tutorial_BatchSource**クリックしてドロップダウン リストから**OK**です。  
  
 進みます[手順 7: オーケストレーションを開始し、BizTalk Server を再起動](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)です。