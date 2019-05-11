---
title: 既知の問題では、EDI 送信処理 |Microsoft Docs
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
ms.openlocfilehash: 201b93c854411e0aec79258caa5777c8be51d352
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329140"
---
# <a name="known-issues-with-edi-send-processing"></a>送信処理中の EDI に関する既知の問題
このトピックでは、EDI 送信パイプラインでの処理に関する既知の問題について説明します。  
  
## <a name="x12-implied-decimal-point-causes-length-validation-to-fail"></a>X12 の暗黙的な小数点 10 進数と長さの検証に失敗します。  
 **現象**  
  
 EDI 送信パイプラインに変換します底 10 の数値の中間 XML で、送信 EDI インターチェンジで Nn 形式の数値を XML インターチェンジの長さの検証が失敗します。  
  
 **考えられる原因**  
  
 X12 でエンコードされた EDI インターチェンジをシリアル化、EDI 送信パイプラインは暗黙の小数点の付いた Nn 形式の番号を底 10 の数値を常に変換します。 たとえば、12.34 の中間 XML ファイルに値がある場合、EDI 送信パイプライン変換されます 1234 の数値型 N2 として指定されている場合に、EDI インターチェンジでします。 底 10 の数値の長さは Nn 形式の番号の長さより大きい値のいずれかになります。 形式 Nn で番号の長さが最大値の場合は、中間 XML で底 10 の数値が XML の長さの検証に失敗します。  
  
 これは、X12 エンコード インターチェンジの問題のみです。  
  
 **解決方法**  
  
 XML の数値の最大長の値に値 1 を追加します。  
  
## <a name="control-numbers-may-need-to-be-reset-archived-or-purged"></a>制御番号がリセット、アーカイブ、または削除する必要があります。  
 制御番号には、フィールドの最大長に達すると、BizTalk Server は、エラーが発生し、インターチェンジを中断します。 EDI のプロパティまたは [EDI グローバル プロパティ] ダイアログ ボックスに入力された制御番号をリセットする必要があります。  
  
 制御番号は、BizTalk MessageBox データベースの dbo.EdiSequenceNumbers テーブルに保存されています。 必要に応じて、このテーブルの制御番号を削除するかアーカイブすることによって、このデータベースを管理する必要があります。  
  
 選択して制御番号の自動リセットを有効にすることもできます**範囲外の時は下限にリセット**EDI のプロパティ ダイアログ ボックス。  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a>コンテキスト プロパティ名でデータ要素名にアンダー スコア、ピリオドではありませんが含まれています  
 EDI セグメント内のデータ要素の名前には、たとえば、UNB2.1、UNB2 送信者セグメントの id フィールドである、ピリオドが含まれています。 ただし、データ要素名は、(たとえば、送信ポートのフィルター式) での EDI コンテキスト プロパティの一部として含まれていますが、期間は、アンダー スコアに置き換えられます。 たとえば、送信者 Id データ要素のコンテキスト プロパティには、EDI です。UNB2_1、EDI ではありません。UNB2.1 します。 この理由は、コンテキスト プロパティ名でピリオドがサポートされていないことです。  
  
## <a name="context-property-values-from-data-elements-must-not-contain-leading-or-trailing-spaces-in-filter-expressions"></a>データ要素からコンテキスト プロパティの値はフィルター式の先頭または末尾のスペースを含めることはできません。  
 受信パイプラインがコンテキストから、先頭または末尾にスペースを削除する場合は、EDI インターチェンジのエンベロープ内のデータ要素には、先頭または末尾のスペースが含まれています。 受信パイプラインは、そのデータ要素の値を持つコンテキスト プロパティを昇格、プロパティ。 その結果、そのコンテキスト プロパティをフィルター式を作成する場合、先頭または末尾のスペースを含まないプロパティの値を入力する必要があります。 フィルター式が先頭または末尾のスペースを含める場合、フィルター式が先頭または末尾のスペースを含めることができませんが、コンテキスト プロパティとの一致では解決できません。  
  
## <a name="default-party-as-interchange-receiver-properties-for-preserved-interchange-will-cause-the-send-pipeline-to-fail"></a>インターチェンジが原因の保存されたインターチェンジの受信者のプロパティが失敗する送信パイプラインに既定のパーティ  
 インターチェンジの受信者としてのパーティのプロパティは、既定値に設定されている場合、インターチェンジをサブスクライブする送信パイプラインが失敗する BizTalk Server では、(エラーで中断されたインターチェンジ) を保持する必要があるバッチ インターチェンジを受信する場合値。 送信者の修飾子の ISA5、ISA6、送信者の識別子など、これらのプロパティは、有効な値に設定する必要があります。 BizTalk Server では、メッセージが無効な関係者は、の構成によりシリアル化されませんでしたを示すエラーを送信します。 保存されたインターチェンジはそのヘッダーで送信者の修飾子と送信者の識別子など、必要な構成設定を持つために、この処理が正しくないです。  
  
## <a name="the-decimal-notation-in-a-message-will-be-changed-if-the-send-side-party-or-global-setting-specifies-a-different-decimal-notation"></a>送信側パーティまたはグローバル設定を別の 10 進表記法を指定する場合、メッセージ内の 10 進表記が変わります。  
 BizTalk Server がインターチェンジのエンベロープでシリアル化して送信するときに使用する小数点表記を変更するインターチェンジで使用される小数点表記が、UNA3 パーティ プロパティで、送信メッセージの指定された小数点表記と異なる場合は、. UNA3 グローバル プロパティが、UNA3 パーティ プロパティの代わりに使用される場合、ケースもになります。 たとえば場合は、受信メッセージで使用される小数点表記は、ピリオド、UNA3 パーティ プロパティまたは送信メッセージの 10 進表記法を決定する UNA3 グローバル プロパティは、コンマを指定します、BizTalk Server は変更の小数点表記、コンマを送信メッセージ。  
  
## <a name="edi-send-pipelines-cannot-be-executed-from-within-an-orchestration"></a>EDI 送信パイプラインは、オーケストレーション内から実行することはできません。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、通常、オーケストレーションの式図形内から送信パイプラインを実行できます。 ただし、EDISend パイプラインや AS2EdiSend パイプラインでこれは使えません。 これらのパイプラインは、送信ポート内で実行する必要があります。 オーケストレーションの式図形で、EDISend パイプラインや AS2EdiSend パイプラインを実行しようとすると、パイプラインは、送信ポートにバインドできませんし、メッセージは中断されます。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更する必要がありません。  
 BizTalk EDI アプリケーションのアイテムを変更または削除する必要があります。 このアプリケーションが変更された場合は、構成を解除し、EDI および AS2 機能を再構成して、元のアプリケーションを復元する方法はありません。  
  
## <a name="using-the-default-row-in-the-functional-group-header-grid-can-result-in-a-message-type-mismatch-between-the-interchange-header-and-the-group-header"></a>機能グループ ヘッダーのグリッドで、既定の行を使用して、メッセージの種類の不一致の間で、インターチェンジ ヘッダーとグループ ヘッダーで結果ことができます。  
 EDIFACT でエンコードされた送信インターチェンジの UNH2.1 の値で、[UNG および UNH セグメントの定義] ページのグリッドで「のメッセージの種類 UNH2.1」の値が一致しない場合、メッセージに入力される UNG1 の値が UNH2.1 の値に対応していません。  
  
 これは、BizTalk メッセージに設定されます値を使用して、グリッドの既定の行の UNG1 のメッセージがその既定行の UNH2.1 要素との一致を持っていない場合でもために発生します。  
  
 X12 でエンコードされた送信インターチェンジの ST1 の値が GS および ST セグメントの定義 ページで、グリッド内の ST1 の値が一致しない場合、メッセージに入力される GS1 の値が動的に決定 ST1 の値に基づきます。  
  
## <a name="invalid-character-in-data-element"></a>データ要素に無効な文字  
 **現象**  
  
 EDI 送信パイプラインを使用して EDI インターチェンジを送信する場合は、'データ要素に無効な文字' があることを示すアプリケーション イベント ログでエラーがあります。  
  
 **考えられる原因**  
  
 このエラーは、ペイロード データに含まれる文字が区切り記号としても使用されている場合に発生することができます。 たとえば、使用する場合、':'、コンポーネント区切り記号がペイロード データの文字も含まれています、':' 文字。  
  
 これは、X12 エンコード インターチェンジの問題のみです。  
  
 **解決方法**  
  
 使用して、**を使用してペイロードの区切り記号を置き換えます**での設定、 **ISA セグメントの定義**によってペイロード データ内の区切り文字で見つかったことを指定する EDI パーティのプロパティ ページを置き換える必要があります、インターチェンジを送信するときに、置換文字を指定します。  
  
 などを選択すると**を使用してペイロードの区切り記号を置き換えます**を入力して、'&#124;'文字がペイロード データを区切り文字の出現を置き換えますが、'&#124;' 文字をインターチェンジが送信されるときにEDI 送信パイプラインを使用します。  
  
## <a name="see-also"></a>参照  
 [EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server が EDI メッセージを送信する方法](../core/how-biztalk-server-sends-edi-messages.md)   
 [チュートリアル (X12):EDI インターチェンジの送信](../core/walkthrough-x12-sending-edi-interchanges.md)