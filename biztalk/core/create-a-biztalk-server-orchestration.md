---
title: BizTalk Server オーケストレーションを作成 |Microsoft ドキュメント
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
ms.openlocfilehash: d6223ab8d8aa3c8d1c20559a88257dd0dccaa22e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008990"
---
# <a name="create-a-biztalk-server-orchestration"></a>BizTalk Server のオーケストレーションの作成
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 配置時に JSON 注文書メッセージを受信し、XML 請求書に変換して JSON 請求書を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成します。  
  
## <a name="define-message-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 このソリューションは、注文書と請求書の 2 つの基本メッセージで機能します。 JSON スキーマ ウィザードを使用して、JSON メッセージから注文書のスキーマをすでに生成しました。 このチュートリアルに用意されているサンプルには、すでに請求書メッセージのスキーマが含まれています。 これらのスキーマを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリのメッセージの種類を作成します。  
  
1.  オーケストレーションを BizTalk プロジェクトに追加して、オーケストレーション ビューを開きます。  
  
2.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
3.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`PurchaseOrder`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *BTSJSON です。PO*ここで、 *BTSJSON* BizTalk プロジェクトの名前を指定します。|  
  
5.  前の手順を繰り返して請求書メッセージの新しいメッセージの種類を作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`InvoiceMsg`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *BTSJSON です。請求書*です。|  
  
## <a name="set-up-the-orchestration"></a>オーケストレーションのセットアップ  
 この手順では、メッセージの構築図形とポートを追加してオーケストレーションを作成します。  
  
### <a name="add-message-shapes"></a>メッセージの構築図形の追加  
 ソリューション エクスプローラーからオーケストレーション ファイルを開いて、次のメッセージの構築図形を追加します。  
  
-   受信図形を追加、その名前を設定**ReceivePO**、およびメッセージの種類を**PurchaseOrder**です。  
  
-   送信図形の追加、その名前を設定**SendInvoice**、およびメッセージの種類を**InvoiceMsg**です。  
  
-   メッセージの構築図形を追加し、設定、**構築メッセージ**にメッセージの構築図形のプロパティ**InvoiceMsg**です。  
  
-   メッセージの構築図形に変換図形を追加します。 変換図形をダブルクリックし、、**変換の構成**ダイアログ ボックスで、**既存のマップ**オプションをクリックし  **BTSJSON です。POToInvoice**マップします。 このマップはサンプルに含まれています。 ダイアログ ボックスで、次のように設定します。**ソース**に**PurchaseOrder**設定と**先**に**InvoiceMsg**です。 **[OK]** をクリックします。  
  
### <a name="add-ports"></a>ポートを追加します。  
 オーケストレーションに、メッセージの受信用と送信用の 2 つのポートを追加します。 ポートに以下のプロパティを設定します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*ReceiveJSONPO*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|ResponseOut|-設定**識別子**に*SendJSONInvoice*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
 以下のスクリーンショットのようにポートとメッセージの図形を接続し、プロジェクトへの変更を保存します。  
  
 ![JSON メッセージを処理するオーケストレーション](../core/media/btsjson-orchestration.png "BTSJSON_Orchestration")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)