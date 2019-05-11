---
title: BizTalk Server オーケストレーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c637ae-f94f-40f8-8ce7-73a7b7df9f8f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ae4a8b8f2c70143d1b9969bdcd7537911a99cc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390162"
---
# <a name="create-a-biztalk-server-orchestration"></a>BizTalk Server オーケストレーションを作成します。
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションを展開するときは、JSON 注文書メッセージを受信し、XML 請求書に変換して JSON 請求書を送信します。  
  
## <a name="define-message-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 このソリューションでは、2 つの基本的なメッセージは – 発注書と請求書。 既に JSON スキーマ ウィザードを使用して JSON メッセージから注文書のスキーマを生成しました。 このチュートリアルで既に提供されたサンプルは、請求書メッセージのスキーマを持ちます。 これらのスキーマを使用してメッセージの種類を作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  
  
1.  オーケストレーションを BizTalk プロジェクトに追加し、オーケストレーション ビューを開きます。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`PurchaseOrder`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *BTSJSON します。PO*ここで、 *BTSJSON* BizTalk プロジェクトの名前を指定します。|  
  
5.  請求書メッセージの新しいメッセージの種類を作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`InvoiceMsg`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *BTSJSON します。請求書*します。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションをセットアップします。  
 この手順では、メッセージの構築図形とオーケストレーションを作成するポートを追加します。  
  
### <a name="add-message-shapes"></a>メッセージの構築図形を追加します。  
 ソリューション エクスプ ローラーからオーケストレーション ファイルを開き、次のメッセージの構築図形を追加します。  
  
-   受信図形を追加、その名前を設定**ReceivePO**、およびメッセージの種類を**PurchaseOrder**します。  
  
-   送信図形を追加、その名前を設定**SendInvoice**、およびメッセージの種類を**InvoiceMsg**します。  
  
-   メッセージの構築図形を追加し、設定、**構築メッセージ**プロパティをメッセージの構築図形の**InvoiceMsg**します。  
  
-   メッセージの構築図形内での変換図形を追加します。 変換図形をダブルクリックし、**変換の構成**ダイアログ ボックスで、**既存のマップ**、オプションを選択して**BTSJSON します。POToInvoice**マップします。 このマップは、サンプルの一部として提供されます。 ダイアログ ボックスで、次のように設定します。**ソース**に**PurchaseOrder**設定と**先**に**InvoiceMsg**します。 **[OK]** をクリックします。  
  
### <a name="add-ports"></a>ポートを追加します。  
 – オーケストレーションのメッセージとメッセージを送信するための 1 つの受信用に 2 つのポートを追加します。 ポートに対して、次のプロパティを使用します。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*ReceiveJSONPO*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|ResponseOut|-設定**識別子**に*SendJSONInvoice*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
 、次のスクリーン ショットのように、ポートとメッセージ図形を接続し、プロジェクトに変更を保存します。  
  
 ![JSON メッセージを処理するオーケストレーション](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)