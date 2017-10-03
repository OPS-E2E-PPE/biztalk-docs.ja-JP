---
title: "AS2 送信コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1dbee64dc2e3484e85e6d8e41ce31a77713ffec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="as2-send-components"></a>AS2 送信コンポーネント
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、いくつかのコンポーネントを使用して AS2 メッセージを送信します。  
  
## <a name="as2-send-pipelines"></a>AS2 送信パイプライン  
 AS2 送信処理の大部分は、次の AS2 送信パイプラインで実行されます。 これらのパイプラインは、\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components の `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` にインストールされています。  
  
> [!NOTE]
>  AS2 送信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされています。  
  
 **AS2EDISend パイプライン**  
  
 このパイプラインでは、EDI メッセージを生成し、AS2 経由で送信します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
-   EDI アセンブラー  
  
-   AS2 エンコーダー  
  
 このパイプラインは、MDN を生成して AS2 経由で送信するためには使用されません。これは、MDN を EDI アセンブラーで処理する必要がないためです。 MDN の送信には AS2SendPipeline を使用します。  
  
> [!NOTE]
>  オーケストレーションからの AS2EDISend パイプラインの実行はサポートされていません。  
  
 **AS2Send パイプライン**  
  
 このパイプラインでは、メッセージが EDI でエンコードされていない場合に、AS2 経由でメッセージを送信します。 また、AS2 経由で MDN を送信します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
-   AS2 エンコーダー。  
  
 AS2 経由で送信するメッセージが EDI メッセージでも XML メッセージでもない場合は、それらのメッセージを処理するために、カスタマイズされた AS2Send パイプラインを作成できます。 このパイプラインには、メッセージを EDIINT/AS2 にエンコードする前に BizTalk Server の中間 XML を他の形式に変換する、カスタマイズされたアセンブラーが必要です。  
  
> [!NOTE]
>  オーケストレーションからの AS2Send パイプラインの実行はサポートされていません。  
  
## <a name="as2-send-pipeline-components"></a>AS2 送信パイプラインのコンポーネント  
 AS2 送信パイプラインでは、次のパイプライン コンポーネントが使用されます。 これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。  
  
 **EDI アセンブラー**  
  
 EDIINT 送信パイプラインでは、EDI アセンブラーによって EDI インターチェンジがシリアル化されます。  
  
 **AS2 エンコーダー**  
  
 AS2 エンコーダーは、AS2 送信パイプラインのエンコード ステージに含まれています。 これは、BizTalk の S/MIME パイプライン コンポーネントを使用して、AS2 メッセージと MDN メッセージに S/MIME エンコード機能を付加します。 AS2 エンコーダーは次の処理を実行します。  
  
-   AS2/HTTP ヘッダーを適用します。  
  
-   送信メッセージに署名します (有効になっている場合)。  
  
-   送信メッセージを暗号化します (有効になっている場合。EDI/AS2 のみで MDN は対象外)。  
  
-   メッセージを圧縮します (有効になっている場合。EDI/AS2 のみで MDN は対象外)。  
  
-   ペイロードをワイヤ形式に保存する場合、**送信のデコードされた AS2 メッセージに対して有効な NRR**プロパティが選択され、メッセージをワイヤ形式に保存する場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**プロパティが選択されています。  
  
-   MIC 値を計算し、データ ストアに保存します。  
  
-   受信の否認不可データベース内でレコードの更新および関連付けを行います。  
  
-   AS2Receive 受信パイプラインの AS2 デコーダーによって生成された MDN をルーティングするパススルー パイプラインとして機能します (MDN メッセージの場合)。 構成設定で要求されている場合、AS2 エンコーダーが MDN に署名します。  
  
    > [!NOTE]
    >  AS2 メッセージでは 8 ビット エンコードが使用されます。 Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。  
  
## <a name="http-adapter"></a>HTTP アダプター  
 EDIINT AS2 処理に使用される送信ポートは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP アダプターを使用します。 この HTTP アダプターは、一方向の送信と送信請求 - 応答送信の両方で構成されます。  
  
## <a name="non-repudiation-database"></a>否認不可データベース  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。  
  
> [!NOTE]
>  EdiMessageContent テーブルは、否認不可ストレージ アグリーメントのプロパティの 1 つがチェックされる場合にのみ BizTalkDTADb データベース内に存在します。  
  
-   署名付き MDN を否認不可記録を提供します。  
  
-   受信 MDN と送信メッセージを関連付ける  
  
-   さまざまな状態の変更を経由してメッセージを保存します。  
  
-   エラー コードの HTTP 応答および NDN への関連付け  
  
-   フィルター条件に基づいてレコードを表示します。  
  
-   マークされたレコードをアーカイブします。  
  
> [!IMPORTANT]
>  否認不可データベースに格納されているメッセージの認証と整合性を確保するには、データベースに格納されるすべてのメッセージ (元の AS2 メッセージと MDN の両方) にデジタル署名を使用する必要があります。 詳細については、表示のセクション 9.1 [「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」、RFC 1430](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)