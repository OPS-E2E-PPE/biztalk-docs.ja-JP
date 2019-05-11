---
title: EDI の検証、スキーマ、およびメッセージに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706b165067fbbed058c12ff096c91851594d945a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380746"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a>EDI の検証、スキーマ、およびメッセージに関する既知の問題
このトピックでは、既知の検証の問題について説明します。  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a>EDI 検証をになっているメッセージは中断されます。  
 **現象**  
  
 1 組のルールに違反すると、検証は無効しが、メッセージは中断されます (結果は、メッセージがシリアル化されることが必要です)。  
  
 **考えられる原因**  
  
 クロス フィールド/セグメント検証を実行すると、場合でも**EDI の種類**プロパティが選択されて、**検証と確認の生成の設定**のノード、 **EDI プロパティ**ダイアログ ボックス。 検証では、スキーマ注釈でオンにするために発生します。  
  
 **解決方法**  
  
 スキーマの注釈で検証を無効にします。  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a>BizTalk サービスは、スキーマを編集し、再デプロイ後に再起動する必要があります。  
 **現象**  
  
 BizTalk Server は有効なメッセージがスキーマを編集し、再デプロイ後に正常に処理していません。  
  
 **考えられる原因**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 無制限のタイムアウトを持つスキーマをキャッシュします。  
  
 **解決方法**  
  
 編集、スキーマを再デプロイすると、BizTalk Server アプリケーション サービスを再起動します。 また、再展開されたスキーマを使用しているパイプラインをホストするホスト インスタンスを再起動する必要があります。  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a>1 つのパーティのエンコードの種類のメッセージの処理は中止されました  
 **現象**  
  
 エンコードの種類のすべてのメッセージの処理 (たとえば、X12 または EDIFACT)、単一のパーティが中止されました。 別のパーティに同じのパーティのエンコードの種類のメッセージまたはメッセージの処理、影響はありません。  
  
 **考えられる原因**  
  
 インターチェンジ、グループ、またはトランザクション セット制御番号の長さが許容される最大長を超えました。  
  
 X12 メッセージで、コントロールの最大長は 9 桁の数字です。 EDIFACT メッセージの場合は、制御番号の最大長は、14 桁を 3 つのフィールドが。  
  
 **解決方法**  
  
 影響を受けるパーティの EDI のプロパティ ダイアログ ボックスの該当するプロパティ ページで、制御番号をリセットします。 次のプロパティ ページで制御番号を編集できます。  
  
-   X12 インターチェンジ制御番号です。ISA セグメントの定義 ページ (パーティ-インターチェンジの受信者 ノード) で X12 のプロパティ  
  
-   X12 グループまたはトランザクション セット制御番号。GS および ST セグメントの定義 ページ (x12 パーティ-インターチェンジの受信者 ノード プロパティ)  
  
-   EDIFACT インターチェンジ制御番号:UNB セグメントの定義ページの [パーティ-インターチェンジの受信者] ノード EDIFACT プロパティの)  
  
-   EDIFACT グループまたはトランザクション セットの制御番号。[パーティ-インターチェンジの受信者] ノードの EDIFACT のプロパティとして)、[UNG および UNH セグメントの定義] ページ  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a>BizTalk Server が 7 つのデータ要素を含む UNH セグメントのスキーマを使用して検証します。  
 UNH セグメントが 7 つの要素 (うち 3 つは省略可能) ではなく、4 つの要素、EDIFACT の以前のバージョンの UNH セグメントの以降のバージョンであります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 検証のための 7 つの要素に以降のバージョンを使用します。  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a>複数のクロス フィールド検証ルールを生成するエラー メッセージをルールに固有にすることはできません。  
 スキーマには、メッセージ内のデータ要素に対して複数のクロス フィールド検証ルールが含まれています、データ要素エラーが発生した場合は、それぞれの検証規則の個別のエラーが生成されます。 ただし、これらのエラーが、同じエラー コードと説明。エラーは、検証規則を特定できません。  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a>EDI 型の検証が無効になっている場合は、受信し、送信を有効になっている、送信パイプラインはできません、メッセージをシリアル化するには  
 EDI 型の検証、受信側で無効にした場合、受信した EDI メッセージからメッセージが有効かどうか、EDI 受信パイプラインに XML メッセージが生成されます。 送信側の EDI の検証が有効な場合、EDI 送信パイプラインは XML ファイルは、エラーにはが含まれていて、その結果、エラーが発生、有効な EDI ファイルに XML を再処理することはできません。  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a>EDI が昇格させたプロパティはのみ、アプリケーションが BizTalk EDI アプリケーションへの参照を使用できます。  
 **現象**  
  
 EDI 名前空間で昇格させたプロパティを使用しようとしている昇格させたプロパティの一覧で、たとえば、オーケストレーションまたは送信ポートのフィルター条件では表示されません。  
  
 **考えられる原因**  
  
 使用している BizTalk アプリケーションには、BizTalk EDI アプリケーションへの参照はありません。 EDI が昇格させたプロパティのプロパティ スキーマは、BizTalk EDI アプリケーションのリソース フォルダーに含まれている Microsoft.BizTalk.Edi.BaseArtifacts.dll 内です。  
  
 **解決方法**  
  
 作業している BizTalk アプリケーションには、BizTalk EDI アプリケーションへの参照を追加します。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>コンテキスト プロパティ名でデータ要素名にアンダー スコア、ピリオドではありませんが含まれています  
 EDI セグメント内のデータ要素の名前には、たとえば、UNB2.1、UNB2 送信者セグメントの id フィールドである、ピリオドが含まれています。 ただし、データ要素名は、EDI コンテキスト プロパティの一部として含まれていますが、期間は、アンダー スコアに置き換えられます。 たとえば、送信者 Id データ要素のコンテキスト プロパティには、EDI です。UNB2_1、EDI ではありません。UNB2.1 します。 この理由は、コンテキスト プロパティ名でピリオドがサポートされていないことです。  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a>インスタンスの検証エラー メッセージに関連のない文字列が追加されます。  
 インスタンスの検証中にエラーを受信したときに、エラー メッセージに「BEC 2004」という文字列が追加されます。 この文字列を無視することができます。  
  
## <a name="edifact-schema-names-are-case-sensitive"></a>EDIFACT スキーマの名前が区別されます。  
 EDIFACT スキーマのスキーマ名、スキーマの root_reference データ要素で示すように小文字は区別されます。 たとえば、EFACT_D98B_ORDERS と EFACT_d98B_Orders は 2 つの異なるスキーマです。  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a>EDI 型の検証が無効になっている場合でも、無効な EDI メッセージを中断することができます。  
 EDI 型の検証が無効になっている場合でも、EDI 構造検証を実行します。 EDI 型の検証が無効になっている場合でも、基本的な構造検証に失敗したインターチェンジは保留されます。  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a>エンベロープ ヘッダーに区切り文字が使用される場合でも、EDI アセンブラーがバッチ処理されていないインターチェンジをシリアル化されます。  
 インターチェンジ受信者としてのパーティに対して定義されている、ヘッダーおよびトレーラのフィールドを区切るために使用する区切り文字は、インターチェンジ、グループ、またはトランザクション セット ヘッダーやトレーラ フィールドのいずれかの定義では使用されませんする必要があります。 場合は、インターチェンジは送信側 BizTalk Server の EDI アセンブラーまたは受信側パーティの逆アセンブラーで処理に失敗します。 インターチェンジ失敗 EDI アセンブラーで、送信バッチの場合、アセンブラーはヘッダー制御 (サービス) スキーマと照らし合わせたエンベロープを検証します。 インターチェンジがバッチでない場合、EDI アセンブラーがシリアル化できますが、受信側パーティの逆アセンブラーで処理は失敗します。  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a>文字セットの不一致によりインターチェンジの中断が生じる  
 送信インターチェンジに対して使用する文字セットは、インターチェンジに挿入するトランザクション セットを作成するために使用する文字セットと同じになります。 ない場合は、無効な文字があったことを示すエラー メッセージでは、インターチェンジは中断可能性があります。  
  
 例: EDIFACT バッチを作成する場合、UNOA を使用して文字セットしますが、バッチに追加するトランザクション セットには、小文字の文字が含まれて、UNOA は小文字を許可していないために、バッチ処理オーケストレーションがメッセージを中断します。  
  
 別の例として、"Basic"の文字セットでの X12 インターチェンジが X12 のバッチ処理に EDI 送信パイプラインを構成する場合がインターチェンジに小文字のため、X12 文字セットが X12 で選択したインターチェンジのエンベロープの生成 ページのパーティ エンベロープの設定が適用されると、インターチェンジの受信者は、「拡張」または"UTF8/Unicode"に設定されている、バッチのメッセージが中断されます。  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a>スキーマの解決に UNH2.5 を使用して、スキーマの更新プログラムが必要です。  
 受信 EDIFACT インターチェンジのスキーマの解決に UNH2.5 (関連付けの割り当てコード) を使用する場合は、\Program Files\Microsoft BizTalk Server 20xx \schema フォルダーにある関連するドキュメント スキーマを更新する必要があります。 Root_reference、display_reference、および xs:element name の既存の値に UNH2.5 の値を追加する必要があります。 たとえば、UNH2.5 が"EAN008"EFACT_D96A_INVOIC スキーマを使用している場合は、root_reference、display_reference、および xs:element name を"EFACT_D96A_INVOIC_EAN008"を設定するとします。  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a>アップグレードを実行するときに、スキーマの圧縮ファイルを置き換え、  
 Microsoft をアップグレードする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルとそれ以降のビルドに、インストール内の MicrosoftEdiXSDTemplates.exe ファイルが置き換えられます。 引き続き古い圧縮ファイルからスキーマを使用する場合は、不要になったアクセスことは、圧縮ファイルに、アップグレード後に古い圧縮ファイルをバックアップする場合を除き。  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a>グループには、複数の X12 が含まれている場合、トランザクション セットと同じ型のあるすべて必要があります  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 同じグループ内の別のトランザクション セットの混在をサポートしません。 グループに複数のトランザクションが含まれている場合、すべてのトランザクションの同じ ST01 の値がある必要があります。  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a>受信 X12 インターチェンジが非 ASCII 区切り記号が含まれている可能性が、メッセージが中断  
 **現象**  
  
 使用が非 ASCII 区切り記号の値、メッセージが中断されると、アプリケーション イベント ログに書き込まれるエラーの場合インターチェンジ受信 X12 です。  
  
 **考えられる原因**  
  
 この問題は、インターチェンジが utf-8 としてエンコードされていない場合に発生することができます。  
  
 **解決方法**  
  
 非 ASCII 区切り記号を含むインターチェンジが utf-8 としてエンコードされた受信 X12 を確認します。  
  
## <a name="see-also"></a>参照  
 [EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [EDI メッセージング](../core/edi-messaging.md)   
 [EDI メッセージの検証](../core/edi-message-validation.md)   
 [EDI スキーマ](../core/edi-schemas.md)   
 [EDI スキーマの開発](../core/developing-edi-schemas.md)