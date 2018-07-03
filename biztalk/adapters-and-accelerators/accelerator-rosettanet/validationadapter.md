---
title: ValidationAdapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbcf26ee8a3a97d2df34bb29dad5d0cf31d4db1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987907"
---
# <a name="validationadapter"></a>ValidationAdapter
ValidationAdapter のサンプルは、応答側パブリック プロセスでメッセージに対して特殊な検証ルールを実行する方法を示しています。 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ送信で検証を実行します。 または、受信パイプライン、オーケストレーション内に存在します。 追加の検証を実行する場合は、検証アダプターを作成します。 追加の検証には、クロスフィールド検証ルールや、XSD を使用して実装できないビジネス固有の検証ルールを含めることができます。  
  
 検証アダプターを作成するには追加することで[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter サンプルで、インターフェイスを公開して、アダプターをアグリーメントのプロパティに入力するコードです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] メッセージの処理中に、検証アダプターはし呼び出します。  
  
 ValidationAdapter はパブリック プロセス オーケストレーションで使用されるため、そのオーケストレーションをホストしている BizTalk ホスト サービスと同じ資格情報の下に実行されます。  
  
 ValidationAdapter サンプルはあります\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ValidationAdapter します。  
  
## <a name="demonstrates"></a>使用例  
 ValidationAdapter サンプルは、サービス コンテンツでの電子メール アドレスの検証を示します。 このサンプルでは、`IValidateRNIFMessageParts` インターフェイスを実装します。 電子メール アドレスが正しい形式でない場合は `RNIFException` が返されます。 XML ドキュメント**preambleToValidate**、 **serviceHeaderToValidate**、 **deliveryHeaderToValidate**、および**serviceContentToValidate**検証を定義します。  
  
 ValidationAdapter では、RNIFerror.IsOkToSendException プロパティを使用して、エラーが発生した場合に送信するメッセージの種類を決定します。 検証に失敗した場合、ValidationAdapter で RNIFerror.ErrorCode がゼロ以外の値に設定されます。 RNIFerror.IsOkToSendException プロパティが True の場合は、否定受信確認応答が送信されます。 RNIF 2.0 では、これは例外メッセージになります。 RNIF 1.1 では、これは受信確認例外メッセージになります。 RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されている場合は、0A1 メッセージが送信されます。 例外メッセージ、受信確認例外メッセージ、または 0A1 メッセージが送信されると、プロセスは終了します。  
  
 RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されていない場合は、例外も 0A1 も送信されません。 エラーが記録され、プロセスは終了します。  
  
 検証に成功すると、ValidationAdapter で RNIFerror.ErrorCode が 0 に設定され、BTARN によりメッセージがプライベート プロセスにルーティングされます。 メッセージがプライベート プロセスにルーティングされるのは、検証が成功した場合のみです。  
  
## <a name="to-implement-this-sample"></a>サンプルの実装  
 ValidationAdapter サンプルを実装するには、検証アダプタを引数に追加する必要があります。  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>検証アダプタをアグリーメントに追加するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。  
  
2. [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**契約**します。  
  
3. 検証アダプタを追加するアグリーメントをダブルクリックします。  
  
4. **検証アダプター**  ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) ボタンの右側に**アセンブリ名**、検証アダプタ アセンブリを格納している場所に移動、適切な .dll ファイルを選択およびクリックして**オープン**します。  
  
5. 下矢印をクリックして**クラス名**、検証アダプタ クラスを選択し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)