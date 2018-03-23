---
title: EDI セキュリティに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9517f6c5b1aeae06b5989eef12fe269f81a27c74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="known-issues-with-edi-security"></a>EDI セキュリティに関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI と AS2 ソリューションのセキュリティに関する既知の問題について説明します。  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a>証明書が設定されていないパーティからの署名付きメッセージが BizTalk によって中断されない  
 [パーティのプロパティ] ページの [証明書] ノードでパーティに署名証明書が設定されていないが、そのパーティからの着信メッセージが署名付きである場合は、BizTalk Server がメッセージを中断せず、証明書の不在に基づいて例外を発行します。  
  
 [パーティ - AS2 メッセージの送信者] ページで受信メッセージ プロパティを上書きし、"メッセージに署名を付ける" プロパティをクリアすると、署名付き受信メッセージは停止されます。  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a>ファイルの改ざん防止のために、プログラム ファイル フォルダーへのアクセスが制限される場合がある  
 認証されていないユーザーが BizTalk Server の実行可能ファイルおよび EDI スキーマを格納するプログラム ファイル フォルダーにアクセスできる場合、それらのファイルはそのようなユーザーによって変更される可能性があります。 このような脅威から保護するためには、プログラム ファイル フォルダーでアクセス制御リスト (ACL) を使用し、アクセスを、信頼されているユーザーのみに制限できます。  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a>文字数の多いフィールドを含むスキーマがサービス拒否の攻撃を受けやすい  
 文字数の多いフィールドを含むカスタム スキーマは、サービス拒否の攻撃の対象になる可能性があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属のスキーマには、文字数が特に多いフィールドはありません。したがって、一般に、そのような攻撃を受けることはありません。  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a>制御番号が最大文字数を超えると、メッセージの処理が中止される  
 インターチェンジ、グループ、またはトランザクション セットの制御番号の最大文字数は制限されています。 これらの制御番号の文字数が最大文字数を超えると、単一パーティを対象としたそのエンコードの種類のすべてのメッセージの処理は中止されます。 別のエンコードの種類 (たとえば X12 ではなく EDIFACT など) のメッセージは影響を受けません。 これは、セキュリティの脆弱性を表している場合があります。  
  
 シーケンス番号の文字数が最大文字数を超えると、ユーザーは影響を受けたパーティについて、EDI プロパティでシーケンス番号をリセットする必要があります。 番号をリセットしたら、そのエンコードの種類のすべてのメッセージの処理を再開できます。  
  
 X12 メッセージの場合、制御番号の最大文字数は 9 桁です。 EDIFACT メッセージの場合、制御番号の最大文字数は、3 つのフィールドを合わせて 14 桁です。  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a>HTTP アダプターと共に EDI 受信パイプラインを使用した場合に確認が送信されないと、接続が開いたままになる  
 トランスポートの種類が HTTP であり、EDIReceive パイプラインを使用する受信場所を作成すると、セキュリティ上の問題が発生する可能性があります。 EdiReceive パイプラインでは、HTTP の "200 OK" 受信確認は生成されません。 EDI の受信確認が返されないと、接続が正常に終了せず、開いたままになります。 接続は、接続タイムアウト期間が経過したときにタイムアウトになります。  
  
 AS2EdiREceive パイプラインには、この問題はありません。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>ポートベースの認証が有効で、BizTalk Server が認証情報およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断される  
 **症状:**  
  
 BizTalk Server は、認証が有効になっている受信ポートでメッセージを受信したときに、そのメッセージを送信したパーティを特定できなければ、メッセージを中断します。  
  
 **考えられる原因**  
  
 受信ポートで認証が有効になっている (受信ポートの "認証しない" プロパティがオフになっている) 場合、インターチェンジを処理するためには、BizTalk Server で ISA1 ～ ISA2 (認証修飾子および認証情報) プロパティおよび ISA3 ～ ISA4 (セキュリティ修飾子およびセキュリティ情報) プロパティが設定されている必要があります。 これらのパーティのプロパティは、パーティの [X12 インターチェンジ処理のプロパティ] ページでインターチェンジの送信者として設定されます。 これらのプロパティの値を決定できない場合、BizTalk Server はメッセージを中断します。  
  
 これは、2 つの方法で発生します。 最初のケースでは、メッセージを送信したパーティを特定できない場合、BizTalk Server は EDI グローバル プロパティを使用するため、認証およびセキュリティの設定にアクセスできません。 その結果、メッセージは中断されます。 2 番目のケースで BizTalk Server には、パーティが決定されますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度アクセス権がない承認およびセキュリティ情報にし、メッセージを中断します。  
  
 **解決方法**  
  
 メッセージの送信側パーティを識別できること、およびパーティ アグリーメントで ISA1 ～ ISA2 および ISA3 ～ ISA4 プロパティが定義されていることを確認します。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)