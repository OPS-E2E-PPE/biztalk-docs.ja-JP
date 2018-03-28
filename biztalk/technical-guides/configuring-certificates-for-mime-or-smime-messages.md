---
title: MIME または SMIME メッセージの証明書の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea6e5481-fc2e-4b17-b6c8-1ec5d2bfa2c3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b54eb52eb7d8885f6a232d428df007d358e6292b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-certificates-for-mime-or-smime-messages"></a>MIME または SMIME メッセージの証明書の構成
セキュリティで保護するデータの転送で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、適切な BizTalk アイテムと証明書ストアにインストールされている証明書を関連付ける必要があります。 これは、MIME/SMIME でエンコードされたメッセージに適用されます。 AS2 トランスポートは、MIME/SMIME メッセージを転送にも適用されます。  
  
 証明書の使用シナリオとで使用できる構成オプションの参照として、次の表を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 手順の詳細については、このトピックの最後に「このセクション」という見出しの各トピックで提供されます。  
  
|**証明書の使用**|**ユーザー コンテキスト**|**証明書ストアの場所**|**証明書の種類**|**BizTalk 管理コンソール内の構成パラメーター**|  
|---------------------------|----------------------|------------------------------------|--------------------------|------------------------------------------------------------------------|  
|暗号化 (送信)|送信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|実行する各コンピューターにログオン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が S/MIME エンコーダー パイプラインをホストし、暗号化証明書をインポートする、**ローカル コンピューター \ その他のユーザー**を格納します。|取引先のパブリック証明書|-暗号化証明書の値を指定する **共通名** と **拇印** 上、 **証明書** のページ、 **送信ポートのプロパティ**  ダイアログ ボックス。<br />パイプラインを指定して **エンコード** オプションには、 **パイプラインの構成**  ダイアログ ボックス。 **パイプラインの構成**  の横にボタンをクリックしてダイアログ ボックスが表示されます、 **送信パイプライン** ドロップダウン リストで、 **全般** のページ、 **送信ポートのプロパティ**  ダイアログ ボックス。|  
|解読 (受信)|受信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|実行する各コンピューターにログオン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各ホスト インスタンス サービス アカウントとして S/MIME デコーダー パイプラインをホストし、暗号化解除証明書をインポートするが、**現在のユーザー \ 個人用**を格納します。 **注:** IIS 6.0 を実行するコンピューター上に成功するか、または後で、IIS アプリケーション プールのアカウントおよび受信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントは、同じであると、このアカウントがあることを確認するパイプラインの解読、メンバー、 \< *machineName*\>\IIS_WPG グループ。 IIS の設定の詳細についてはプロセス id」を参照して IIS [IIS アクセス許可の問題を解決するためのガイドライン](http://go.microsoft.com/fwlink/?LinkId=155161)(http://go.microsoft.com/fwlink/?LinkId=155161)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。 これらのプロセスは同じアカウントで実行する必要があります。これは、アカウント プロファイルが読み込まれ、それに続いてパイプラインで解読を実行するのに必要なレジストリ キーが読み込まれるようにするためです。 パフォーマンス上の理由から、IIS はプロファイルを読み込まない、アカウント、関連する w3wp.exe プロセスを開始するときにそのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスは、同じアカウントで構成する必要がありますように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がアカウント プロファイルとレジストリ キーを読み込みます。|独自のプライベート証明書|-暗号解読証明書の値を指定する **共通名** と **拇印** 上、 **証明書** の各ページ **ホストのプロパティ**  ダイアログ ボックス。<br />パイプラインを指定して **デコード** オプションには、 **パイプラインの構成**  ダイアログ ボックス。 **パイプラインの構成**  の横にボタンをクリックしてダイアログ ボックスが表示されます、 **受信パイプライン** ドロップダウン リストで、 **全般** のページ、 **受信場所のプロパティ**  ダイアログ ボックス。|  
|署名 (送信)|送信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|実行する各コンピューターにログオン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各ホスト インスタンス サービス アカウントに S/MIME エンコーダー パイプラインをホストし、署名証明書をインポートするは、**現在のユーザー \ 個人用**を格納します。|独自のプライベート証明書|-署名証明書の値を指定する **共通名** と **拇印** 上、 **証明書** のページ、 **BizTalk グループのプロパティ**  ダイアログ ボックス。 **注:**各 BizTalk サーバー グループごとに 1 つだけの署名証明書を指定できます。<br />パイプラインを指定して **エンコード** オプションには、 **パイプラインの構成**  ダイアログ ボックス。 **パイプラインの構成**  の横にボタンをクリックしてダイアログ ボックスが表示されます、 **送信パイプライン** ドロップダウン リストで、 **全般** のページ、 **送信ポートのプロパティ**  ダイアログ ボックス。|  
|署名の検証 (受信)|受信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|実行する各コンピューターにログオン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]S/MIME デコーダー パイプラインをホストし、署名証明書をインポートするが、**ローカル コンピューター \ その他のユーザー**を格納します。|取引先のパブリック証明書|-検証証明書の値を指定する **共通名** と **拇印** 上、 **証明書** の各ページ **パーティのプロパティ**  ダイアログ ボックス。<br />パイプラインを指定して **デコード** オプションには、 **パイプラインの構成**  ダイアログ ボックス。 **パイプラインの構成**  の横にボタンをクリックしてダイアログ ボックスが表示されます、 **受信パイプライン** ドロップダウン リストで、 **全般** のページ、 **受信場所のプロパティ**  ダイアログ ボックス。 **注:**パーティを他のパーティの署名の検証に使用する証明書から一意にする必要があります、署名の検証に使用する証明書。 **注:**      の構成、 **デコード** オプションは、MIME/SMIME デコーダー コンポーネントを含むパイプラインが展開されている必要があります。|  
|パーティの解決 (受信)|受信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|ログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]するパーティの解決が構成されているおよびコンピューターに証明書をインポート、**ローカル コンピューター \ その他のユーザー**を格納します。|取引先のパブリック証明書|-証明書の値を指定する **共通名** と **拇印** 上、 **証明書** の各ページ **ホストのプロパティ**  ダイアログ ボックス。<br />-指定 **パーティの解決** オプションには、 **パイプラインの構成**  ダイアログ ボックス。 **パイプラインの構成**  の横にボタンをクリックしてダイアログ ボックスが表示されます、 **受信パイプライン** ドロップダウン リストで、 **全般** のページ、 **受信場所のプロパティ**  ダイアログ ボックス。 **注:**      このオプションの構成が含まれたパイプラインの使用を要求する、 **パーティの解決** コンポーネントです。 **XMLReceive** パイプラインに含まれる、 **パーティの解決** コンポーネントです。|  
|HTTPS (送信)|送信ハンドラーに関連付けられているホスト インスタンスが使用するアカウント|SSL 通信では、クライアント証明書は必要ありません。 クライアント証明書が必要かどうかは、送信先の Web サーバーの管理者が決定します。 送信先の Web サーバーがクライアント証明書を要求する場合は、次の手順を実行します。<br /><br /> 取引先からパブリック証明書を取得します。<br />実行する各コンピューターにログオン ログ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントです。<br />-証明書をインポート、 **現在のユーザー \ 個人用** を格納します。<br /><br /> SSL を使用するように IIS を構成する方法の詳細については、サポート技術情報の記事を参照してください。[操作方法: インポートされた証明書のインストールで Windows Server 2003 Web サーバーで](http://go.microsoft.com/fwlink/?LinkId=155162)(http://go.microsoft.com/fwlink/?LinkId=155162)です。<br /><br /> Windows Server 2003 証明書サービス Web ページを使用して証明書を取得する方法については、次を参照してください。[を使用して Windows Server 2003 証明書サービス Web ページ](http://go.microsoft.com/fwlink/?LinkID=69975)(http://go.microsoft.com/fwlink/?LinkID=69975)です。 **注:** 、Windows Server 2008 コンピューターから証明書を取得する証明書サービス Web ページを使用して、Microsoft サポート技術情報記事 922706 を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=155317 ](http://go.microsoft.com/fwlink/?LinkId=155317) (http://go.microsoft.com/fwlink/?LinkId=155317)です。|取引先のパブリック証明書|-   **HTTP トランスポート** - 設定、 **SSL クライアント証明書の拇印**  オプションを選択、 **認証** のタブ、 **HTTP トランスポートのプロパティ**  ダイアログ ボックス。 **HTTP トランスポートのプロパティ** をクリックしてダイアログ ボックスが表示されます、 **構成** のボタンでは、 **全般** のページ、 **送信ポートのプロパティ**  ダイアログ ボックス。<br />-   **SOAP トランスポート** - 設定、 **クライアント証明書の拇印**  オプションを選択、 **全般** のタブ、 **SOAP トランスポートのプロパティ**  ダイアログ ボックス。 **SOAP トランスポートのプロパティ** をクリックしてダイアログ ボックスが表示されます、 **構成** のボタンでは、 **全般** のページ、 **送信ポートのプロパティ**  ダイアログ ボックス。|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法](../technical-guides/how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages.md)  
  
-   [暗号化された MIME または SMIME メッセージを送信する BizTalk Server を構成する方法](~/technical-guides/how-to-configure-biztalk-server-to-send-encrypted-mime-smime-messages.md)  
  
-   [MIME または SMIME メッセージを受信する BizTalk Server を構成する方法が署名済み](../technical-guides/how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages.md)  
  
-   [MIME または SMIME メッセージを送信する BizTalk Server を構成する方法が署名済み](../technical-guides/how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages.md)