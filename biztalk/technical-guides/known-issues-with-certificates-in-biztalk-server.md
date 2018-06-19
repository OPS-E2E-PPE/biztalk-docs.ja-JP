---
title: BizTalk Server での証明書に関する既知の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab58264b-2475-4831-9f08-bfbaa293022f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aecfca9f58758e72f357439901684a0a617f3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297578"
---
# <a name="known-issues-with-certificates-in-biztalk-server"></a>BizTalk Server での証明書に関する既知の問題
このセクションで使用されるデジタル証明書の管理に関する既知の問題の説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
## <a name="general-certificate-issues"></a>[全般] 証明書の問題  
  
### <a name="lack-of-connectivity-to-the-certificate-revocation-list-will-cause-a-certificate-to-be-rejected"></a>証明書失効リストに接続できない問題が発生する、証明書が拒否されます。  
 この問題は、次のエラー:"認証エラーが発生しました。 メッセージの署名に使用する証明書を発行した証明機関 (CA) の状態が不明です。" このエラーは、署名証明書が MMC の下に表示されるときに有効な場合でも発生することができます (を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ユーザー) に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
 この状態は、受信パイプラインで S/MIME デコーダー コンポーネントで「証明書の失効を確認する」プロパティが有効になっている場合に発生することができます。 このプロパティが true の場合、BizTalk Server に設定するときは、受信した証明書が失効しているかどうかに証明書失効リスト (CRL) のクエリを実行を試みます。 証明書自体が失効していない場合は重要ではありません。 BizTalk Server は、接続の問題があるため、対応する CRL を照会することはできない場合、は、証明書を受け付けることができません。 このエラーをトラブルシューティングするには、使用する証明書をダブルクリックして、証明書のプロパティを表示します。 詳細 タブで、「CRL 配布ポイント」フィールドの一覧内の属性が表示されます。 この属性で、CA サーバーで CRL をポイントするいくつかの Url を入力する必要があります。 BizTalk server は、CRL を取得するには、この Url のいずれかにアクセスできる必要があります。 それ以外の場合、失効確認は失敗し、上記のエラーが通知されます。  
  
### <a name="the-other-people-certificate-store-is-not-initialized-until-accessed"></a>アクセスされるまで、その他のユーザーの証明書ストアが初期化されていません  
 この問題は、次の証明書ストアのエラーを追加または送信/受信ポート/を使用して場所を変更しようとすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者コンソールでのリモート:「を開けませんでした証明書ストアです」。 "システムは、指定されたファイルを見つけることができません。 (システム)"です。  
  
> [!NOTE]  
>  ログオンしている場合に直接、管理コンソールを使用してこれらの成果物を変更することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
 新しくインストールされたコンピューターで、**その他のユーザーの証明書**ストアが 2 回アクセスする場合を除き、初期化されていません。 グループの構成時に初期化するにはこの**その他のユーザーの証明書**格納、およびその結果の構成が行われているグループにコンピューターにこのエラーが表示されません。  
  
### <a name="biztalk-server-only-supports-one-personal-certificate-for-each-biztalk-group"></a>BizTalk Server では、BizTalk グループごとに 1 つの個人証明書のみがサポートしています  
 BizTalk グループによって使用される個人証明書を指定するには、BizTalk グループのプロパティで個人証明書の拇印を設定します。 BizTalk グループには、企業、部署、ハブ、または別の部署を表すことができます。  
  
## <a name="as2-certificate-issues"></a>AS2 の証明書の問題  
  
### <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 デコーダーは、ホストまたは送信先パーティの証明書が構成されていることを検証できません。  
 AS2 デコーダーは、メッセージのプライベート証明書が証明書ストアで構成されていれば、そのメッセージを解読します。 ただし、AS2 デコーダーは、暗号化解除証明書がホストで構成されている証明書と同じであるかどうかは検証しません。 受信したメッセージは、複数の証明書を使用して暗号化できます。  
  
### <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server を証明書が有効でない場合は、ワイヤ形式で保存されたメッセージの暗号化を解除することはできません。  
 **現象**  
  
 BizTalk Server が、ワイヤ形式で否認不可データベースに保存された受信 AS2 メッセージを解読できません。  
  
 **考えられる原因**  
  
 メッセージの解読に必要な証明書の有効期限が切れているか、証明書が失効しています。 これは、AS2 メッセージが否認不可データベースに保存されてから一定期間が経過している場合に発生する傾向があります。 この現象が発生した場合、メッセージの有効な証明書に直接アクセスする権限がない可能性があります。  
  
 **解決策**  
  
 メッセージを解読するための有効な証明書を取得してください。  
  
### <a name="if-an-as2-message-cannot-be-decrypted-the-problem-may-be-fixed-by-re-importing-the-certificate"></a>証明書を再インポートすることによって、問題が修正される場合は、AS2 メッセージを解読できません。  
 **現象**  
  
 AS2 デコーダで、例外が発生し、AS2 メッセージの暗号化を解除しようとしたとき、次のエラーをスローします。  
  
```  
"The AS2 Decoder encountered an exception during processing. Details of the message and exception are as follows:   
   AS2-From:"PARTNER" AS2-To:"HOME" MessageID:"<137706.1178060412333@servername>"   
   MessageType: "unknown" Exception:"An error occurred when decrypting an AS2 message."  
System.ArgumentNullException: Value cannot be null.  
Parameter name: PayloadContentType  
at Microsoft.BizTalk.Edi.Reporting.Common.Utilities.ValidateArgument(Object o,  
String parameterName, Boolean isEmptyStringValidationRequired)  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.ValidateParameters()  
at Microsoft.BizTalk.EdiInt.Reporting.AS2MessageActivity.Create()"  
  
```  
  
 **考えられる原因**  
  
 AS2 メッセージの解読に使用する証明書を個人証明書ストアに再度読み込む必要があります。  
  
 **解決策**  
  
 個人証明書ストアから既存の証明書を削除し、証明書のインポート ウィザードで証明書を個人証明書ストアに再インポートします。 右クリックして行う、**証明書**の下のフォルダー、**の個人用ストア**をポイントして、**すべてのタスク**、クリックして**インポート**です。  
  
### <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>インプロセス ホスト インスタンスと分離ホスト インスタンスに対して同じログオンを使用して、その個人ストアが認識されることを確認するには  
 個人証明書ストアは、ログオン資格情報がホスト インスタンスに関連付けられているユーザーのユーザー プロファイルが読み込まれた場合にのみ、メッセージ処理に使用できます。 個人証明書ストアは、証明書 (ユーザー独自の秘密キー) の署名と解読に使用されます。 ユーザー プロファイルは、インプロセス ホスト インスタンスでは既定で読み込まれますが、分離ホスト インスタンスでは既定で読み込まれません。 分離ホストのユーザー プロファイルは、アプリケーションで読み込むことができます。 インプロセス ホスト インスタンスと分離ホスト インスタンスに同じログオンを使用することで、この問題を回避することもできます。  
  
 アプリケーションによってユーザー プロファイルを読み込む代わりに、プロファイルを読み込むための空のサービスを作成することもできます。 空のサービスの作成の詳細については、次を参照してください。[する方法: Windows サービスの作成](http://go.microsoft.com/fwlink/?LinkId=155149)(http://go.microsoft.com/fwlink/?LinkId=155149) で、Visual Studio のヘルプ。  
  
 プロファイルを読み込むには、空のサービスを作成すると、次の手順します。  
  
1.  をクリックして**開始**、順にクリック**実行**を開くには、**実行** ダイアログ ボックス。  
  
2.  **実行** ダイアログ ボックスで、「 **service.msc**とキーを押します**ENTER**開くには、**サービス**MMC スナップイン。  
  
3.  開く、**プロパティ**作成したサービスのダイアログ ボックス。 サービスを右クリックし **プロパティ**です。  
  
4.  をクリックして、**ログオン**] タブで [**アカウント**、し分離ホスト インスタンスで使用するログオン名を入力します。  
  
5.  **[OK]** をクリックします。  
  
6.  手動でサービスを開始するログオン ユーザーのユーザー プロファイルを読み込めません。  
  
### <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>証明書のキーの使用法属性が、証明書の使用法に一致する必要がある  
 AS2 トランスポートに使用する証明書には、その使用目的に必要な属性が設定されている必要があります。 署名および署名の検証を行うには、証明書の [キーの使用法] 属性が [デジタル署名] である必要があります。 暗号化および解読を行うには、証明書の [キーの使用法] 属性が [データの暗号化] または [キーの暗号化] である必要があります。 キー使用法属性を確認するにはクリックすると、証明書をダブルクリックして、**詳細** タブで、**証明書** ダイアログ ボックスやチェック、**キー使用法**フィールド.  
  
### <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>AS2-To プロパティがパーティに対して設定されていない場合、送信 MDN に対して証明書解決の一覧が検証される  
 送出 MDN の既定のアグリーメントでは、証明書解決の一覧の検証が実行されます。 この検証を実行する必要がない場合は、受信側パーティを解決できるようにするため、およびパーティのプロパティを特定できるようにするために、正しい AS2-To パーティ プロパティが設定されていることを確認します。 これにより、証明書解決の一覧の検証を要求する既定のアグリーメントが使用されなくなります。 また、AS2 パーティ プロパティの [全般] ページで、"証明書失効リストを確認する" プロパティを無効にする必要もあります。