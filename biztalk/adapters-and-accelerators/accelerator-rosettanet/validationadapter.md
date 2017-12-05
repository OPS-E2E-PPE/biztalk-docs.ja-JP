---
title: "ValidationAdapter |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a325a561017c6efaf6d6aefe2e271c834c13a363
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validationadapter"></a>ValidationAdapter
ValidationAdapter のサンプルは、応答側パブリック プロセスでメッセージに対して特殊な検証ルールを実行する方法を示しています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] では、送信または受信パイプライン、およびオーケストレーションで検証がネイティブに実行されます。 追加の検証を実行する場合は、検証アダプターを作成します。 追加の検証には、クロスフィールド検証ルールや、XSD を使用して実装できないビジネス固有の検証ルールを含めることができます。  
  
 追加することで、検証アダプターを作成することができます[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter サンプルでは、インターフェイスを公開して、アダプターをアグリーメントのプロパティに入力するコードです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]メッセージの処理中に、検証アダプターを次呼び出されます。  
  
 ValidationAdapter はパブリック プロセス オーケストレーションで使用されるため、そのオーケストレーションをホストしている BizTalk ホスト サービスと同じ資格情報の下に実行されます。  
  
 ValidationAdapter サンプルにある\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ValidationAdapter です。  
  
## <a name="demonstrates"></a>使用例  
 ValidationAdapter サンプルは、サービス コンテンツでの電子メール アドレスの検証を示します。 このサンプルでは、`IValidateRNIFMessageParts` インターフェイスを実装します。 電子メール アドレスが正しい形式でない場合は `RNIFException` が返されます。 XML ドキュメント**preambleToValidate**、 **serviceHeaderToValidate**、 **deliveryHeaderToValidate**、および**serviceContentToValidate**検証を定義します。  
  
 ValidationAdapter では、RNIFerror.IsOkToSendException プロパティを使用して、エラーが発生した場合に送信するメッセージの種類を決定します。 検証に失敗した場合、ValidationAdapter で RNIFerror.ErrorCode がゼロ以外の値に設定されます。 RNIFerror.IsOkToSendException プロパティが True の場合は、否定受信確認応答が送信されます。 RNIF 2.0 では、これは例外メッセージになります。 RNIF 1.1 では、これは受信確認例外メッセージになります。 RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されている場合は、0A1 メッセージが送信されます。 例外メッセージ、受信確認例外メッセージ、または 0A1 メッセージが送信されると、プロセスは終了します。  
  
 RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されていない場合は、例外も 0A1 も送信されません。 エラーが記録され、プロセスは終了します。  
  
 検証に成功すると、ValidationAdapter で RNIFerror.ErrorCode が 0 に設定され、BTARN によりメッセージがプライベート プロセスにルーティングされます。 メッセージがプライベート プロセスにルーティングされるのは、検証が成功した場合のみです。  
  
## <a name="to-implement-this-sample"></a>サンプルの実装  
 ValidationAdapter サンプルを実装するには、検証アダプタを引数に追加する必要があります。  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>検証アダプタをアグリーメントに追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**です。  
  
2.  [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、クリックして**契約**です。  
  
3.  検証アダプタを追加するアグリーメントをダブルクリックします。  
  
4.  **検証アダプター**  ダイアログ ボックスで、省略記号ボタンをクリックして (**.**) の右側にあるボタン**アセンブリ名**、検証アダプタ アセンブリを格納している場所に移動、適切な .dll ファイルを選択し、をクリックして**開く**です。  
  
5.  下矢印をクリックして**クラス名**、検証アダプタ クラスを選択し、クリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)