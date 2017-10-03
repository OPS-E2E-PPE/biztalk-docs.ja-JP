---
title: "EDI 検証、スキーマ、およびメッセージに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a508834ff81814b17bc12f1d698984d65748092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a>EDI 検証、スキーマ、およびメッセージに関する既知の問題
このトピックでは、検証に関する既知の問題について説明します。  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a>EDI 検証の無効化によってメッセージが中断される  
 **現象**  
  
 1 組のルールに違反し、検証は無効であるにもかかわらず、メッセージが (シリアル化される代わりに) 中断されます。  
  
 **考えられる原因**  
  
 クロス フィールド/セグメント検証を実行すると、場合でも**EDI の種類**プロパティが選択されて、**検証と確認の生成の設定**のノード、 **EDI プロパティ**ダイアログ ボックス。 検証は、スキーマの注釈で有効になっているために発生します。  
  
 **解決策**  
  
 スキーマの注釈で検証を無効にします。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a>スキーマを編集し、再展開した後で BizTalk サービスを再起動する必要がある  
 **現象**  
  
 スキーマを編集し、再展開した後に BizTalk Server が有効なメッセージを正常に処理しません。  
  
 **考えられる原因**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、無限のタイムアウトが設定されたスキーマをキャッシュしています。  
  
 **解決策**  
  
 スキーマを編集し、再展開した後で、BizTalk Server アプリケーション サービスを再起動します。 また、再展開されたスキーマを使用するパイプラインをホストするホスト インスタンスを再起動する必要もあります。  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a>1 つのパーティのエンコードの種類が同じであるメッセージの処理が中断される  
 **現象**  
  
 1 つのパーティのエンコードの種類 (X12、EDIFACT など) が同じであるすべてのメッセージの処理が中断されます。 このパーティのエンコードの種類が異なるメッセージ、または別のパーティのメッセージは処理されます。  
  
 **考えられる原因**  
  
 インターチェンジ、グループ、またはトランザクション セットの制御番号の長さが許容されている最大の長さを超えています。  
  
 X12 メッセージの場合、制御番号の最大文字数は 9 桁です。 EDIFACT メッセージの場合、制御番号の最大文字数は、3 つのフィールドを合わせて 14 桁です。  
  
 **解決策**  
  
 影響を受けるパーティの [EDI のプロパティ] ダイアログ ボックスの該当するプロパティ ページで、制御番号をリセットしてください。 制御番号は、次のプロパティ ページで編集できます。  
  
-   X12 インターチェンジ制御番号 : X12 プロパティの [パーティ - インターチェンジの受信者] ノードにある [ISA セグメントの定義] ページ  
  
-   X12 グループまたはトランザクション セット制御番号 : X12 プロパティの [パーティ - インターチェンジの受信者] ノードにある [GS および ST セグメントの定義] ページ  
  
-   EDIFACT インターチェンジ制御番号 : EDIFACT プロパティの [パーティ - インターチェンジの受信者] ノードにある [UNB セグメントの定義] ページ  
  
-   EDIFACT グループまたはトランザクション セット制御番号 : EDIFACT プロパティの [パーティ - インターチェンジの受信者] ノードにある [UNG および UNH セグメントの定義] ページ  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a>BizTalk Server が 7 つのデータ要素を含む UNH セグメントを持つスキーマを使用して検証を行う  
 EDIFACT の以前のバージョンの UNH セグメントには 4 つの要素が含まれていましたが、新しいバージョンの UNH セグメントには 7 つの要素 (うち 3 つはオプション) が含まれています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、7 つのデータ要素を含む新しいバージョンを検証に使用します。  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a>複数のクロスフィールド検証に対して生成されたエラー メッセージが、ルールに固有のものではない  
 メッセージのデータ要素に対する複数のクロスフィールド検証ルールがスキーマに含まれている場合、データ要素にエラーが発生すると、検証ルールごとに別々のエラーが生成されます。 ただし、これらのエラーには同じエラー コードと説明が表示されます (エラーが検証ルールに固有のものではありません)。  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a>EDI 型の検証が受信時は無効、送信時は有効の場合、送信パイプラインはメッセージをシリアル化できない  
 EDI 型の検証を受信側で無効にした場合、EDI 受信パイプラインは、メッセージが有効であるか無効であるかにかかわらず、受信した EDI メッセージから XML メッセージを生成します。 EDI 型の検証を送信側で有効にした場合、XML ファイルにエラーが含まれていると、EDI 送信パイプラインは XML を有効な EDI ファイルに再処理することができないため、エラーが生成されます。  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a>EDI が昇格させたプロパティは、アプリケーションが BizTalk EDI アプリケーションを参照する場合にのみ使用可能である  
 **現象**  
  
 EDI 名前空間で昇格させたプロパティが、オーケストレーションや送信ポートのフィルター条件などで使用する予定の昇格させたプロパティの一覧に表示されません。  
  
 **考えられる原因**  
  
 使用している BizTalk アプリケーションが BizTalk EDI アプリケーションを参照していません。 EDI が昇格させたプロパティのプロパティ スキーマは、BizTalk EDI アプリケーションのリソース フォルダーに格納されている Microsoft.BizTalk.Edi.BaseArtifacts.dll 内にあります。  
  
 **解決策**  
  
 操作している BizTalk アプリケーションに、BizTalk EDI アプリケーションへの参照を追加します。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>データ要素名のピリオドがコンテキスト プロパティ名ではアンダースコアになる  
 EDI セグメント内のデータ要素名には、ピリオドが含まれています (UNB2 送信者セグメントの ID フィールドである UNB2.1 など)。 しかし、データ要素名が EDI コンテキスト プロパティの一部となった場合、ピリオドがアンダースコアに置き換えられます。 たとえば、送信者 ID データ要素を表すコンテキスト プロパティは、EDI.UNB2.1 ではなく EDI.UNB2_1 となります。 この現象は、コンテキスト プロパティ名でピリオドがサポートされていないために発生します。  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a>インスタンスの検証エラー メッセージに関連のない文字列が追加される  
 インスタンスの検証中にエラーが表示された場合、エラー メッセージに "BEC 2004" という文字列が追加されます。 この文字列は無視してかまいません。  
  
## <a name="edifact-schema-names-are-case-sensitive"></a>EDIFACT スキーマ名で大文字と小文字が区別される  
 EDIFACT スキーマのスキーマ名では、スキーマの root_reference データ要素に示されるように、大文字と小文字が区別されます。 たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a>EDI 型の検証が無効の場合でも、無効な EDI メッセージを中断できる  
 EDI 型の検証が無効の場合でも、EDI 構造検証は実行されます。 EDI の種類の検証が無効であっても、基本的な構造の検証でエラーとなったインターチェンジは中断されます。  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a>エンベロープ ヘッダーに区切り文字が使用されている場合でも、EDI アセンブラーはバッチ化されていないインターチェンジをシリアル化する  
 ヘッダー フィールドとトレーラー フィールドを分離するために使用する区切り文字は、インターチェンジ受信者としてのパーティ用に定義されているとおり、インターチェンジ、グループ、またはトランザクション セットのヘッダーまたはトレーラー フィールドの定義で使用することはできません。 これらを定義で使用すると、インターチェンジは、送信側 BizTalk Server の EDI アセンブラーまたは受信側パーティの逆アセンブラーのどちらかの処理に失敗します。 アセンブラーはヘッダー制御 (サービス) スキーマに対してエンベロープを検証するので、送信バッチの場合、インターチェンジは EDI アセンブラーの処理に失敗します。 バッチ化されていないインターチェンジは、EDI アセンブラーではシリアル化されますが、受信側パーティの逆アセンブラーでは処理に失敗します。  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a>文字セットの不一致によりインターチェンジの中断が発生する  
 送信インターチェンジに使用される文字セットは、インターチェンジに挿入されるトランザクション セットの作成に使用される文字セットと同じである必要があります。 同じでなければ、無効な文字が存在することを示すエラー メッセージが表示され、インターチェンジが中断される場合があります。  
  
 たとえば、UNOA 文字セットを使用して EDIFACT バッチを作成するときに、バッチに追加するトランザクション セットに小文字を使用すると、UNOA は小文字を許可しないためバッチ処理オーケストレーションはメッセージを中断します。  
  
 また、"基本" 文字セットを使用して X12 インターチェンジの EDI 送信パイプラインを構成するときに、インターチェンジ受信者としてのパーティの [X12 インターチェンジのエンベロープの生成] ページで選択される X12 文字セットは "拡張" または "UTF8/Unicode" であるため、バッチ化された X12 インターチェンジに小文字を使用すると、エンベロープの設定が適用されるときに、バッチ化されたメッセージは中断されます。  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a>スキーマの解決に UNH2.5 を使用する場合、スキーマの更新が要求される  
 受信 EDIFACT インターチェンジのスキーマの解決に UNH2.5 (関連付けの割り当てコード) を使用する場合は、\Program Files\Microsoft BizTalk Server 20xx\Schema フォルダーにある、関連するドキュメント スキーマを更新する必要があります。 root_reference、display_reference、および xs:element name の既存の値に、UNH2.5 の値を追加する必要があります。 たとえば、UNH2.5 が "EAN008" で、EFACT_D96A_INVOIC スキーマを使用している場合、root_reference、display_reference、および xs:element name を "EFACT_D96A_INVOIC_EAN008" に設定します。  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a>アップグレードを実行すると、スキーマの圧縮ファイルが置き換えられる  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を新しいビルドにアップグレードすると、環境内の MicrosoftEdiXSDTemplates.exe ファイルが、アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。 古い圧縮ファイルのスキーマを引き続き使用する場合は、古い圧縮ファイルをバックアップしない限り、アップグレード後、圧縮ファイルにアクセスできなくなります。  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a>1 つのグループに複数の X12 トランザクション セットが含まれる場合、すべてが同じ種類でなければならない  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、同じグループ内での異なるトランザクション セットの混合はサポートされていません。 1 つのグループに複数のトランザクションが含まれる場合、すべてのトランザクションで ST01 の値が同じである必要があります。  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a>ASCII 以外の区切り文字を含む X12 インターチェンジを受信すると、メッセージが中断する場合がある  
 **現象**  
  
 ASCII 以外の区切り文字の値を使用する X12 インターチェンジを受信すると、メッセージが中断状態になり、アプリケーション イベント ログにエラーが書き込まれる場合があります。  
  
 **考えられる原因**  
  
 この問題は、インターチェンジが UTF-8 としてエンコードされていない場合に発生する可能性があります。  
  
 **解決策**  
  
 ASCII 以外の区切り文字を含む受信 X12 インターチェンジが UTF-8 としてエンコードされていることを確認します。  
  
## <a name="see-also"></a>参照  
 [EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [EDI メッセージング](../core/edi-messaging.md)   
 [EDI メッセージの検証](../core/edi-message-validation.md)   
 [EDI スキーマ](../core/edi-schemas.md)   
 [EDI スキーマの開発](../core/developing-edi-schemas.md)