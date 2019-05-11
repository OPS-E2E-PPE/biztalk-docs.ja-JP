---
title: 既知の問題では、EDI 受信処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734a093a554f01b8625d8cd1ba8f154153d33979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330239"
---
# <a name="known-issues-with-edi-receive-processing"></a>既知の問題では、EDI 受信処理
このトピックでは、処理に関する既知の問題を説明します。 edi 受信パイプライン。  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a>末尾の区切り記号の受信側処理に失敗します。  
 **現象**  
  
 末尾の区切り記号と、トランザクション セットが失敗し、エラー コード AK403 = 6、X12 でエンコードされたメッセージまたはエラー コードの UCM3 = 4/UCD1 = 45、EDIFACT でエンコードされたメッセージ。  
  
 **考えられる原因**  
  
 末尾の区切り記号の処理が有効になっていません。  
  
 **解決方法**  
  
 メッセージを送信したパーティの EDI のプロパティを開きます。 (X12 または EDIFACT) の EDI のプロパティ ダイアログ ボックスの 検証と確認の生成 ページでは、"末尾の区切り記号/区切り記号を許可する を選択します。 このチェック ボックスをクリックすると、末尾の区切り記号の中間 XML で"末尾の区切り記号に空の XML タグを作成 をクリックして、空の XML タグが作成されたことを指定できます。  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a>CONTRL 確認を有効にするが生成されません。  
 **現象**  
  
 検証と確認の生成で機能確認の生成のチェック ボックス、送信元パーティがオンになっていますが、EDI 受信パイプラインが生成されません CONTRL 受信確認。  
  
 **考えられる原因**  
  
 CONTRL メッセージには、インターチェンジからコピーする必要があるいくつかの必須データ要素が含まれています。 場合は、インターチェンジのデータ要素が存在しないか、構文が無効、受信パイプラインは構文的に有効な CONTRL メッセージを生成できません。  
  
 **解決方法**  
  
 CONTRL 確認以外の他の方法でエラーを報告します。  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a>「...、受信パイプラインの実行中にエラーが発生しました」エラー メッセージ  
 **現象**  
  
 AS2 を実行しようとしています。 受信パイプライン、80040154 エラーが発生します。  
  
 **考えられる原因**  
  
 パイプラインは、64 ビット ホスト インスタンスではサポートされていません。  
  
 **解決方法**  
  
 パイプラインを 32 ビットのホストに関連付けます。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>ポート ベースの認証が有効になっているし、BizTalk Server では、承認、およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断されます。  
 **現象**  
  
 認証が有効になっていると、メッセージを特定できないを送信したパーティの受信ポートでメッセージが受信されると、BizTalk Server には、メッセージが中断されます。  
  
 **考えられる原因**  
  
 BizTalk Server が、「ISA1-2 (認証修飾子およびセキュリティ情報)」の設定が必要です (受信ポートの [認証なし] プロパティがオフ)、受信ポートの認証が有効な場合、「ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)」インターチェンジを処理するためにプロパティです。 これらのプロパティは、x12 の場合、パーティの設定は、インターチェンジの送信者としてのパーティのインターチェンジ処理のプロパティ ページ。 BizTalk Server がこれらのプロパティの値を判別できない場合、メッセージは中断されます。  
  
 これは、2 つの方法で発生します。 最初のケースでは、BizTalk Server は、メッセージを送信したパーティを決定できない場合は EDI グローバル プロパティを使用し、承認およびセキュリティ設定へのアクセスはありません。 その結果、メッセージは中断されます。 2 番目のケースでは、BizTalk Server は、パーティを決定しますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度、承認およびセキュリティ情報へのアクセスと、メッセージは中断されます。  
  
 **解決方法**  
  
 メッセージの送信元パーティを識別でき、パーティ アグリーメントで ISA1 ~ 2 および ISA3 ~ 4 のプロパティが定義されているようにします。  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a>分割された HIPAA サブドキュメントの SE01 が正しくないです。  
 **現象**  
  
 トランザクション セット トレーラー (SE01 フィールド) は、X12 または HIPAA ドキュメントのヘッダーおよびトレーラ セグメントを含む、データ セグメントの数を提供します。 ただし、分割 HIPAA をサブ ドキュメントの場合、EDI 受信パイプラインには再計算ではなく、元のドキュメントと同じ SE01 値が適用されます。  
  
 **原因**  
  
 EDI 受信パイプラインのコピーの SE01 値元の HIPAA ドキュメントから分割サブ ドキュメントにします。  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a>重複する UNB5 または UNH1 のエラー メッセージの説明がないです。  
 BizTalk Server は、重複する UNB5 を持つメッセージを受信した場合 (インターチェンジ制御番号) または UNH1 (トランザクション セット参照番号) は、エラー コードとポストバックの説明は明確に示しません問題の種類。  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a>BizTalk Server は、メモリが不足している場合、大容量のインターチェンジは中断します。  
 BizTalk Server は、大容量のインターチェンジを解析するときにメモリ不足実行可能性があります。 その場合が、エラーが送信され、インターチェンジを中断します。 グループ ハブ ページでは、すべての中断された大容量のインターチェンジの内容を表示できませんされます。 メッセージの最初の部分を表示することができますが、BizTalk Server が表示できる中断されたインターチェンジからのデータの量に制限されています。  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a>KEDIFACT スキーマで列挙に追加された韓国語の文字が UNICODE である必要があります。  
 BizTalk サーバーでは、韓国語の文字で KEDIFACT でエンコードされたインターチェンジを受信すると、インターチェンジを処理するのにコード ページ/文字セット値 UNB2 フィールドで使用されます。 ただし、列挙型に ID データ型の韓国語の文字を追加して KEDIFACT スキーマを変更する場合スキーマの上部にある指定された値、utf-16 UNICODE に追加する必要があります。  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a>受信パイプラインの実行、EDI 内から、オーケストレーションはサポートされていません  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、通常実行することができます、オーケストレーションの式図形内からパイプラインを受信します。 この機能は、EDIReceive パイプラインまたは AS2EdiReceive パイプラインは、サポートされていないためにテストされていません。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更する必要がありません。  
 BizTalk EDI アプリケーションのアイテムを変更または削除する必要があります。 このアプリケーションが変更された場合は、構成を解除し、EDI および AS2 機能を再構成して、元のアプリケーションを復元する方法はありません。  
  
## <a name="see-also"></a>参照  
 [EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)   
 [チュートリアル (X12):EDI インターチェンジの受信と受信確認の送信](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)