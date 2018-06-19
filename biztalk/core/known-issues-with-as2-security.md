---
title: AS2 セキュリティに関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b291e000-630d-49a1-8e19-f76c4dfee294
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb633e092ed568bb3817df7be788364934be446
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262402"
---
# <a name="known-issues-with-as2-security"></a>AS2 セキュリティに関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 ソリューションのセキュリティに関する既知の問題について説明します。  
  
## <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 デコーダーによって、ホストまたは送信先パーティで証明書が構成されていることが検証されない  
 AS2 デコーダーは、メッセージのプライベート証明書が証明書ストアで構成されていれば、そのメッセージを解読します。 ただし、AS2 デコーダーは、暗号化解除証明書がホストで構成されている証明書と同じであるかどうかは検証しません。 受信したメッセージは、複数の証明書を使用して暗号化できます。  
  
## <a name="storing-as2-messages-in-wire-format-can-lead-to-a-security-issue"></a>AS2 メッセージをワイヤ形式で保存すると、セキュリティ上の問題が発生する  
 証明書が使用されない場合、AS2 メッセージをワイヤ形式で否認不可 (NRR) データベースに格納することはお勧めしません。 これを行うと、セキュリティ上の問題が発生する可能性があります。  
  
## <a name="messages-or-mdns-to-be-stored-in-the-nrr-database-should-be-signed"></a>NRR データベースに保存されるメッセージまたは MDN に署名を付ける必要がある  
 受信の否認不可を確実に行うには、該当するメッセージの認証と整合性を確立する必要があります。 メッセージのデジタル署名を使用して認証と整合性を確立することをお勧めします。 この結果、メッセージまたは MDN を否認不可データベースに保存するように AS2 パーティのプロパティを構成した場合は、保存するメッセージまたは MDN に署名を付けるように AS2 プロパティを構成する必要があります。  
  
## <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>証明書が有効でない場合、BizTalk Server がワイヤ形式で保存されたメッセージを解読できない  
 **現象**  
  
 BizTalk Server が、ワイヤ形式で否認不可データベースに保存された受信 AS2 メッセージを解読できません。  
  
 **考えられる原因**  
  
 メッセージの解読に必要な証明書の有効期限が切れているか、証明書が失効しています。 これは、AS2 メッセージが否認不可データベースに保存されてから一定期間が経過している場合に発生する傾向があります。 この現象が発生した場合、メッセージの有効な証明書に直接アクセスする権限がない可能性があります。  
  
 **解決策**  
  
 メッセージを解読するための有効な証明書を取得してください。  
  
## <a name="the-inner-envelope-of-a-signed-as2-message-must-not-be-changed-after-the-signature-has-been-calculated"></a>署名が計算された後は、署名付きの AS2 メッセージの内部エンベロープを変更することはできません。  
 AS2 メッセージに署名が付けられるとき、内部エンベロープのヘッダーおよびペイロードに基づいて署名が計算されます。 署名の計算後に内部エンベロープを変更すると、署名が破損します。 境界ヘッダー、または境界ヘッダーの外側の要素は変更できますが、境界ヘッダー内のすべてを変更しないでください。  
  
## <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>インプロセス ホスト インスタンスと分離ホスト インスタンスに同じログオンを使用して、個人証明書ストアが認識されるようにする  
 個人証明書ストアは、ログオン資格情報がホスト インスタンスに関連付けられているユーザーのユーザー プロファイルが読み込まれた場合にのみ、メッセージ処理に使用できます。 個人証明書ストアは、証明書 (ユーザー独自の秘密キー) の署名と解読に使用されます。 ユーザー プロファイルは、インプロセス ホスト インスタンスでは既定で読み込まれますが、分離ホスト インスタンスでは既定で読み込まれません。 分離ホストのユーザー プロファイルは、アプリケーションで読み込むことができます。 インプロセス ホスト インスタンスと分離ホスト インスタンスに同じログオンを使用することで、この問題を回避することもできます。  
  
 アプリケーションによってユーザー プロファイルを読み込む代わりに、プロファイルを読み込むための空のサービスを作成することもできます。 空のサービスを作成する方法の詳細については、次を参照してください。[する方法: Windows サービスの作成](http://go.microsoft.com/fwlink/?LinkId=196492)です。 サービスを作成した後、コンピューターの管理 ダイアログ ボックスが開き、サービスのプロパティ ダイアログ ボックスが開き、 をクリックして、**ログオン** タブで **アカウント**、使用するログオン名を入力してください、分離ホスト インスタンス、およびクリック**OK**です。 これにより、このログオン ユーザーのユーザー プロファイルを読み込むサービスを手動で開始できます。  
  
## <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>証明書のキーの使用法属性が、証明書の使用法に一致する必要がある  
 AS2 トランスポートに使用する証明書には、その使用目的に必要な属性が設定されている必要があります。 署名および署名の検証を行うには、証明書の [キーの使用法] 属性が [デジタル署名] である必要があります。 暗号化および解読を行うには、証明書の [キーの使用法] 属性が [データの暗号化] または [キーの暗号化] である必要があります。 証明書をダブルクリックし、[証明書] ダイアログ ボックスの [詳細] タブをクリックして [キーの使用法] ボックスを参照することで、[キーの使用法] 属性を確認できます。  
  
## <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>AS2-To プロパティがパーティに対して設定されていない場合、送信 MDN に対して証明書解決の一覧が検証される  
 送出 MDN の既定のアグリーメントでは、証明書解決の一覧の検証が実行されます。 この検証を実行する必要がない場合は、受信側パーティを解決できるようにするため、およびパーティのプロパティを特定できるようにするために、正しい AS2-To パーティ プロパティが設定されていることを確認します。 これにより、証明書解決の一覧の検証を要求する既定のアグリーメントが使用されなくなります。 また、AS2 パーティ プロパティの [全般] ページで、"証明書失効リストを確認する" プロパティを無効にする必要もあります。