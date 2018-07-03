---
title: '手順 6: 受信確認のバッチの送信ポートを作成する |Microsoft Docs'
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
ms.openlocfilehash: 3f38b8c7f8e2f486e4de6feca12bf69551221428
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005003"
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a>手順 6: 受信確認のバッチの送信ポートを作成します。
この手順では、送信元パーティを作成する受信確認のバッチを配信する送信ポートを作成します。 これは、ファイル アダプターの種類を静的な一方向のポートです。 場所のソース (\Tutorial_BatchACKDrop) ファイルのフォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチ ファイルが削除されます。 ポートで送信する受信確認のバッチの種類を示すポートのフィルターを定義します。 フィルターには、Tutorial_BatchSource と OutboundBatch のメッセージの種類のソースを指定します。  

### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a>受信確認のバッチの送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |   プロパティ    |                              目的                               |
   |---------------|-----------------------------------------------------------------------|
   |   **名前**    |                    型**Tutorial_BatchSource**します。                     |
   |   **型**    |               選択**ファイル**ドロップダウン リストから。                |
   | **構成** | クリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。 |


3. ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  


   |        プロパティ        |                                                                                                                                                                              目的                                                                                                                                                                               |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | 参照する **\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_BatchACKDropのアクセラレータ**. これは、ファイル システムまたはパブリックの共有上の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信確認のバッチを含んでいるファイルに書き込まれます。 |
   |     **[ファイル名]**      |                                                                                                                                            型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。                                                                                                                                             |
   |     **コピー モード**      |                                                                                                                                                                        選択**新規作成**です。                                                                                                                                                                         |


4. **[OK]** をクリックします。  

5. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

6. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                                                              目的                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **プロパティ** | 下のフィールドをクリックします。**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストから。 |
   | **[演算子]** |                                                    まま**==** 演算子として。                                                     |
   |  **[値]**   |                                                    型**Tutorial_BatchSource**します。                                                    |
   | **グループ化** |                                               選択**と**ドロップダウン リストから。                                                |
   | **プロパティ** |                                             選択**BTAHL7Schemas.BTAHL7MessageType**します。                                              |
   | **[演算子]** |                                                    まま**==** 演算子として。                                                     |
   |  **[値]**   |                                                       型**OutboundBatch**します。                                                        |


7. **Enter**キーを押します。 クリックしてダイアログ ボックスの下部にあるウィンドウで、フィルター式の入力が正しいことを確認します**OK**します。  

8. BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchSource**、 をクリックし、**開始**。  

### <a name="to-associate-the-send-port-with-the-source-party"></a>送信元パーティに送信ポートを関連付ける  

1. BizTalk 管理コンソールで、次のようにクリックします。**パーティ**します。 右クリックして**Tutorial_BatchSource**、 をクリックし、**プロパティ**します。  

2. パーティのプロパティ] ダイアログ ボックスで、[**送信ポート**コンソール ツリーでします。 **送信ポート**を選択します**Tutorial_BatchSource**クリックしてドロップダウン リストから**OK**します。  

   続行する[手順 7: オーケストレーションの開始し、BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)します。