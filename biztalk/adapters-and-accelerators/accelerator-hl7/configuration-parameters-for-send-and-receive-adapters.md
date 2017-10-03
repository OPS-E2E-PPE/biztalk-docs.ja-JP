---
title: "構成パラメーターを送信および受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters
- send adapters
- configuration parameters [adapters]
- receive adapters
ms.assetid: f24ca8ae-feaf-4e5f-b434-76bc3c1c8ccf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c33e49e82f9ebbf8856dd447989d7557558c0e4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-parameters-for-send-and-receive-adapters"></a>構成パラメーターを送信および受信アダプター
このセクションでは、構成パラメーターを最小限に抑える下位層プロトコル (MLLP) アダプターの送受信を提供します。 これらのパラメーターは 2 つの型に分類されます。 文字をブロックし、ネットワーク接続のパラメーターです。  
  
 ブロックの文字設定で設定 MLLP トランスポートの種類を使用して送信ポートの MLLP トランスポートのプロパティ。  
  
 パラメーターを設定、ネットワーク接続 MLLP トランスポートのプロパティのいずれかの送信ポートまたは受信場所が MLLP のトランスポートの種類を使用できます。 ためには、BizTalk Server 管理コンソールを開き、該当する場合に、送信ポートまたは受信場所のフォルダーに移動、特定の送信ポートを右クリックしてまたは受信場所をクリックして**プロパティ**をクリックして**構成**です。  
  
## <a name="block-characters"></a>文字のブロック  
 これらのパラメーターは、特殊文字を HL7 メッセージ MLLP アダプター経由で送信または受信したを囲む必要があります。 これらの文字は、次の形式で、ブロックを形成: \<SB >*DDD*\<EB >\<CR > ここで、 *DDD*メッセージ データの略\<SB> 開始ブロック文字で\<EB > end ブロックの文字と\<CR > は、復帰、戻り値。  
  
|パラメーター|新しく使用する機能|  
|---------------|---------|  
|**\<CR > キャリッジ リターン**|バイト値 (16 進数形式) をキャリッジ リターン (末尾バイトの後に 2 番目のバイト ラッパー) を使用します。 省略可。|  
|**\<EB > End ブロック文字**|末尾バイト (メッセージ トレーラー ラッパー) を使用するバイト値。 ASCII \<FS > など、 \<1 c >。|  
|**\<SB > 開始ブロック文字**|先頭バイト (メッセージ ヘッダーのラッパー) を使用するバイト値。 ASCII \<VT > など、 \<0b >。|  
  
## <a name="deliverymode"></a>DeliveryMode  
 インスタンス ファイルが順番に、または誤った順序で、順序どおりの順序に配信されるかどうかを制御配信モード パラメーターを使用するとします。 各受信場所がファイルのシーケンス インスタンスの独自の配信します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|順次配送|**MLLP の受信**:<br /><br /> 設定、**順次配送**プロパティを**TRUE**メッセージが特定の順序で処理されることを指定します。 順次配送は、パートナーのビジネス プロセスの指定どおりに、メッセージをコンボイとして処理する必要がある場合に重要です。<br /><br /> 設定した場合、**順次配送**プロパティを**FALSE** (既定値) の場合は、ポートが順次配送を行いません。|  
  
## <a name="network-connection-parameters"></a>ネットワーク接続パラメーター  
 コメント、接続の名前、ホスト名など、ネットワーク経由で接続を確立、ID のポート、受信タイムアウト、およびタイムアウトを送信するには、これらのパラメーターを使用します。  
  
|パラメーター|新しく使用する機能|  
|---------------|---------|  
|**コメント**|接続の説明です。 省略可。|  
|**接続名**|監視対象の接続の名前。 名前が一意であることをお勧めします。 名前は、この接続のパフォーマンス カウンターのインスタンス名に含める。|  
|**ホスト**|**MLLP の受信**:<br /><br /> 省略可。 着信接続をリッスンするローカル インターフェイスを指定します。 によって既定すべてのローカル インターフェイスで受信を待機します。<br /><br /> **MLLP 送信**:<br /><br /> NetBIOS 名または接続する基幹業務 (LOB) コンピューターの IP アドレスを指定します。|  
|**永続的な接続**|**MLLP の受信**:<br /><br /> 設定、**永続的な接続**プロパティを**FALSE** (既定値)、接続がアイドル タイムアウト期間の後に、接続を終了します。 設定、**永続的な接続**プロパティを**True**接続を開いたままにします。<br /><br /> 次の表は、結果の有効な値について、**永続的な接続**と**受信タイムアウト**値。<br /><br /> **FALSE**<br /><br /> - >0<br /><br /> のメッセージが受信されるか、タイムアウト期間が経過した後接続を閉じます。<br /><br /> **FALSE**<br /><br /> - 0<br /><br /> -エラーが発生の原因:"の受信タイムアウトの値は指定できません固定接続 FALSE の場合 0 です"。<br /><br /> **場合は TRUE。**<br /><br /> - 0<br /><br /> ありません-接続が中断されます。<br /><br /> **場合は TRUE。**<br /><br /> - <>0<br /><br /> -エラーが発生の原因:「の受信タイムアウトの値を永続的な接続 TRUE の場合 0 にする必要があります」です。<br /><br /> **MLLP 送信**:<br /><br /> 設定、**永続的な接続**プロパティを**FALSE**、タイムアウト期間内に応答が受信した場合、またはタイムアウト期間が経過した場合、接続を閉じます。 設定、**永続的な接続**プロパティを**True** (既定値)、接続を開いたままにします。<br /><br /> 次の表は、結果の有効な値について、**永続的な接続**と**受信タイムアウト**値。<br /><br /> **FALSE**<br /><br /> -O または > 0<br /><br /> の応答が受信されるか、タイムアウト期間が経過した後接続を閉じます。<br /><br /> **場合は TRUE。**<br /><br /> -0 またはな<br /><br /> ありません-接続が中断されます。 **送信タイムアウト**値に、接続の状態は影響しません。<br /><br /> ときに、型の異なる送信ポートに接続の状態、次の表は永続的な接続の設定の応答を送信請求と変更されます。<br /><br /> 静的な一方向<br /><br /> 場合は TRUE。<br /><br /> -なし<br /><br /> -開いたまま<br /><br /> 静的な一方向<br /><br /> 場合は TRUE。<br /><br /> -[はい]<br /><br /> -開いたまま<br /><br /> 静的な一方向<br /><br /> -FALSE<br /><br /> -なし<br /><br /> 閉じる<br /><br /> 静的な一方向<br /><br /> -FALSE<br /><br /> -[はい]<br /><br /> 閉じる<br /><br /> 送信請求応答の静的<br /><br /> 場合は TRUE。<br /><br /> -なし<br /><br /> -開いたまま<br /><br /> 送信請求応答の静的<br /><br /> 場合は TRUE。<br /><br /> -[はい]<br /><br /> -開いたまま<br /><br /> 送信請求応答の静的<br /><br /> -FALSE<br /><br /> -なし<br /><br /> 閉じる<br /><br /> 送信請求応答の静的<br /><br /> -FALSE<br /><br /> -[はい]<br /><br /> 閉じる|  
|**[ポート]**|**MLLP の受信**:<br /><br /> リッスンするようにローカル ポートの ID です。<br /><br /> **MLLP 送信**:<br /><br /> 接続するリモート ポート ID です。|  
|**送信タイムアウト**|**MLLP 送信**:<br /><br /> 送信アダプタがメッセージの送信中に待機する最大時間するまで、送信ソケットにはタイムアウトがします。有効期限、BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) メッセージを再試行してください。<br /><br /> 同期の操作、送信ポートの LOB から確認 (ACK) を受信するための最大時間が発生した場合も。|  
|**受信タイムアウト**|**MLLP の受信**:<br /><br /> 受信アダプターが受信側のソケットがタイムアウトする、メッセージを受信中に待機する最大時間。有効期限、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接続は切断されます。<br /><br /> また、同期操作、受信場所、LOB に ACK を送信するための最大時間が発生した場合。|  
|**送信請求応答を有効になっています。**|**MLLP 送信**:<br /><br /> はい/いいえ。 同じ TCP 接続の Ack を受信できるようにします。|  
|**送信場所の URI の ACK を受信**|**MLLP 送信**:<br /><br /> Ack が同じ TCP 接続で受信する受信場所の URI は、メッセージ ボックス データベースに配信されます。|  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [MLLP の受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)