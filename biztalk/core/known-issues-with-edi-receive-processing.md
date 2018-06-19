---
title: 既知の問題 EDI 受信処理 |Microsoft ドキュメント
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
ms.openlocfilehash: 75ab2769ab4a6eacf885dbf675a6bd3fda371007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262962"
---
# <a name="known-issues-with-edi-receive-processing"></a>EDI 受信処理に関する既知の問題
このトピックでは、EDI 受信パイプラインでの処理に関する既知の問題について説明します。  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a>末尾の区切り記号の受信側での処理が失敗する  
 **現象**  
  
 末尾に区切り記号のあるトランザクション セットは、X12 でエンコードされたメッセージの場合はエラー コード AK403= 6、EDIFACT でエンコードされたメッセージの場合はエラー コード UCM3=4/UCD1=45 によって失敗します。  
  
 **考えられる原因**  
  
 末尾の区切り記号の処理が有効になっていません。  
  
 **解決策**  
  
 メッセージを送信したパーティの [EDI のプロパティ] を開きます。 X12 または EDIFACT の [EDI のプロパティ] ダイアログ ボックスの [検証と確認の生成] ページで、[末尾の区切り記号を許可する] をオンにします。 次に、[末尾の区切り記号に空の XML タグを作成する] をオンにすることにより、中間 XML で末尾の区切り記号として空の XML タグが作成されるように指定できます。  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a>CONTRL 確認は有効であるのに生成されない  
 **現象**  
  
 送信元パーティの [検証と確認の生成] の [機能確認を生成する] チェック ボックスがオンになっているにもかかわらず、EDI 受信パイプラインによって CONTRL 確認が生成されていません。  
  
 **考えられる原因**  
  
 CONTRL メッセージにはインターチェンジからコピーする必要のある必須データ要素がいくつか含まれています。 インターチェンジ内のデータ要素が欠落しているか、構文が無効である場合、受信パイプラインは構文が有効な CONTRL メッセージを生成できません。  
  
 **解決策**  
  
 CONTRL 確認以外の方法でエラー状態を報告します。  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a>「...、受信パイプラインを実行中にエラーが発生しました」 エラー メッセージ  
 **現象**  
  
 AS2 受信パイプラインを実行しようとすると、80040154 エラーが発生します。  
  
 **考えられる原因**  
  
 64 ビットのホスト インスタンスではパイプラインがサポートされていません。  
  
 **解決策**  
  
 パイプラインを 32 ビットのホストと関連付けます。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>ポートベースの認証が有効で、BizTalk Server が認証情報およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断される  
 **現象**  
  
 BizTalk Server は、認証が有効になっている受信ポートでメッセージを受信したときに、そのメッセージを送信したパーティを特定できなければ、メッセージを中断します。  
  
 **考えられる原因**  
  
 受信ポートで認証が有効になっている (受信ポートの "認証しない" プロパティがオフになっている) 場合、インターチェンジを処理するためには、BizTalk Server で ISA1 ～ ISA2 (認証修飾子および認証情報) プロパティおよび ISA3 ～ ISA4 (セキュリティ修飾子およびセキュリティ情報) プロパティが設定されている必要があります。 これらのパーティのプロパティは、パーティの [X12 インターチェンジ処理のプロパティ] ページでインターチェンジの送信者として設定されます。 これらのプロパティの値を決定できない場合、BizTalk Server はメッセージを中断します。  
  
 これは、2 つの方法で発生します。 最初のケースでは、メッセージを送信したパーティを特定できない場合、BizTalk Server は EDI グローバル プロパティを使用するため、認証およびセキュリティの設定にアクセスできません。 その結果、メッセージは中断されます。 2 番目のケースでは、BizTalk Server には、パーティが決定されますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度アクセス権がない承認およびセキュリティ情報にし、メッセージは中断されます。  
  
 **解決策**  
  
 メッセージの送信側パーティを識別できること、およびパーティ アグリーメントで ISA1 ～ ISA2 および ISA3 ～ ISA4 プロパティが定義されていることを確認します。  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a>分割された HIPAA サブドキュメントの SE01 に誤りがある  
 **現象**  
  
 トランザクション セット トレーラー (SE01 フィールド) は、X12/HIPAA ドキュメントのヘッダー セグメントとトレーラー セグメントを含めたデータ セグメントの数を提供します。 ただし、分割された HIPAA サブドキュメントの場合、EDI 受信パイプラインでは元のドキュメントと同じ SE01 値が適用され、再計算が行われません。  
  
 **原因**  
  
 EDI 受信パイプラインでは、元の HIPAA ドキュメントの SE01 値が分割されたサブドキュメントにコピーされます。  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a>UNB5 または UNH1 の重複に対するエラー メッセージの記述内容が明確でない  
 UNB5 (インターチェンジ制御番号) または UNH1 (トランザクション セット参照番号) が重複したメッセージを受信した場合に表示されるエラー コードと説明は、問題の内容を明確に示しません。  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a>メモリ不足になると BizTalk Server が大容量のインターチェンジを中断する  
 大容量のインターチェンジを解析するとき、BizTalk Server はメモリ不足になる場合があります。 その場合、エラーが送信され、インターチェンジが中断されます。 [グループ ハブ] ページでは、中断された大容量のインターチェンジの内容を確認できません。 メッセージの最初の部分を表示することができますが、BizTalk Server は表示できるように中断されたインターチェンジからのデータの量に制限されます。  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a>KEDIFACT スキーマで列挙に追加する韓国語の文字は UNICODE 形式である必要がある  
 BizTalk Server は、KEDIFACT でエンコードされた韓国語の文字を含むインターチェンジを受信すると、UNB2 フィールドのコード ページ/文字セット値を使用してこのインターチェンジを処理します。 ただし、ID データ型の韓国語の文字を列挙に追加して KEDIFACT スキーマを変更する場合は、スキーマの冒頭で指定されているとおり、UTF-16 UNICODE の値を追加する必要があります。  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a>オーケストレーション内からの EDI 受信パイプラインの実行がサポートされない  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、通常はオーケストレーションの式図形内から受信パイプラインを実行できます。 この機能は、EDIReceive パイプラインまたは AS2EdiReceive パイプラインについてはテストされていないため、サポートされていません。  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a>BizTalk EDI アプリケーションを変更できない  
 BizTalk EDI アプリケーション内のアイテムは、変更または削除できません。 このアプリケーションを変更すると、EDI 機能や AS2 機能の構成を解除して再構成しても、元のアプリケーションを復元することはできません。  
  
## <a name="see-also"></a>参照  
 [EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [BizTalk Server が EDI メッセージを受信する方法](../core/how-biztalk-server-receives-edi-messages.md)   
 [チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)