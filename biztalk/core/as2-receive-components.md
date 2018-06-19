---
title: AS2 受信コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232554"
---
# <a name="as2-receive-components"></a>AS2 の受信コンポーネント
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、AS2 メッセージの受信にいくつかのコンポーネントが使用されます。  
  
## <a name="as2-receive-pipelines"></a>AS2 受信パイプライン  
 AS2 受信処理の大部分は、次の AS2 受信パイプラインで実行されます。 これらのパイプラインがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。  
  
 **AS2EdiReceive パイプライン**  
  
 このパイプラインは、MDN を含む AS2 経由で受信した EDI メッセージを処理します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
-   AS2 デコーダー  
  
-   EDI 逆アセンブラー  
  
-   BatchMarker です。  
  
    > [!NOTE]
    >  AS2EdiReceive パイプラインを使用する場合、BizTalk Application Users グループに、BizTalk 分離ホスト インスタンス プロセスが実行されているユーザー アカウントを追加する必要があります。 AS2EdiReceive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行されます。 AS2EdiReceive パイプラインは、BizTalk Application Users グループに属しているユーザーのみが使用できる SSO ストアにアクセスします。  
  
 **AS2Receive パイプライン**  
  
 このパイプラインは、メッセージが EDI でエンコードされていない場合に、AS2 経由で受信したメッセージを処理します。 これらのメッセージは、バイナリ メッセージとして扱われます。 このパイプラインは、AS2 経由で受信した MDN も処理します。 パイプラインは、次のパイプライン コンポーネントで構成されます。  
  
-   AS2 デコーダー  
  
-   AS2 逆アセンブラー  
  
## <a name="as2-receive-pipeline-components"></a>AS2 受信パイプライン コンポーネント  
 AS2 受信パイプラインでは、次のパイプライン コンポーネントが使用されます。 これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\です。  
  
> [!NOTE]
>  AS2 受信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされます。  
  
 **AS2 デコーダー**  
  
 AS2 デコーダーは、AS2EDIReceivePipeline 受信パイプラインおよび AS2Receive 受信パイプラインの両方のデコード ステージに含まれています。 このデコーダーは、BizTalk の S/MIME パイプライン コンポーネントを使用して、AS2 メッセージと MDN メッセージに S/MIME デコード機能を付加します。  
  
-   AS2/HTTP ヘッダーを処理します。  
  
-   メッセージが署名付きの場合は署名を検証します。  
  
-   メッセージが暗号化されている場合はメッセージを解読します (MDN ではなく EDI/AS2 メッセージの場合)。  
  
-   メッセージが圧縮されている場合はメッセージを圧縮解除します。  
  
-   受信した MDN を元の送信メッセージと照合して調整します。  
  
-   否認不可データベース内でレコードの更新および関連付けを行います。  
  
-   AS2 状態レポートのレコードを書き込みます。  
  
    > [!NOTE]
    >  AS2 メッセージの受信側の処理中にエラーが発生した場合、AS2 デコーダーはそれ以降のダウンストリーム メッセージ処理を停止します (たとえば、EDI 逆アセンブラーはインターチェンジを解析しません)。 その場合でも、AS2 逆アセンブラーまたは EDI 逆アセンブラーは MDN を生成する必要があります。  
  
    > [!NOTE]
    >  AS2 メッセージでは 8 ビット エンコードが使用されます。 Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。  
  
 **AS2 逆アセンブラー**  
  
 AS2Receive 受信パイプラインでは、AS2 逆アセンブラーは次の処理を実行します。  
  
-   MDN が必要かどうか、MDN が同期または非同期のどちらである必要があるかを決定します。  
  
-   AS2 MDN を生成します。  
  
-   MDN が同期の場合は `EdiIntAS.IsAS2AsynchronousMDN` プロパティを False に設定し、非同期の場合は True に設定します。  
  
-   MDN に関連付けのトークンとプロパティを設定します。  
  
 **EDI 逆アセンブラー**  
  
 AS2EDIReceivePipeline では、EDI 逆アセンブラーは EDI メッセージを処理するために中間 XML メッセージに解析します。 詳細については、次を参照してください。 [「EDI 逆アセンブラーの動作](../core/how-the-edi-disassembler-works.md)です。  
  
 **BatchMarker**  
  
 AS2EDIReceivePipeline では、BatchMarker パイプライン コンポーネントは、バッチ処理されたインターチェンジの処理に必要な AgreementPartIdForSend および ToBeBatched の各コンテキスト プロパティを設定します。 このコンポーネントは、AS2EDIReceive パイプラインの最後のステージ (アグリーメントの解決) に含まれています。 EDI メッセージをバッチ処理するすべてのパイプラインに BatchMarker パイプライン コンポーネントが含まれている必要があります。  
  
> [!NOTE]
>  BatchMarker パイプライン コンポーネントは、EDI 以外のメッセージの処理に使用する AS2Receive パイプラインには含まれていません。 ただし、EDI 逆アセンブラーを含まないカスタム受信パイプラインに BatchMarker コンポーネントを含めることはできます。 詳細についてを参照してください「の処理非 EDI メッセージ BatchMarker コンポーネントで」[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)です。  
  
## <a name="http-adapter"></a>HTTP アダプター  
 AS2 処理に使用される受信ポートと受信場所では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP アダプターが使用されます。 この HTTP アダプターは、一方向の送信と要求 - 応答の送信のいずれかに構成されます。  
  
## <a name="non-repudiation-database"></a>否認不可データベース  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。  
  
> [!NOTE]
>  EdiMessageContent テーブルは、否認不可ストレージ アグリーメントのプロパティの 1 つがチェックされている場合にのみ BizTalkDTADb データベース内に存在します。  
  
-   署名付き MDN の否認不可記録の提供  
  
-   送信メッセージと受信 MDN の関連付け  
  
-   さまざまな状態変更によるメッセージの保存  
  
-   HTTP 応答と MDN の関連付けられたエラー コード  
  
-   フィルター条件に基づくレコードの表示  
  
-   マークされたレコードのアーカイブ  
  
> [!IMPORTANT]
>  否認不可受信データベースに格納されているメッセージの認証と整合性を確保するには、データベースに格納されるすべてのメッセージ (元の AS2 メッセージと MDN の両方) にデジタル署名を使用する必要があります。 詳細については、表示のセクション 9.1 [「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」、RFC 1430](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)