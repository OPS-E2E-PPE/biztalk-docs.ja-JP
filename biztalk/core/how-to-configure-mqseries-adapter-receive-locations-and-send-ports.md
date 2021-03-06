---
title: アダプター受信場所と送信ポートを MQSeries を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, receive ports
- receive ports, MQSeries adapters
- MQSeries adapters, send ports
- configuring [MQSeries adapters], send ports
- configuring [MQSeries adapters], receive ports
- send ports, MQSeries adapters
- configuring [MQSeries adapters], receive locations
- MQSeries adapters, receive locations
- receive locations, MQSeries adapters
ms.assetid: 552aacde-9ec0-4459-b369-073676b6f926
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fee2200541bceeb8bfbe2f840a2070831a023e03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341373"
---
# <a name="how-to-configure-mqseries-adapter-receive-locations-and-send-ports"></a>アダプター受信場所と送信ポートを MQSeries を構成する方法
受信場所と送信ポートの両方については、MQSeries アダプターを構成できます。  

## <a name="to-configure-receive-locations-and-send-ports"></a>構成する受信場所と送信ポート  
 **受信ポートを作成すると、受信場所。**  

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開し、受信場所を作成するアプリケーションです。  

2. 右クリックし、**受信ポート**ノード、をクリックして**新規、**  をポイント**一方向の受信ポート**。  

3. 適切な値を入力して、**ポートのプロパティ** ダイアログ ボックス。 については、**ポートのプロパティ**ダイアログ ボックスを参照してください[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)します。  

4. 右クリックし、BizTalk Server 管理コンソールで、**受信ポート**ノードを作成し、をクリックし、**プロパティ**します。  

5. **受信ポートのプロパティ**ダイアログ ボックスで、左側のウィンドウで、**受信場所**、 をクリックし、**新規**右側のウィンドウでします。  

6. **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**の横**型**、 **MQSeries**ドロップダウン リストからボックスの一覧をクリックして**構成**します。  

7. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |        プロパティ        |                                                                                                                                                                                                                                                                                                                                                                                                                             目的                                                                                                                                                                                                                                                                                                                                                                                                                             |
   |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |     **バッチ サイズ**     | KB のメッセージのバッチの最大サイズを決定します。 **注:** 場合、**トランザクションがサポートされている**受信場所のプロパティに設定されて**はい**; Microsoft 分散トランザクションのコンテキストでメッセージ ボックス データベースに各メッセージ バッチが送信されます。コーディネーター (MSDTC) トランザクション。 バッチ内のすべてのメッセージをメッセージ ボックス データベースに保存し、適切なサブスクライバー キューに配置されるまで、メッセージ バッチ用に作成した MSDTC トランザクションが開いたままです。 として、この MSDTC トランザクションの期間を増加するため、**最大バッチ サイズ**パラメーターが増加します。 全体のパフォーマンスに悪影響 MSDTC トランザクションのオープンの数が多いを同時に持つため、**最大バッチ サイズ**トランザクションのサポートが有効にすると、パラメーターを非常に大きな値に設定しない必要があります。 |
   | **順次処理** |                                                                                                                                                                                                                                                                                         MQSeries キューから受信するときに、メッセージの順序を維持するために MQSeries を設定します。 **注:** メッセージの特定のキューの順序を維持するために 1 つだけの BizTalk ホスト インスタンスはメッセージを受信する MQSeries キューから。 <br /><br /> **既定値:** False                                                                                                                                                                                                                                                                                          |
   |       **キュー**        |                                                                                                                                                                                                                                                                                                                                                     情報の入力、**キュー定義** ダイアログ ボックス。 **注:** URI を送信ポートまたは受信場所が 256 文字を超えることはできません。                                                                                                                                                                                                                                                                                                                                                      |
   |   **トランザクション**    |                                                                                                                                                                                                                                                                                                                   アダプターでは、BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始します。 設定すると**いいえ**、メッセージ配信の保証はありません。<br /><br /> **既定値:** False                                                                                                                                                                                                                                                                                                                   |


8. **MQSeries トランスポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**を設定する、**アドレス (URI)** ボックスに、**受信場所のプロパティ** ダイアログ ボックス。  

9. **受信場所のプロパティ** ダイアログ ボックスに、受信場所の構成を完了し、をクリックするには、適切な値を入力して、 **OK**設定を保存します。 **[受信場所のプロパティ]** ダイアログ ボックスの詳細については、「 [受信場所を作成する方法](../core/how-to-create-a-receive-location.md)」を参照してください。  

   **送信ポートを作成します。**  

10. BizTalk Server 管理コンソールでは、新しい静的な送信ポートを作成します。 参照してください[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)詳細についてはします。 すべての送信ポートのオプションを構成し、指定**MQSeries**の**型**オプション、**トランスポート**のセクション、**全般**タブ。  

11. **全般**] タブで、**トランスポート**セクションで、[、**構成**横に**型**します。  

12. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  

    |プロパティ|説明|  
    |--------------|-----------------|  
    |**フラグメント化サイズ**|アダプターと MQSAgent との間でデータが送信されるときのメッセージを (KB 単位) のメッセージ チャンク サイズを設定します。|  
    |**SSO 関連アプリケーション**|シングル サインオン (SSO) 関連アプリケーションを設定します。 ユーザー ID と SSO のパスワードの使用は、 **MQMD_UserIdentifier**、および**MQIIH_Authenticator** (または**MQCIH_Authenticator**) プロパティそれぞれします。<br /><br /> **既定値:** 空白|  
    |**データ変換**|メッセージを MQSeries for Windows server の ANSI コード ページに変換します。<br /><br /> 選択**はい**Unicode から ANSI に変換を実行します。<br /><br /> **既定値:** いいえ|  
    |**順序付け**|MQSeries が、MQSeries キューに送信されるときに、メッセージの順序を維持するために設定します。<br /><br /> 選択**はい**メッセージの順序を維持するためにします。 **注:** 設定する必要があります、**配信通知**プロパティに、オーケストレーションで**送信**送信ポート。 <br /><br /> **既定値:** いいえ|  
    |**キュー定義**|情報を設定、**キュー定義** ダイアログ ボックスのフィールドに直接またはします。 **注:** URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|  
    |**セグメント化の許可**|個々 のメッセージが MQSeries キューのメッセージの最大長を超える場合は、MQSeries キュー マネージャーのセグメント化を使用します。 選択した場合**はい**、MQSeries キューにセグメント化されたメッセージを格納します。<br /><br /> **既定値:** いいえ|  
    |**トランザクションのサポート**|アダプターでは、BizTalk Server と MQSeries Server 間の DTC トランザクションを開始します。 設定すると**いいえ**、メッセージ配信の保証はありません。<br /><br /> **既定値:** [はい]**に注意してください。** 異なる送信ポートを構成しなかった**トランザクションがサポートされている**設定は、同じ MQSeries キューにメッセージを送信します。 **注:** テストのシナリオを除いてこのを常にプロパティの既定値に**はい**します。 このプロパティの値を設定**いいえ**で実稼働環境予期しない問題が発生する可能性があります。|  

     次の図は、これらのプロパティを構成する方法を示します。  

     ![MQSeries トランスポートのプロパティ ダイアログ ボックス](../core/media/bts-dev-mqsendtransportprops.gif "BTS_Dev_MQSendTransportProps")  

13. 省略記号をクリックします (**.**) の右側にボタン、**キュー定義**ボックスは、キューを定義します。 使用することができます、**エクスポート**ダイアログ ボックスで、同じようで、受信場所は、すぐにキューを作成するキューを定義するスクリプトをエクスポートしたりする必要があります。  

14. クリックして**OK**閉じて設定を保存するには、各ダイアログ ボックスでします。  

    **送信ポートを参加させる、送信ポートを起動し、受信場所を有効にします。**  

15. 送信ポートを右クリックし、をクリックして**参加**送信ポートを参加させる。  

16. 送信ポートを右クリックし、をクリックして**開始**送信ポートを開始します。  

17. 受信場所を右クリックし、をクリックして**を有効にする**受信場所を有効にします。  

18. BizTalk Server のエラーがないことを確認するイベント ログを確認します。  

## <a name="see-also"></a>参照  
 [MQSeries アダプターを構成する方法は、送信し、受信ハンドラー](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md)   
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)