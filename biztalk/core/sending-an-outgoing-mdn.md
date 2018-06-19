---
title: 送信 MDN を送信する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dce7620-d354-4b76-bcbc-f97dc93c3fc3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d947751e06e0dc9892ab63e109b417047ad91b59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271426"
---
# <a name="sending-an-outgoing-mdn"></a>送信 MDN の送信
送信 MDN は、AS2EDIReceive または AS2Receive 受信パイプラインにより生成され、AS2Send パイプラインにより送信されます。 このトピックでは、MDN の送信方法について説明します。 MDN を生成する方法の詳細については、次を参照してください。[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)です。  
  
> [!NOTE]
>  AS2EDISend 送信パイプラインは、送信 MDN の送信には使用されません。これは、このパイプラインの EDI アセンブラーが、MDN の処理では使用されないためです。  
  
## <a name="agreement-resolution-for-an-mdn"></a>MDN のアグリーメントの解決  
 MDN はセルフ ルーティングです。 MDN には、目的のアグリーメントまでルーティングされるのに必要な情報が含まれます。 送信パイプラインは、AS2 アグリーメント プロパティを使用して送信 MDN を処理します。 ただし、MDN では、パーティにルーティングされるためにアグリーメントを解決する必要がありません。  
  
 AS2Send パイプラインは、送信 MDN を処理するとき、メッセージ コンテキストの AS2-To 値を使用してアグリーメント プロパティを取得し MDN を処理します。 これは、AS2 の一致によって-、AS2 でのコンテキスト プロパティに-でアグリーメントのプロパティに、**識別子** ページでは、一方向の AS2 アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 AS2-To 値がアグリーメントに対して設定されていない場合、MDN のこのアグリーメントの解決は失敗する場合があります。 アグリーメントを特定できない場合は、MDN を生成するために既定のアグリーメントが使用されます。  
  
 送出 MDN の既定のアグリーメントでは、証明書解決の一覧の検証が実行されます。 この検証を実行する必要がない場合は、受信側パーティを解決できるようにするため、およびアグリーメントのプロパティを特定できるようにするために、正しい AS2-To アグリーメント プロパティが設定されていることを確認します。 これにより、証明書解決の一覧の検証を要求する既定のアグリーメントが使用されなくなります。 無効にする必要があります、**証明書失効リストのチェック**プロパティを**検証**一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックス。  
  
## <a name="synchronous-and-asynchronous-transmission"></a>同期送信と非同期送信  
 既定の AS2 処理では、MDN は同期送信されます。 MDN が送信される双方向に関連付けられているポートの受信ポートで送信します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP POST に対する HTTP 応答として、または同じ TCP/IP 接続で HTTPS POST に対する HTTPS 応答として MDN を送信します。 MDN は、HTTP 応答コマンドのメッセージのボディ部に組み込まれます。  
  
 MDN を非同期に送信する場合、メッセージ ボックスから MDN を取得する個別の送信ポートから MDN を送信する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]個別の元の AS2 メッセージを配信するために使用される一意な TCP/IP 接続で配信される HTTP Post として MDN を送信します。 MDN が個別の HTTP Post として設定されていても、Post では HTTP 応答コマンドが必要です。  
  
 非同期 MDN は、通常、元の AS2 メッセージの Receipt-Delivery-Option ヘッダーの URL に送信されます。 ただし場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティが設定されて、上、**検証**一方向の AS2 アグリーメント タブのページ、**アグリーメントプロパティ**、MDN は送信 URL にダイアログ ボックスを **- Receipt-delivery-option (URL)** アグリーメント プロパティに設定します。  
  
## <a name="how-the-send-pipeline-processes-an-outgoing-mdn"></a>送信パイプラインによる送信 MDN の処理方法  
 AS2Send パイプラインは、送信 MDN を次のように処理します。  
  
-   デジタル署名の適用を含む MIME 処理を実行します (AS2 の一方向のアグリーメント プロパティで有効になっている場合)。  
  
-   否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) に関連付けのエントリを作成します。  
  
-   MDN のコピー (ワイヤ形式) を作成しで有効になっている場合は、否認不可データベースに格納、**送信 MDN の NRR の有効化**アグリーメントのプロパティです。  
  
-   MDN を HTTP アダプターに配信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 送信コンポーネント](../core/as2-send-components.md)