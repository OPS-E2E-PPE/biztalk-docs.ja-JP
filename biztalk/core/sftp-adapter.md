---
title: "SFTP アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f64c4c8-64a0-4e43-9660-b5c2d75d28aa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c30911f96e91a79e8cbd71b9d145cdef6dfd421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sftp-adapter"></a>SFTP アダプター
BizTalk Server は、 **SFTP** SSH ファイル転送プロトコルを使用してセキュリティで保護された FTP サーバーからメッセージを送受信するアダプター。 このトピックの内容には構成する手順が含まれています、 **SFTP**受信場所、およびセキュリティで保護された FTP サーバーからメッセージを送受信する SFTP 送信ポートを構成します。 一般的な質問と回答も含まれています。

## <a name="prerequisites"></a>前提条件
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** 、SFTP アダプターは WinSCP を使用して、SFTP に接続し、大規模な範囲の SFTP サーバーをサポートしています。 **ダウンロード[WinSCP](http://winscp.net)** 上、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム。 サポートされている WinSCP バージョンを確認してください[ハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)

[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]以前のバージョンは WinSCP をサポートしていません。
  
## <a name="configure-the-receive-location"></a>受信場所を構成します。
  
> [!NOTE]
>  受信場所を作成する前にする必要がありますが既に追加一方向の受信ポート。 参照してください[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)手順については、特定します。  
  
 
1.  BizTalk Server 管理コンソールで、 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**アプリケーションを展開し、受信場所を作成する です。  
  
2.  左側のウィンドウで、[ **受信ポート** ] ノードをクリックし、右側のウィンドウで、新しい受信場所に関連付ける受信ポートを右クリックし、[ **プロパティ**] をクリックします。  
  
3.  [ **受信ポートのプロパティ** ] ダイアログ ボックスの左側のウィンドウで [ **受信場所**] を選択し、右側のウィンドウで [ **新規作成** ] をクリックして、新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**セクションで、 **SFTP**から、**型**ドロップ ダウン リストし、をクリックして**構成**を受信場所のトランスポートのプロパティを構成します。  
  
5.  **SFTP トランスポートのプロパティ**次の操作を行います。  
 
     **Others**
         
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーに対して開くことができる同時接続の最大数を指定します。<br /><br /> この設定はサーバーごと、および受信場所ごとです。 以下のようなシナリオが考えられます。<br /><br /> は 2 つの受信場所に同じ値を設定、ConnectionLimit プロパティも含め、同じ構成プロパティ値を持ちます。 たとえば、プロパティは 6 に設定します。 このような状況では、1 つの接続が受信場所の両方で使用されている (使用可能な接続を 6) のプールです。<br /><br /> -は、2 つの受信場所が、同じ構成の値で構成されている ConnectionLimit プロパティが異なる値に設定します。 たとえば、ReceiveLocation1 プロパティが 6 に設定し、ReceiveLocation2 プロパティが 5 に設定します。 このような状況では、それぞれの受信場所では、独自の使用可能な接続には、独自の接続プールします。 ReceiveLocation1 接続プールの使用可能な接続の数は 6 です。 ReceiveLocation2 接続プールの使用可能な接続の数は 5 です。|  
    |Log | 始まる新しい[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]です。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 このログ ファイルを使用すると、すべてのエラーをトラブルシューティングできます。|
  
     **ポーリング**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |ポーリング間隔|アダプターが、サーバーをポーリングする間隔を指定します。 継続してポーリングを行うには、この値をゼロに設定します。<br /><br /> **既定値:** 5|  
    |ユニット|指定するポーリング間隔の単位を指定します。たとえば、秒、分、時間、日などです。<br /><br /> **既定値:** (秒)|  
  
     **プロキシ**(以降で新規[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |Address|DNS 名か、プロキシ サーバーの IP アドレスを指定します。|  
    |Password|プロキシ サーバーのパスワードを指定します。|  
    |ポート|プロキシ サーバーのポートを指定します。|  
    |型|プロキシ サーバーで使用されるプロトコルを指定します。|  
    |UserName|プロキシ サーバーのユーザー名を指定します。|  
  
     **セキュリティ**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |任意の SSH サーバー ホスト キーを承諾します。|ときに**True**、受信場所がサーバーからの任意の SSH パブリック ホスト キーを受け入れます。 ときに**False**、受信場所、サーバーの指紋認証を使用します。 指紋を入力して、 **SSHServerHostKeyFingerPrint**プロパティです。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|受信場所が SSH サーバーに対するクライアントの認証に使用する認証方法を選択します。 場合設定**パスワード**の値を入力する必要があります、**パスワード**プロパティです。 場合設定**PublicKeyAuthentication**、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey**プロパティです。 場合に設定**MultiFactorAuthentication**を入力する必要があります**Username**でその**パスワード**と**PrivateKey**です。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを入力、 **PrivateKeyPassword**プロパティです。<br /><br /> **既定値:**パスワード|  
    |暗号 |始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]です。 <br/><br/>暗号化の種類を入力します。<br/><br/>[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]オプション: Auto、AES、TripleDES<br/><br/>[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]オプション: Auto、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |Password|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode**に**パスワード**です。|  
    |秘密キー|設定した場合は、SFTP ユーザーの秘密キーを指定、 **ClientAuthenticationMode**に**PublicKeyAuthentication**です。<br /><br /> **注:**秘密キー ファイルは、指定した *.ppk ファイルである必要があります。|  
    |秘密キーのパスワード|指定されたキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey**プロパティです。|  
    |SSH サーバー ホスト キーのフィンガー プリント|SSH サーバーのパブリック ホスト キーの 指紋を指定します。|  
    |[ユーザー名]|SFTP サーバーにログオンするためのユーザー名を指定します。|  
  
     **SSH サーバー**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[ファイル マスク]|セキュリティで保護された FTP サーバーからファイルを取得するときに使用するファイル マスクを指定します。|  
    |フォルダーのパス|受信場所がファイルを取得できる、セキュリティで保護された FTP サーバー上のフォルダー パスを指定します。|  
    |ポート|ファイル転送が実行される、セキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|セキュリティで保護された FTP サーバーのサーバー名または IP アドレスを指定します。|  
  
6.  **[OK]**をクリックします。  
  
7.  [ **受信場所のプロパティ** ] ダイアログ ボックスで、受信場所を構成するための適切な値を入力し、[ **OK** ] をクリックして設定を保存します。 については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。
 
## <a name="configure-the-send-port"></a>送信ポートを構成します。  
  
1.  BizTalk Server 管理コンソールで、新しい送信ポートを作成または変更する既存の送信ポートをダブルクリックします。 詳細については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**SFTP**の**型**オプション、**トランスポート**のセクションで、**全般**タブです。  
  
2.  **全般**] タブの [、**トランスポート**セクションで、をクリックして、**構成**ボタンをクリックします。  
  
3.  **SFTP トランスポートのプロパティ**次を入力します。  
  
    **Others**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーに対して開くことができる同時接続の最大数を指定します。|  
    |Log | 始まる新しい[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]です。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 このログ ファイルを使用すると、すべてのエラーをトラブルシューティングできます。|
    |[一時フォルダ] | 始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]です。 <br/><br/>サイズの大きなファイルを、同じサーバーの指定された場所に原始的に移動する前のアップロード先となる SFTP サーバーの一時フォルダー。|  
    
    **プロキシ**(で始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |Address|DNS 名か、プロキシ サーバーの IP アドレスを指定します。|  
    |Password|プロキシ サーバーのパスワードを指定します。|  
    |ポート|プロキシ サーバーのポートを指定します。|  
    |型|プロキシ サーバーで使用されるプロトコルを指定します。|  
    |[ユーザー名]|プロキシ サーバーのユーザー名を指定します。|  
    
    **セキュリティ**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |任意の SSH サーバー ホスト キーにアクセスします。|ときに**True**、送信ポートがサーバーからの任意の SSH パブリック ホスト キーを受け入れます。 ときに**False**、ポートで指定されたキーを持つホスト キーに一致する、 **SSHServerHostKey**プロパティです。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|送信ポートが SSH サーバーに対するクライアントの認証に使用する認証方法を指定します。 場合設定**パスワード**の値を入力する必要があります、**パスワード**プロパティです。 場合設定**PublicKeyAuthentication**、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey**プロパティです。 場合に設定**MultiFactorAuthentication**指定する必要があります**Username**でその**パスワード**と**PrivateKey**です。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを入力、 **PrivateKeyPassword**プロパティです。<br /><br /> **既定値:**パスワード|  
    |暗号 | 始まる新しい[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]です。<br/><br/>暗号化の種類を入力します。<br/><br/>[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]オプション: Auto、AES、TripleDES<br/><br/>[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]オプション: Auto、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |Password|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode**に**パスワード**です。|  
    |秘密キー|設定した場合は、SFTP ユーザーの秘密キーを指定、 **ClientAuthenticationMode**に**PublicKeyAuthentication**です。|  
    |秘密キーのパスワード|指定されたキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey**プロパティです。|  
    |SSH サーバー ホスト キーのフィンガー プリント|場合、サーバーの認証にアダプターによって使用されるサーバー フィンガー プリントを指定、 **AccessAnySSHServerHostKey**プロパティに設定されている**False**です。 指紋が一致しない場合、接続は失敗します。|  
    |ユーザー名|セキュリティで保護された FTP サーバーのユーザー名を指定します。|  
    
    **SSH サーバー**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |追加する場合が存在します。|セキュリティで保護された FTP サーバーに転送中のファイルが既に転送先に存在する場合、このプロパティは転送中のファイルのデータを既存のファイルに追加するかどうかを指定します。 場合設定**True**データが追加されます。 場合設定**False**、転送先サーバーにファイルが上書きされます。<br /><br /> **既定値:** False|  
    |フォルダーのパス|ファイルのコピー先となる、セキュリティで保護された FTP サーバー上のフォルダー パスを指定します。|  
    |ポート|ファイル転送が実行される、セキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|セキュリティで保護された FTP サーバーのサーバー名または IP アドレスを指定します。|  
    |ターゲット ファイル名|セキュリティで保護された FTP サーバーに転送されるファイルの名前を指定します。 ターゲット ファイル名にマクロを使用することもできます。|  
  
4.  をクリックして**[ok]**と**OK**もう一度設定を保存します。  
  
## <a name="frequently-asked-questions"></a>よく寄せられる質問  
  
|質問|応答|  
|--------------|------------|  
|どの SFTP サーバーがサポートされていますか?|参照してください[サポートされる SFTP サーバー](http://social.technet.microsoft.com/wiki/contents/articles/29940.biztalk-serverbiztalk-services-supported-sftp-servers.aspx)です。 以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]、SFTP アダプターでは、WinSCP を使用して、SFTP に接続します。 その結果、WinSCP をサポートする SFTP サーバーが動作する必要があります。|  
|SFTP アダプターを相互認証方法 (公開キーとパスワード) とともに使用することはできますか?|開始**BizTalk Server 2013 R2**、[はい] です。 場合に設定**MultiFactorAuthentication**指定する必要があります**Username**でその**パスワード**と**PrivateKey**です。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを指定、 **PrivateKeyPassword**プロパティです。<br /><br /> - **BizTalk Server 2013**か、**パスワード**または**PublicKeyAuthentication**使用できます。 **MultiFactorAuthentication**付属の BizTalk Server 2013 の SFTP アダプターでサポートされていません。|  
|秘密キー形式はサポートされていますか? OpenSSH 秘密キー形式は使用できますか?|SFTP アダプターは PuTTY 秘密キー ファイル形式のみをサポートしています。 PuTTYgen を使用すると OpenSSH から .ppk 形式に変換できます。|  
|SSHServerHostKeyFingerPrint では、どのような指紋アルゴリズムと形式を使用する必要がありますか?|形式で、サーバーのキーの MD5 指紋を使用する必要があります:`ssh-rsa 2048 90:e4:9b:67:d9:22:a7:5f:6f:33:db:6a:b1:23:96:12`です。|  
|SFTP アダプターは 256 ビットの暗号化をサポートしていますか?|はい。SFTP アダプターは 256 ビットの暗号化をサポートしています。 次のような暗号化アルゴリズムがサポートされています。<br /><br /> -AES 暗号化: 256 ビット、192 ビット、または 128 ビット SDCTR か CBC<br /><br /> -3 des (TRIPLE-DES) 暗号化: 168 ビット SDCTR または CBC|  
|アダプターでサポートされる SSH のバージョンを教えてください。|SSH2 のみです。 バージョンが SSH1 である SFTP サーバーと接続を確立することはできません。|  
|ファイル マスクでは大文字と小文字が区別されますか。|不可。 「*.txt」および\*です。TXT が両方にとっては動作します。 BizTalk Server 2013 の最新の累積的な更新プログラムをインストールしてください。 BizTalk Server 2013 RTM リリースでは、大文字小文字を区別ファイル マスクがありました。|  
|バインドをエクスポートすると [パスワード] フィールドが空になります。 このようなバインドをインポートして受信場所を作成する場合、どのような変更を加える必要がありますか。|バインド ファイルを編集し、[パスワード] フィールドに変更を加えてください。 さらに、 `<Password vt="1">MySecretPassword</Password>`、 **vt =「1」**の null 値を示します。 変更する**vt =「8」**文字列を示します。 例:<br /><br /> `<Password vt="8">MySecretPassword</Password>`<br /><br /> 詳細については、次を参照してください[http://msdn.microsoft.com/library/system.runtime.interopservices.varenum (v=vs.100).aspx。](http://msdn.microsoft.com/library/system.runtime.interopservices.varenum\(v=vs.100\).aspx)|  
|ファイル パスの指定方法を教えてください。|通常、パスは `/folder/pathname` という形式で指定します。 ただし、サーバーの種類によっては別の形式になる場合や、先頭または末尾のスラッシュの有無が異なる場合があります。 そのため、次のように指定することもできます。<br /><br /> -                   `/folder/pathname`<br /><br /> -                   `/folder/pathname/`<br /><br /> -                   `folder/pathname`<br /><br /> -                   `folder/pathname/`|  
  

