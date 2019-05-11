---
title: SFTP アダプター |Microsoft Docs
description: 作成または受信場所を構成および送信ポートの faq の SFTP アダプターを使用して、BizTalk Server での SFTP アダプターの使用
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f64c4c8-64a0-4e43-9660-b5c2d75d28aa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 115eba0f61735ecaf361127c263c86b1bc518b59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393188"
---
# <a name="sftp-adapter"></a>SFTP アダプター
BizTalk Server が含まれています、 **SFTP** SSH ファイル転送プロトコルを使用してセキュリティで保護された FTP サーバーからメッセージを送受信するアダプター。 このトピックでには構成する手順が含まれています、 **SFTP**受信場所、およびセキュリティで保護された FTP サーバーからメッセージを送受信するための SFTP 送信ポートを構成します。 一般的な質問と回答も含まれています。

## <a name="prerequisites"></a>前提条件
**BizTalk Server 2016 以降で**、SFTP アダプターは、WinSCP を使用して、SFTP に接続し、したがってより大きな範囲の SFTP サーバーをサポートします。 **ダウンロード[WinSCP](http://winscp.net)**  BizTalk Server ランタイムにします。 サポートされている WinSCP バージョンを確認してください[ハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)

BizTalk Server 2013 R2 と以前のバージョンでは、WinSCP をサポートしていません。
  
## <a name="configure-the-receive-location"></a>受信場所を構成します。
  
> [!NOTE]
>  受信場所を作成する前にする必要がありますが既に追加一方向の受信ポート。 参照してください[受信ポートを作成](../core/how-to-create-a-receive-port.md)具体的な手順について。  
  
 
1.  BizTalk Server 管理コンソールで、BizTalk Server を展開し、 **BizTalk グループ**、展開**アプリケーション**アプリケーションを展開し、受信場所を作成します。  
  
2.  左側のウィンドウで、**[受信ポート]** ノードをクリックし、右側のウィンドウで、新しい受信場所に関連付ける受信ポートを右クリックし、**[プロパティ]** をクリックします。  
  
3.  **[受信ポートのプロパティ]** ダイアログ ボックスの左側のウィンドウで **[受信場所]** を選択し、右側のウィンドウで **[新規作成]** をクリックして、新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、**トランスポート**セクションで、 **SFTP**から、**型**ドロップダウン リスト、し、クリックして**構成**受信場所のトランスポートのプロパティを構成します。  
  
5.  **SFTP トランスポートのプロパティ**次の操作を行います。  
 
     **Others**
         
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーを開くことができる同時接続の最大数を指定します。<br /><br /> この設定はサーバーごとにあり、受信場所ごとです。 以下のようなシナリオが考えられます。<br /><br /> -は 2 つの受信場所に同じ値を設定、ConnectionLimit プロパティも含め、同じ構成プロパティ値を持ちます。 たとえば、プロパティは、6 に設定されます。 このような状況では、1 つの接続が受信場所の両方で使用されている (使用可能なに 6 接続) をプールします。<br /><br /> 2 つの受信場所が同じの構成値し、ConnectionLimit プロパティを別の値に設定されているがあります。 たとえば、ReceiveLocation1 プロパティが 6 に設定し、ReceiveLocation2 プロパティが 5 に設定します。 このような状況では、それぞれの受信場所では、独自の使用可能な接続には、独自の接続プールします。 ReceiveLocation1 接続プールには、使用可能な 6 つの接続があります。 ReceiveLocation2 接続プールには、5 つの使用可能な接続があります。|  
    |Log | BizTalk Server 2016 以降で利用できます。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 すべてのエラーのトラブルシューティングを行うには、このログ ファイルを使用します。|
  
     **ポーリング**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |ポーリング間隔|アダプターが、サーバーをポーリングする間隔を指定します。 ポーリングを継続的に、この値を 0 に設定します。<br /><br /> **既定値:** 5|  
    |ユニット|ポーリング間隔を指定する単位、秒、分、時間、または日を指定します。<br /><br /> **既定値:** Seconds|  
  
     **プロキシ**(BizTalk Server 2013 R2 以降を使用可能)  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |Address|DNS 名またはプロキシ サーバーの IP アドレスのいずれかを指定します。|  
    |パスワード|プロキシ サーバーのパスワードを指定します。|  
    |Port|プロキシ サーバーのポートを指定します。|  
    |型|プロキシ サーバーによって使用されるプロトコルを指定します。|  
    |UserName|プロキシ サーバーのユーザー名を指定します。|  
  
     **Security**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |任意の SSH サーバー ホスト キーを承諾します。|ときに**True**、受信場所は、サーバーからの任意の SSH パブリック ホスト キーを受け入れます。 ときに**False**、受信場所は、認証サーバーの指紋を使用します。 指紋を入力して、 **SSHServerHostKeyFingerPrint**プロパティ。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|受信場所が SSH サーバーに対するクライアントを認証するために使用する認証方法を選択します。 場合設定**パスワード**、値を入力する必要があります、**パスワード**プロパティ。 場合設定**PublicKeyAuthentication**、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey**プロパティ。 場合に設定**MultiFactorAuthentication**入力する必要があります**Username**でその**パスワード**と**PrivateKey**。 さらに、秘密キーがパスワードで保護されている、パスワードを入力に対しても同様、 **PrivateKeyPassword**プロパティ。<br /><br /> **既定値:** パスワード|  
    |暗号化の暗号 |BizTalk Server 2013 r2 以降を使用できます。 <br/><br/>暗号化の種類を入力します。<br/><br/>BizTalk Server 2013 R2 のオプション:自動、AES、TripleDES<br/><br/>BizTalk Server 2016 のオプション:自動、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |パスワード|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode**に**パスワード**します。|  
    |秘密キー|設定した場合は、SFTP ユーザーの秘密キーを指定、 **ClientAuthenticationMode**に**PublicKeyAuthentication**します。<br /><br /> **注:** 秘密キー ファイルは、指定した .ppk ファイルである必要があります。|  
    |秘密キーのパスワード|指定したキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey**プロパティ。|  
    |SSH サーバー ホスト キーの指紋|SSH サーバーのパブリック ホスト キーのフィンガー プリントを指定します。|  
    |[ユーザー名]|SFTP サーバーにログオンするユーザー名を指定します。|  
  
     **SSH サーバー**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |ファイル マスク|セキュリティで保護された FTP サーバーからファイルを取得するときに使用するファイル マスクを指定します。|  
    |フォルダーのパス|受信場所がファイルを取得できるからセキュリティで保護された FTP サーバー上のフォルダーのパスを指定します。|  
    |Port|ファイル転送が行われるセキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|サーバー名またはセキュリティで保護された FTP サーバーの IP アドレスを指定します。|  
  
6.  **[OK]** をクリックします。  
  
7.  **[受信場所のプロパティ]** ダイアログ ボックスで、受信場所を構成するための適切な値を入力し、**[OK]** をクリックして設定を保存します。 については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成](../core/how-to-create-a-receive-location.md)です。
 
## <a name="configure-the-send-port"></a>送信ポートを構成します。  
  
1.  BizTalk Server 管理コンソールで新しい送信ポートを作成または変更する既存の送信ポートをダブルクリックします。 詳細については、次を参照してください。[送信ポートを作成](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定**SFTP**の**型**オプション、**トランスポート**のセクション、**全般**タブ。  
  
2.  **全般**] タブで、**トランスポート**セクションで、[、**構成**ボタンをクリックします。  
  
3.  **SFTP トランスポートのプロパティ**次を入力します。  
  
    **Others**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーを開くことができる同時接続の最大数を指定します。|  
    |Log | BizTalk Server 2016 以降で利用できます。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 すべてのエラーのトラブルシューティングを行うには、このログ ファイルを使用します。|
    |一時フォルダー | BizTalk Server 2013 r2 以降を使用できます。 <br/><br/>同じサーバーにアトミックに必要な場所に移動することができますに大きなファイルをアップロードする SFTP サーバー上の一時フォルダーです。|  
    
    **プロキシ**(BizTalk Server 2013 R2 の提供開始予定)
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |Address|DNS 名またはプロキシ サーバーの IP アドレスのいずれかを指定します。|  
    |パスワード|プロキシ サーバーのパスワードを指定します。|  
    |Port|プロキシ サーバーのポートを指定します。|  
    |型|プロキシ サーバーによって使用されるプロトコルを指定します。|  
    |[ユーザー名]|プロキシ サーバーのユーザー名を指定します。|  
    
    **Security**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |任意の SSH サーバー ホスト キーをアクセスします。|ときに**True**、送信ポートは、サーバーからの任意の SSH パブリック ホスト キーを受け入れます。 ときに**False**で指定されたキーを持つホスト キーにすると、ポート、 **SSHServerHostKey**プロパティ。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|送信ポートが SSH サーバーに対するクライアントを認証するために使用する認証方法を指定します。 場合設定**パスワード**、値を入力する必要があります、**パスワード**プロパティ。 場合設定**PublicKeyAuthentication**、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey**プロパティ。 場合に設定**MultiFactorAuthentication**提供する必要があります**Username**でその**パスワード**と**PrivateKey**します。 さらに、秘密キーがパスワードで保護されている、パスワードを入力に対しても同様、 **PrivateKeyPassword**プロパティ。<br /><br /> **既定値:** パスワード|  
    |暗号化の暗号 | BizTalk Server 2013 r2 以降を使用できます。<br/><br/>暗号化の種類を入力します。<br/><br/>BizTalk Server 2013 R2 のオプション:自動、AES、TripleDES<br/><br/>BizTalk Server 2016 のオプション:自動、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |パスワード|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode**に**パスワード**します。|  
    |秘密キー|設定した場合は、SFTP ユーザーの秘密キーを指定、 **ClientAuthenticationMode**に**PublicKeyAuthentication**します。|  
    |秘密キーのパスワード|指定したキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey**プロパティ。|  
    |SSH サーバー ホスト キーのフィンガー プリント|場合、サーバーの認証に、アダプターによって使用されるサーバーの指紋を指定します、 **AccessAnySSHServerHostKey**プロパティに設定されて**False**します。 指紋が一致しない場合、接続が失敗します。|  
    |[ユーザー名]|セキュリティで保護された FTP サーバーのユーザー名を指定します。|  
    
    **SSH サーバー**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |場合は追加が存在します。|このプロパティでは、転送先に既にセキュリティで保護された FTP サーバーに転送されるファイルが存在する場合、転送中のファイルからデータを既存のファイルに追加するかどうを指定します。 場合設定**True**データが追加されます。 場合設定**False**、転送先サーバーにファイルが上書きされます。<br /><br /> **既定値:** False|  
    |フォルダーのパス|セキュリティで保護された FTP サーバーが、ファイルのコピー先フォルダーのパスを指定します。|  
    |Port|ファイル転送が行われるセキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|サーバー名またはセキュリティで保護された FTP サーバーの IP アドレスを指定します。|  
    |ターゲット ファイル名|セキュリティで保護された FTP サーバーにファイルを転送する名前を指定します。 ターゲット ファイル名のマクロを使用することもできます。|  
  
4.  をクリックして **[ok]** と**OK**設定を保存するには、もう一度です。  
  
## <a name="use-a-newer-winscp-version"></a>新しい WinSCP バージョンを使用して、

BizTalk Server で、新しいバージョンの WinSCP を使用するには、BizTalk は、どのアセンブリを読み込むを認識できるように、アセンブリのリダイレクトを追加します。 リダイレクトは、BizTalk Server 構成ファイルで構成されます。BTSNTSVC.exe.config (32 ビット ホスト インスタンス) および BTSNTSVC64.exe.config (64 ビット ホスト インスタンス)。

次に、サンプル構成の構文が含まれます。 置き換えてください`%NEWVERSION%`バージョン。

```
<configuration>
 <runtime>
  <assemblyBinding>
   <dependentAssembly>
    <assemblyIdentity name="WinSCPnet" publicKeyToken="2271ec4a3c56d0bf" culture="neutral" />
    <bindingRedirect oldVersion="1.2.10.6257" newVersion="%NEWVERSION%"/>
   </dependentAssembly>
  </assemblyBinding>
 </runtime>
</configuration>
```

完了すると、構成は、次のようにはなります。  

![構成ファイル内のアセンブリ リダイレクトします。](media/AssemblyRedirect.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問  
  
|質問|応答|  
|--------------|------------|  
|どの SFTP サーバーがサポートされますか。|参照してください[サポートされている SFTP サーバー](http://social.technet.microsoft.com/wiki/contents/articles/29940.biztalk-serverbiztalk-services-supported-sftp-servers.aspx)します。 BizTalk Server 2016 以降では、SFTP アダプターは、SFTP に接続するための WinSCP を使用します。 その結果、WinSCP をサポートする SFTP サーバーが動作する必要があります。|  
|SFTP アダプターは、(公開キーとパスワード) は、相互認証メソッドで使用できますか。|開始**BizTalk Server 2013 R2**、[はい] です。 場合に設定**MultiFactorAuthentication**提供する必要があります**Username**でその**パスワード**と**PrivateKey**します。 さらに、秘密キーがパスワードで保護されている場合ものパスワードを指定、 **PrivateKeyPassword**プロパティ。<br /><br /> - **BizTalk Server 2013**, か、**パスワード**または**PublicKeyAuthentication**ことができます。 **MultiFactorAuthentication**は、BizTalk Server 2013 に付属する SFTP アダプターではサポートされていません。|  
|秘密キー形式がサポートされますか。 OpenSSH 秘密キー形式を使用できますか。|SFTP アダプターは、PuTTY の秘密キー ファイル形式のみをサポートします。 PuTTYgen は、OpenSSH から .ppk 形式に変換するために使用できます。|  
|Sshserverhostkeyfingerprint、どの指紋アルゴリズムと形式を使用する必要がありますか。|形式でサーバーのキーの MD5 フィンガー プリントを使用する必要があります:`ssh-rsa 2048 90:e4:9b:67:d9:22:a7:5f:6f:33:db:6a:b1:23:96:12`します。|  
|SFTP アダプターは 256 ビット暗号化をサポートしますか。|はい - SFTP アダプターでは、256 ビット暗号化をサポートしています。 サポートされている暗号化アルゴリズムは次のとおりです。<br /><br /> -AES 暗号化:256 ビット、192 ビット、または 128 ビット SDCTR または CBC<br /><br /> -3 des (TRIPLE-DES) 暗号化。168 ビット SDCTR または CBC|  
|アダプターでサポートされる SSH のバージョンですか。|Ssh2 のみです。 SFTP サーバーが ssh1 であるバージョンとの接続を確立できません。|  
|ファイル マスクは、大文字小文字を区別しますか。|No. 「\*.txt」と です \*.TXT は幸先の良い動作します。 BizTalk Server 2013 の最新の累積的な更新プログラムをインストールしてください。 BizTalk Server 2013 RTM リリースでは、大文字小文字を区別するファイル マスクがありました。|  
|バインドをエクスポートでは、空白のパスワード フィールドを提供します。 これらのバインドをインポートすることによって、受信場所を作成しようとしています。 すべての変更になるとは|[パスワード] フィールドを編集することによって、バインド ファイルを編集します。 また、 `<Password vt="1">MySecretPassword</Password>`、 **vt =「1」** null 値を示します。 変更する**vt =「8」** 文字列を示します。 以下に例を示します。<br /><br /> `<Password vt="8">MySecretPassword</Password>`<br /><br /> 詳細については、次を参照してください。 [http://msdn.microsoft.com/library/system.runtime.interopservices.varenum(v=vs.100).aspx](http://msdn.microsoft.com/library/system.runtime.interopservices.varenum\(v=vs.100\).aspx)|  
|ファイルのパスを指定する方法は?|通常、パスはの形式で指定された`/folder/pathname`します。 ただし、別のサーバーでは、さまざまな形式、先頭または末尾のスラッシュの有無が必要です。 そのため、試すこともできます、次の。<br /><br /> -                   `/folder/pathname`<br /><br /> -                   `/folder/pathname/`<br /><br /> -                   `folder/pathname`<br /><br /> -                   `folder/pathname/`|  
  

