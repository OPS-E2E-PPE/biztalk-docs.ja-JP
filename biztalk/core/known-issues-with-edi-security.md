---
title: EDI セキュリティに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d4afab871dc34e3249d2ea3ed7d531b18472a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380668"
---
# <a name="known-issues-with-edi-security"></a>EDI セキュリティに関する既知の問題
このトピックでは、のセキュリティに関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 ソリューション。  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a>BizTalk によってなしの証明書を設定する対象のパーティから署名付きメッセージが中断されません。  
 BizTalk Server がメッセージを中断発展し、証明書の有無に基づいて例外をスローできません (証明書 ノードでパーティのパーティのプロパティ ページの) のパーティに対して署名証明書を設定しない場合は、そのパーティからの受信メッセージの署名.  
  
 ([パーティ-AS2 メッセージの送信者] ページ)、受信メッセージのプロパティをオーバーライドして、「メッセージに署名する必要があります」プロパティをオフに、BizTalk Server は署名付き受信メッセージを中断します。  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a>Program Files フォルダーへのアクセスはファイルの改ざんを防ぐために制限できます。  
 認証されていないユーザーに BizTalk Server 実行可能ファイルおよび EDI スキーマを含むプログラム ファイル フォルダーがある場合これらのユーザーは可能性があるこれらのファイルを変更できます。 その脅威に対する保護のため、することができますを使用して、アクセス制御リスト (Acl)、Program Files フォルダーに信頼されたユーザーへのアクセスを制限します。  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a>長いフィールドを持つスキーマをサービス拒否攻撃を受けやすいことができます。  
 文字数の多いフィールドを持つカスタム スキーマは、サービス拒否攻撃によって悪用される可能性可能性があります。 同梱されているスキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]多い、フィールドを持たず、したがっては一般に、このような攻撃を受けやすくなります。  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a>制御番号が、最大の長さを超えた場合、メッセージの処理は中止されます。  
 インターチェンジ、グループ、またはトランザクション セットの制御番号が、最大長が制限されています。 これらの制御番号のいずれかの長さが最大長を超える場合は、単一のパーティ、そのエンコードの種類のすべてのメッセージの処理は中止されます。 エンコードの種類 (たとえば X12 ではなく EDIFACT など) のメッセージには影響しません。 これにより、セキュリティの脆弱性が表すことができます。  
  
 シーケンス番号の長さが最大長を超えるユーザーが影響を受けるパーティの EDI プロパティでシーケンス番号をリセットします。 数をリセットすると、そのエンコードの種類のすべてのメッセージもう一度処理することができます。  
  
 X12 メッセージで、コントロールの最大長は 9 桁の数字です。 EDIFACT メッセージの場合は、制御番号の最大長は、14 桁を 3 つのフィールドが。  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a>確認が送信されない場合、受信の HTTP アダプターはまま、接続を開くとパイプラインを EDI を使用して  
 トランスポートの種類が HTTP であり、EDIReceive パイプラインを使用する受信場所を作成すると、セキュリティ上の問題が発生する可能性があります。 EdiReceive パイプラインでは、HTTP の "200 OK" 受信確認は生成されません。 EDI の受信確認が返されないと、接続が正常に終了せず、開いたままになります。 接続は、接続タイムアウト期間が経過したときにタイムアウトになります。  
  
 これは、AS2EdiREceive パイプラインを備えた問題ではありません。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>ポート ベースの認証が有効になっているし、BizTalk Server では、承認、およびセキュリティ情報にアクセスできない場合、X12 でエンコードされたメッセージが中断されます。  
 **現象**  
  
 認証が有効になっていると、メッセージを特定できないを送信したパーティの受信ポートでメッセージが受信されると、BizTalk Server には、メッセージが中断されます。  
  
 **考えられる原因**  
  
 BizTalk Server が、「ISA1-2 (認証修飾子およびセキュリティ情報)」の設定が必要です (受信ポートの [認証なし] プロパティがオフ)、受信ポートの認証が有効な場合、「ISA3 ~ 4 (セキュリティ修飾子およびセキュリティ情報)」インターチェンジを処理するためにプロパティです。 これらのプロパティは、x12 の場合、パーティの設定は、インターチェンジの送信者としてのパーティのインターチェンジ処理のプロパティ ページ。 BizTalk Server がこれらのプロパティの値を判別できない場合、メッセージは中断されます。  
  
 これは、2 つの方法で発生します。 最初のケースでは、BizTalk Server は、メッセージを送信したパーティを決定できない場合は EDI グローバル プロパティを使用し、承認およびセキュリティ設定へのアクセスはありません。 その結果、メッセージは中断されます。 2 番目のケースでは、BizTalk Server は、パーティを決定しますが、パーティの ISA1 2 および ISA3 ~ 4 のプロパティが構成されていない場合、BizTalk Server がもう一度、承認およびセキュリティ情報へのアクセスと、メッセージは中断されます。  
  
 **解決方法**  
  
 メッセージの送信元パーティを識別でき、パーティ アグリーメントで ISA1 ~ 2 および ISA3 ~ 4 のプロパティが定義されているようにします。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)