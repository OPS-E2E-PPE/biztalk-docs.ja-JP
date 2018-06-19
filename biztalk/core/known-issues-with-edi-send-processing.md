---
title: 既知の問題 edi の送信処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1325dcd9-5dbb-48bb-b5a3-1502d1424d4e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbebfa213aa125252a8c58e246df376e2a36527d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263314"
---
# <a name="known-issues-with-edi-send-processing"></a>EDI の送信処理に関する既知の問題
このトピックでは、EDI 送信パイプラインでの処理に関する既知の問題について説明します。  
  
## <a name="x12-implied-decimal-point-causes-length-validation-to-fail"></a>X12 の暗黙的な小数点が原因で長さの検証に失敗する  
 **現象**  
  
 EDI 送信パイプラインが、中間 XML に含まれる底 10 の数値を、送信する EDI インターチェンジで Nn 形式の数値に変換するときに、XML インターチェンジの長さの検証に失敗します。  
  
 **考えられる原因**  
  
 EDI 送信パイプラインは、X12 でエンコードされた EDI インターチェンジをシリアル化するときに、必ず底 10 の数値を暗黙的な小数点を含む Nn 形式の数値に変換します。 たとえば、中間 XML ファイルに 12.34 という値が含まれている場合、これが数値型 N2 として指定されていると、EDI 送信パイプラインは、EDI インターチェンジでこれを 1234 に変換します。 底 10 の数値の長さは、Nn 形式の数値より 1 だけ長くなります。 Nn 形式の数値の長さが最大である場合、中間 XML 内の底 10 の数値は、XML の長さの検証で失敗します。  
  
 これは、X12 エンコード インターチェンジの問題だけです。  
  
 **解決策**  
  
 XML の数値の最大長を 1 だけ増やします。  
  
## <a name="control-numbers-may-need-to-be-reset-archived-or-purged"></a>制御番号をリセット、アーカイブ、または削除する必要が発生する場合がある  
 制御番号がフィールドの最大長に達すると、BizTalk Server でエラーが発生し、インターチェンジが中断されます。 このため、[EDI のプロパティ] または [EDI グローバル プロパティ] ダイアログ ボックスで制御番号をリセットする必要があります。  
  
 制御番号は、BizTalk MessageBox データベースの dbo.EdiSequenceNumbers テーブルに保存されています。 必要に応じて、このテーブルの制御番号を削除するかアーカイブすることによって、このデータベースを管理する必要があります。  
  
 選択して制御番号の自動リセットを有効にすることもできます**範囲外の時は下限にリセット**EDI のプロパティ ダイアログ ボックスをオンにします。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>データ要素名のピリオドがコンテキスト プロパティ名ではアンダースコアになる  
 EDI セグメント内のデータ要素名には、ピリオドが含まれています (UNB2 送信者セグメントの ID フィールドである UNB2.1 など)。 しかし、データ要素名が EDI コンテキスト プロパティの一部となった場合 (送信ポートのフィルター式など)、ピリオドがアンダースコアに置き換えられます。 たとえば、送信者 ID データ要素を表すコンテキスト プロパティは、EDI.UNB2.1 ではなく EDI.UNB2_1 となります。 この現象は、コンテキスト プロパティ名でピリオドがサポートされていないために発生します。  
  
## <a name="context-property-values-from-data-elements-must-not-contain-leading-or-trailing-spaces-in-filter-expressions"></a>データ要素から取得されたコンテキスト プロパティ値をフィルター式で使用する場合、前後のスペースを削除する必要がある  
 EDI インターチェンジのエンベロープに含まれるデータ要素の前後にスペースが含まれており、受信パイプラインがそのデータ要素の値を使用したコンテキスト プロパティを昇格させる場合、受信パイプラインは、そのコンテキスト プロパティの前後のスペースを削除します。 このため、そのコンテキスト プロパティを使用してフィルター式を作成する場合、前後のスペースのないプロパティ値を入力する必要があります。 フィルター式でプロパティの前後にスペースが含まれていると、コンテキスト プロパティには前後のスペースが含まれていないため、そのフィルター式で正しい結果を得ることができません。  
  
## <a name="default-party-as-interchange-receiver-properties-for-preserved-interchange-will-cause-the-send-pipeline-to-fail"></a>保存されたインターチェンジのインターチェンジ受信者プロパティに既定のパーティが指定されていると、送信パイプラインでエラーが発生する  
 BizTalk Server が、保存する必要のあるバッチ化されたインターチェンジを受信したときに (インターチェンジがエラーにより中断された場合)、インターチェンジの受信パーティを表すプロパティが既定値に設定されていると、そのインターチェンジをサブスクライブする送信パイプラインでエラーが発生します。 これらのプロパティ (送信者修飾子の ISA5 や送信者 ID の ISA6 など) は、有効な値に設定する必要があります。 BizTalk Server では、パーティの構成が無効であるためにメッセージをシリアル化できないことを示すエラーが発生します。 バッチ化されたインターチェンジのヘッダーには、送信者修飾子や送信者 ID などの必須の構成設定が含まれているため、この処理は正しくありません。  
  
## <a name="the-decimal-notation-in-a-message-will-be-changed-if-the-send-side-party-or-global-setting-specifies-a-different-decimal-notation"></a>メッセージで使用されている小数点表記と、送信側パーティまたはグローバル設定で指定されている小数点表記が異なる場合、メッセージの小数点表記が変更される  
 インターチェンジで使用されている小数点表記が、UNA3 パーティ プロパティで送信メッセージに指定されている小数点表記と異なる場合、BizTalk Server は、インターチェンジをシリアル化して送信するときに、インターチェンジのエンベロープで使用されている小数点表記を変更します。 この現象は、UNA3 パーティ プロパティではなく UNA3 グローバル プロパティが使用されている場合にも発生します。 たとえば場合は、受信メッセージで使用される小数点表記は、ピリオド、および、UNA3 パーティ プロパティまたは送信メッセージの 10 進表記法を決定する UNA3 グローバル プロパティは、コンマを指定します、BizTalk Server は変更の小数点表記、コンマを送信メッセージ。  
  
## <a name="edi-send-pipelines-cannot-be-executed-from-within-an-orchestration"></a>EDI 送信パイプラインをオーケストレーションから実行できない  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、通常はオーケストレーションの式図形内から送信パイプラインを実行できます。 しかし、EDISend パイプラインや AS2EdiSend パイプラインは実行できません。 これらのパイプラインは、送信ポート内で実行する必要があります。 EDISend パイプラインや AS2EdiSend パイプラインをオーケストレーションの式図形で実行しようとすると、パイプラインが送信ポートにバインドされず、メッセージが中断されます。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更できない  
 BizTalk EDI アプリケーション内のアイテムは、変更または削除できません。 このアプリケーションを変更すると、EDI 機能や AS2 機能の構成を解除して再構成しても、元のアプリケーションを復元することはできません。  
  
## <a name="using-the-default-row-in-the-functional-group-header-grid-can-result-in-a-message-type-mismatch-between-the-interchange-header-and-the-group-header"></a>機能グループ ヘッダー グリッドの既定の行を使用することにより、インターチェンジ ヘッダーとグループ ヘッダーとの間でメッセージの種類が一致しない場合がある  
 EDIFACT でエンコードされた送信インターチェンジの UNH2.1 の値が、[UNG および UNH セグメントの定義] ページのグリッドの [メッセージの種類 UNH2.1 の場合] の値と一致しない場合、メッセージに入力される UNG1 の値が UNH2.1 の値と一致しないことがあります。  
  
 この不一致は、メッセージにグリッドの既定行の UNH2.1 要素との一致がない場合でも、BizTalk がその既定行の UNG1 の値をメッセージに設定することが原因で発生します。  
  
 X12 でエンコードされた送信インターチェンジの ST1 の値が、[GS および ST セグメントの定義] ページのグリッドの [ST1 の場合] の値と一致しない場合、メッセージに入力される GS1 の値は、ST1 の値に基づいて動的に決定されます。  
  
## <a name="invalid-character-in-data-element"></a>データ要素に無効な文字がある  
 **現象**  
  
 EDI 送信パイプラインを使用して EDI インターチェンジを送信する場合、"データ要素に無効な文字がある" というエラーがアプリケーション イベント ログに記録されることがあります。  
  
 **考えられる原因**  
  
 このエラーは、ペイロード データに含まれる文字が区切り文字としても使用されている場合に発生します。 たとえば、"." 文字をコンポーネントの区切り文字として使用しており、ペイロード データにも "." 文字が含まれている場合があります。  
  
 これは、X12 エンコード インターチェンジの問題だけです。  
  
 **解決策**  
  
 使用して、**ペイロードの区切り記号を置き換えます**での設定、 **ISA セグメントの定義**によってペイロード データの区切り記号の文字が見つかったことを指定する EDI パーティ プロパティのページを置き換える必要があります、インターチェンジを送信するときに、置換文字を指定します。  
  
 たとえばを選択すると**ペイロードの区切り記号を置き換えます**」と入力して、' (& a) #124;' 文字がペイロード データに区切り文字の任意の出現箇所を置き換えますが、' (& a) #124;'、インターチェンジは文字EDI 送信パイプラインを使用して送信されます。  
  
## <a name="see-also"></a>参照  
 [EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)   
 [EDI インターチェンジの送信チュートリアル (X12):](../core/walkthrough-x12-sending-edi-interchanges.md)