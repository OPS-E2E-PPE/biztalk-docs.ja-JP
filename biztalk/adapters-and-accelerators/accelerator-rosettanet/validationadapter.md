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
ms.openlocfilehash: 0e4c6ba197f12de8236faed0f8494251fe858aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299913"
---
# <a name="validationadapter"></a>ValidationAdapter
ValidationAdapter サンプルは、応答側パブリック プロセス内のメッセージに対して特別な検証ルールを実行する方法を示します。 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ送信で検証を実行します。 または、受信パイプライン、オーケストレーション内に存在します。 追加の検証を実行する場合は、検証アダプターを作成できます。 追加の検証には、クロス フィールド検証や、XSD を使用して実装することはできませんビジネス固有の検証規則を含めることができます。  
  
 検証アダプターを作成するには追加することで[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter サンプルで、インターフェイスを公開して、アダプターをアグリーメントのプロパティに入力するコードです。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] メッセージの処理中に、検証アダプターはし呼び出します。  
  
 ValidationAdapter は、パブリック プロセス オーケストレーションで使用されるため、そのオーケストレーションをホストしている BizTalk ホスト サービスと同じ資格情報で実行されます。  
  
 ValidationAdapter サンプルはあります\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ValidationAdapter します。  
  
## <a name="demonstrates"></a>使用例  
 ValidationAdapter サンプルは、service content の電子メール アドレスの検証を示します。 サンプルでは実装、`IValidateRNIFMessageParts`インターフェイス。 返します、`RNIFException`電子メール アドレスが正しい形式でない場合。 XML ドキュメント**preambleToValidate**、 **serviceHeaderToValidate**、 **deliveryHeaderToValidate**、および**serviceContentToValidate**検証を定義します。  
  
 ValidationAdapter では、RNIFerror.IsOkToSendException プロパティを使用して、エラーが発生した場合に送信するメッセージの種類を決定します。 検証が成功しなかった場合、ValidationAdapter によって RNIFerror.ErrorCode が 0 以外の値に設定します。 RNIFerror.IsOkToSendException プロパティが true の場合、プロセスは、否定受信確認応答を送信します。 RNIF 2.0 では、これは、例外メッセージです。 RNIF 1.1 では、これは、受信確認例外メッセージです。 RNIFerror.IsOkToSendException プロパティが false であり、0A1 が構成されている場合、プロセスは 0A1 メッセージを送信します。 例外メッセージ、受信確認例外メッセージ、または 0A1 メッセージを送信すると、プロセスが終了します。  
  
 RNIFerror.IsOkToSendException プロパティが false であり、0A1 が構成されていない場合、プロセスは、例外も 0A1 に送信されます。 エラー ログに記録され、終了します。  
  
 検証が成功すると、ValidationAdapter RNIFerror.ErrorCode を 0 に設定して、BTARN プライベート プロセスにメッセージをルーティングします。 検証が成功した場合にのみ、メッセージをプライベート プロセスにルーティングします。  
  
## <a name="to-implement-this-sample"></a>このサンプルを実装するには  
 ValidationAdapter サンプルを実装するには、契約書に検証アダプターを追加する必要があります。  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a>検証アダプタをアグリーメントに追加するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。  
  
2. [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**契約**します。  
  
3. 検証アダプターを追加するアグリーメントをダブルクリックします。  
  
4. **検証アダプター**  ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) ボタンの右側に**アセンブリ名**、検証アダプタ アセンブリを格納している場所に移動、適切な .dll ファイルを選択およびクリックして**オープン**します。  
  
5. 下矢印をクリックして**クラス名**、検証アダプタ クラスを選択し、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)