---
title: AS2 送信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 352cde6b72aecaf0baa9c53d1f67b63f3da215c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359003"
---
# <a name="as2-send-components"></a>AS2 送信コンポーネント
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] いくつかのコンポーネントを使用して、AS2 メッセージを送信します。  
  
## <a name="as2-send-pipelines"></a>AS2 送信パイプライン  
 ほとんどの AS2 送信処理は、次の AS2 送信パイプラインで実行されます。 これらのパイプラインがインストールされている`Microsoft.BizTalk.Edi.EdiIntPipelines.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components にします。  
  
> [!NOTE]
>  AS2 送信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされます。  
  
 **AS2EDISend パイプライン**  
  
 このパイプラインは、生成し、AS2 経由で EDI メッセージを送信します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
- EDI アセンブラー  
  
- AS2 エンコーダー  
  
  このパイプラインは、MDN は EDI アセンブラーによって処理される必要がないために生成し、AS2 経由で Mdn を送信するのには使用されません。 AS2SendPipeline を使用すると、Mdn を送信します。  
  
> [!NOTE]
>  オーケストレーションからの AS2EDISend パイプラインの実行はサポートされていません。  
  
 **AS2Send パイプライン**  
  
 このパイプラインは、メッセージが EDI でエンコードされていないときに、AS2 経由でメッセージを送信します。 また、AS2 経由で Mdn を送信します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
- AS2 エンコーダー。  
  
  AS2 経由で送信するメッセージが EDI でも XML メッセージの場合は、これらのメッセージを処理するためにカスタマイズされた AS2Send パイプラインを作成することができます。 このパイプラインには、カスタマイズされたアセンブラーの中間 XML では、BizTalk Server はメッセージを ediint/as2 にエンコードする前に他の形式に変換する必要があります。  
  
> [!NOTE]
>  オーケストレーションからの AS2Send パイプラインを実行することはできません。  
  
## <a name="as2-send-pipeline-components"></a>AS2 送信パイプライン コンポーネント  
 AS2 送信パイプラインは、次のパイプライン コンポーネントを使用します。 これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\します。  
  
 **EDI アセンブラー**  
  
 EDIINT 送信パイプラインでは、EDI アセンブラーは EDI インターチェンジをシリアル化します。  
  
 **AS2 エンコーダー**  
  
 AS2 エンコーダーは、AS2 送信パイプラインのエンコード ステージに含まれます。 S/MIME エンコード AS2 および MDN メッセージに機能を提供するのに、BizTalk の S/MIME パイプライン コンポーネントを使用します。 AS2 エンコーダーは、次を行います。  
  
-   AS2 または HTTP ヘッダーに適用されます。  
  
-   有効になっている場合、送信メッセージに署名  
  
-   (Edi/as2、MDN ではない) を有効になっている場合、送信メッセージを暗号化します。  
  
-   (Edi/as2、MDN ではない) を有効になっている場合、メッセージを圧縮します。  
  
-   ペイロードをワイヤ形式に保存する場合、**送信のデコードされた AS2 メッセージに対して有効な NRR**プロパティが選択されているし、メッセージをワイヤ形式に保存する場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**プロパティが選択されています。  
  
-   MIC 値を計算し、データ ストアに格納されます。  
  
-   更新し、受信の否認不可データベース内のレコードを関連付けています  
  
-   MDN メッセージの場合は、as2receive AS2 デコーダーによって生成された MDN をルーティングするパススルー パイプラインとして機能は受信パイプラインです。 構成設定で必要な場合、AS2 エンコーダーが MDN に署名します。  
  
    > [!NOTE]
    >  AS2 メッセージでは 8 ビット エンコードが使用されます。 Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。  
  
## <a name="http-adapter"></a>HTTP アダプター  
 EDIINT AS2 処理の使用するために使用される送信ポート、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP アダプター。 HTTP アダプターが一方向の両方で構成されていると、送信請求-応答送信します。  
  
## <a name="non-repudiation-database"></a>否認不可データベース  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。  
  
> [!NOTE]
>  EdiMessageContent テーブルは、非否認不可ストレージ アグリーメントのプロパティのいずれかがチェックされている場合にのみ BizTalkDTADb データベースに存在します。  
  
-   署名付き MDN を否認不可記録を提供します。  
  
-   受信 MDN と送信メッセージを関連付け  
  
-   さまざまな状態の変化を経由してメッセージを格納します。  
  
-   エラー コードを HTTP 応答および MDN と関連付ける  
  
-   フィルター条件に基づくレコードの表示  
  
-   マークされたレコードのアーカイブ  
  
> [!IMPORTANT]
>  認証と否認不可データベースに格納されたメッセージの整合性を確保するには、元の AS2 メッセージと Mdn の両方のデータベースに格納されるすべてのメッセージにデジタル署名を使用する必要があります。 詳細については、表示のセクション 9.1 [RFC 1430 の「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)