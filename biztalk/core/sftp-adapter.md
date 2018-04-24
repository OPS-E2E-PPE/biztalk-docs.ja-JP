---
title: SFTP アダプター |Microsoft ドキュメント
description: 作成または受信場所を構成および BizTalk Server で、SFTP アダプターを使用してよく寄せられる質問を含む SFTP アダプターを使用してポートを送信
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
ms.openlocfilehash: 0d28c3b453ab3e704ddbb06ed42b23dc641a6711
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="sftp-adapter"></a>SFTP アダプター
BizTalk Server は、 **SFTP** SSH ファイル転送プロトコルを使用してセキュリティで保護された FTP サーバーからメッセージを送受信するアダプター。 このトピックでは、構成する手順、 **SFTP** 受信場所、およびセキュリティで保護された FTP サーバーからメッセージを送受信する SFTP 送信ポートを構成します。 一般的な質問と回答も含まれています。

## <a name="prerequisites"></a>前提条件
**BizTalk Server 2016 で始まる**、SFTP アダプターは WinSCP を使用して、SFTP に接続し、大規模な範囲の SFTP サーバーをサポートしています。 **ダウンロード[WinSCP](http://winscp.net)**  BizTalk Server ランタイムにします。 サポートされている WinSCP バージョンを確認してください[ハードウェアとソフトウェアの要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)

BizTalk Server 2013 R2 および以前のバージョンでは、WinSCP はサポートされません。
  
## <a name="configure-the-receive-location"></a>受信場所を構成します。
  
> [!NOTE]
>  受信場所を作成する前にする必要がありますを既に追加した一方向の受信ポートです。 参照してください[受信ポートを作成](../core/how-to-create-a-receive-port.md)手順については、特定します。  
  
 
1.  BizTalk Server 管理コンソールで、BizTalk Server を展開し、 **BizTalk グループ**、展開**アプリケーション**アプリケーションの順に展開し、受信場所を作成する です。  
  
2.  左側のウィンドウで、**[受信ポート]** ノードをクリックし、右側のウィンドウで、新しい受信場所に関連付ける受信ポートを右クリックし、**[プロパティ]** をクリックします。  
  
3.  **[受信ポートのプロパティ]** ダイアログ ボックスの左側のウィンドウで **[受信場所]** を選択し、右側のウィンドウで **[新規作成]** をクリックして、新しい受信場所を作成します。  
  
4.  **受信場所のプロパティ** ダイアログ ボックスで、 **トランスポート** ] セクションの [ **SFTP** から、 **型** クリックしてドロップダウン リスト **構成** 受信場所のトランスポートのプロパティを構成します。  
  
5.  **SFTP トランスポートのプロパティ**, 、次の操作を行います。  
 
     **他のユーザー**
         
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーに対して開くことができる同時接続の最大数を指定します。<br /><br /> この設定はサーバーごと、および受信場所ごとです。 以下のようなシナリオが考えられます。<br /><br /> -が 2 つの受信、ConnectionLimit プロパティが同じ値に設定を含む同じの構成プロパティ値を持つ場所です。 たとえば、プロパティは 6 に設定します。 このような状況では、1 つの接続は受信場所の両方で使用されている (使用可能なに 6 接続) のプールです。<br /><br /> -が 2 つの受信場所が同じの構成値を使用して構成および ConnectionLimit プロパティが異なる値に設定します。 たとえば、ReceiveLocation1 プロパティが 6 に設定し、ReceiveLocation2 プロパティが 5 に設定します。 このような状況では、それぞれの受信場所では、独自の利用可能な接続には、独自の接続プールです。 ReceiveLocation1 接続プールの使用可能な接続の数は 6 です。 ReceiveLocation2 接続プールの使用可能な接続の数は 5 です。|  
    |Log | BizTalk Server 2016 以降で利用できます。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 このログ ファイルを使用して、エラーを解決します。|
  
     **ポーリング**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |ポーリング間隔|アダプターが、サーバーをポーリングする間隔を指定します。 継続してポーリングを行うには、この値をゼロに設定します。<br /><br /> **既定値:** 5|  
    |ユニット|指定するポーリング間隔の単位を指定します。たとえば、秒、分、時間、日などです。<br /><br /> **既定値:** (秒)|  
  
     **プロキシ**(BizTalk Server 2013 R2 以降を使用可能)  
  
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
    |任意の SSH サーバー ホスト キーをそのまま使用します。|**True**, 、受信場所が、サーバーからの任意の SSH パブリック ホスト キーを受け入れます。 **False**, 、認証のため、受信場所が、サーバーの指紋を使用します。 指紋を入力して、 **SSHServerHostKeyFingerPrint** プロパティです。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|受信場所が SSH サーバーに対するクライアントの認証に使用する認証方法を選択します。 場合に設定 **パスワード**, の値を入力する必要があります、 **パスワード** プロパティです。 場合に設定 **PublicKeyAuthentication**, 、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey** プロパティです。 場合に設定 **MultiFactorAuthentication** を入力する必要があります **ユーザー名** とその **パスワード** と **PrivateKey**します。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを入力、 **PrivateKeyPassword** プロパティです。<br /><br /> **既定値:** パスワード|  
    |暗号 |BizTalk Server 2013 R2 以降を利用できます。 <br/><br/>暗号化の種類を入力します。<br/><br/>BizTalk Server 2013 R2 のオプション: Auto、AES、TripleDES<br/><br/>BizTalk Server 2016 のオプション: Auto、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |Password|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode** に **パスワード**します。|  
    |秘密キー|設定した場合、SFTP ユーザーの秘密キーの指定、 **ClientAuthenticationMode** に **PublicKeyAuthentication**します。<br /><br /> **注:** 秘密キー ファイルは、指定した .ppk ファイルである必要があります。|  
    |秘密キーのパスワード|指定したキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey** プロパティです。|  
    |SSH サーバー ホスト キー フィンガー プリント|SSH サーバーのパブリック ホスト キーの 指紋を指定します。|  
    |[ユーザー名]|SFTP サーバーにログオンするためのユーザー名を指定します。|  
  
     **SSH サーバー**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[ファイル マスク]|セキュリティで保護された FTP サーバーからファイルを取得するときに使用するファイル マスクを指定します。|  
    |フォルダーのパス|受信場所がファイルを取得できる、セキュリティで保護された FTP サーバー上のフォルダー パスを指定します。|  
    |ポート|ファイル転送が実行される、セキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|セキュリティで保護された FTP サーバーのサーバー名または IP アドレスを指定します。|  
  
6.  **[OK]** をクリックします。  
  
7.  **[受信場所のプロパティ]** ダイアログ ボックスで、受信場所を構成するための適切な値を入力し、**[OK]** をクリックして設定を保存します。 については、**受信場所のプロパティ**ダイアログ ボックスを参照してください[受信場所を作成](../core/how-to-create-a-receive-location.md)です。
 
## <a name="configure-the-send-port"></a>送信ポートを構成します。  
  
1.  BizTalk Server 管理コンソールでは、新しい送信ポートを作成または変更する既存の送信ポートをダブルクリックします。 詳細については、次を参照してください。[送信ポートを作成](../core/how-to-create-a-send-port2.md)です。 すべての送信ポートのオプションを構成し、指定 **SFTP** の **型** オプション、 **トランスポート** のセクションで、 **全般**  タブをクリックします。  
  
2.  **全般的な**  タブで、 **トランスポート**  をクリックして、 **構成**  ボタンをクリックします。  
  
3.  **SFTP トランスポートのプロパティ**, 、次を入力します。  
  
    **他のユーザー**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |接続の制限|サーバーに対して開くことができる同時接続の最大数を指定します。|  
    |Log | BizTalk Server 2016 以降で利用できます。 <br/><br/>クライアント側のログ ファイルを作成する完全なパスを入力します。 このログ ファイルを使用して、エラーを解決します。|
    |[一時フォルダ] | BizTalk Server 2013 R2 以降を利用できます。 <br/><br/>サイズの大きなファイルを、同じサーバーの指定された場所に原始的に移動する前のアップロード先となる SFTP サーバーの一時フォルダー。|  
    
    **プロキシ**(以降で使用可能 BizTalk Server 2013 R2)
    
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
    |任意の SSH サーバー ホスト キーをアクセスします。|**True**, 、送信ポートがサーバーからの任意の SSH パブリック ホスト キーを受け入れます。 **False**, 、ホスト キーで指定したキーにすると、ポート、 **SSHServerHostKey** プロパティです。<br /><br /> **既定値:** False|  
    |クライアントの認証モード|送信ポートが SSH サーバーに対するクライアントの認証に使用する認証方法を指定します。 場合に設定 **パスワード**, の値を入力する必要があります、 **パスワード** プロパティです。 場合に設定 **PublicKeyAuthentication**, 、内のユーザーの秘密キーを入力する必要があります、 **PrivateKey** プロパティです。 場合に設定 **MultiFactorAuthentication** 提供する必要があります **ユーザー名** とその **パスワード** と **PrivateKey**します。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを入力、 **PrivateKeyPassword** プロパティです。<br /><br /> **既定値:** パスワード|  
    |暗号 | BizTalk Server 2013 R2 以降を利用できます。<br/><br/>暗号化の種類を入力します。<br/><br/>BizTalk Server 2013 R2 のオプション: Auto、AES、TripleDES<br/><br/>BizTalk Server 2016 のオプション: Auto、AES、Arcfour、Blowfish、TripleDES、および DES|  
    |Password|設定した場合は、SFTP ユーザーのパスワードを指定、 **ClientAuthenticationMode** に **パスワード**します。|  
    |秘密キー|設定した場合、SFTP ユーザーの秘密キーの指定、 **ClientAuthenticationMode** に **PublicKeyAuthentication**します。|  
    |秘密キーのパスワード|指定したキーに必要な場合は、秘密キーのパスワードを指定、 **PrivateKey** プロパティです。|  
    |SSH サーバー ホスト キー フィンガー プリント|場合、サーバーの認証に、アダプターによって使用されるサーバーの指紋を指定、 **AccessAnySSHServerHostKey** にプロパティが設定されている **False**します。 指紋が一致しない場合、接続は失敗します。|  
    |ユーザー名|セキュリティで保護された FTP サーバーのユーザー名を指定します。|  
    
    **SSH サーバー**
    
    |プロパティ|目的|  
    |--------------|----------------|  
    |追加が存在します。|セキュリティで保護された FTP サーバーに転送中のファイルが既に転送先に存在する場合、このプロパティは転送中のファイルのデータを既存のファイルに追加するかどうかを指定します。 場合に設定 **True**, 、データが追加されます。 場合に設定 **False**, 、転送先サーバーにファイルが上書きされます。<br /><br /> **既定値:** False|  
    |フォルダーのパス|ファイルのコピー先となる、セキュリティで保護された FTP サーバー上のフォルダー パスを指定します。|  
    |ポート|ファイル転送が実行される、セキュリティで保護された FTP サーバーのポート アドレスを指定します。|  
    |サーバーのアドレス|セキュリティで保護された FTP サーバーのサーバー名または IP アドレスを指定します。|  
    |ターゲット ファイル名|セキュリティで保護された FTP サーバーに転送されるファイルの名前を指定します。 ターゲット ファイル名にマクロを使用することもできます。|  
  
4.  をクリックして **[ok]** と **OK** 設定を保存します。  
  
## <a name="use-a-newer-winscp-version"></a>新しい WinSCP バージョンを使用します。

WinSCP の新しいバージョンを使用して、BizTalk Server で、するには、BizTalk アセンブリを読み込むにわかるように、アセンブリのリダイレクトを追加します。 リダイレクトは、BizTalk Server 構成ファイルで構成します。 BTSNTSVC.exe.config (32 ビット ホスト インスタンス) と BTSNTSVC64.exe.config (64 ビット ホスト インスタンス)。

次のサンプル構成の構文が含まれます。 置き換えてください`%NEWVERSION%`バージョン。

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

完了したら、構成は次のようになります。  

![構成ファイル内のアセンブリ リダイレクトします。](media/AssemblyRedirect.png)

## <a name="frequently-asked-questions"></a>よく寄せられる質問  
  
|質問|応答|  
|--------------|------------|  
|どの SFTP サーバーがサポートされていますか?|参照してください [SFTP サーバーがサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/29940.biztalk-serverbiztalk-services-supported-sftp-servers.aspx)します。 BizTalk Server 2016 以降では、SFTP アダプターは、SFTP への接続に WinSCP を使用します。 その結果、WinSCP をサポートする SFTP サーバーは動作します。|  
|SFTP アダプターを相互認証方法 (公開キーとパスワード) とともに使用することはできますか?|始まる **BizTalk Server 2013 R2**, 、[はい] です。 場合に設定 **MultiFactorAuthentication** 提供する必要があります **ユーザー名** とその **パスワード** と **PrivateKey**します。 さらに、秘密キーがパスワードで保護されている場合、同様のパスワードを指定、 **PrivateKeyPassword** プロパティです。<br /><br /> -の **BizTalk Server 2013**, か、 **パスワード** または **PublicKeyAuthentication** 使用できます。 **MultiFactorAuthentication** は、BizTalk Server 2013 と同梱 SFTP アダプターではサポートされていません。|  
|秘密キー形式はサポートされていますか? OpenSSH 秘密キー形式は使用できますか?|SFTP アダプターは PuTTY 秘密キー ファイル形式のみをサポートしています。 PuTTYgen を使用すると OpenSSH から .ppk 形式に変換できます。|  
|SSHServerHostKeyFingerPrint では、どのような指紋アルゴリズムと形式を使用する必要がありますか?|形式のサーバーのキーの MD5 フィンガー プリントを使用する必要があります: `ssh-rsa 2048 90:e4:9b:67:d9:22:a7:5f:6f:33:db:6a:b1:23:96:12`です。|  
|SFTP アダプターは 256 ビットの暗号化をサポートしていますか?|はい。SFTP アダプターは 256 ビットの暗号化をサポートしています。 次のような暗号化アルゴリズムがサポートされています。<br /><br /> -AES 暗号化: 256 ビット、192 ビットまたは 128 ビット SDCTR または CBC<br /><br /> -3 des (TRIPLE-DES) 暗号化: 168 ビット SDCTR または CBC|  
|アダプターでサポートされる SSH のバージョンを教えてください。|SSH2 のみです。 バージョンが SSH1 である SFTP サーバーと接続を確立することはできません。|  
|ファイル マスクでは大文字と小文字が区別されますか。|不可。 「\*.txt」と です \*.TXT は幸先の良い動作します。 BizTalk Server 2013 の累積的な最新の更新プログラムをインストールしてください。 BizTalk Server 2013 RTM リリースでは、区別するファイル マスクがありました。|  
|バインドをエクスポートすると [パスワード] フィールドが空になります。 このようなバインドをインポートして受信場所を作成する場合、どのような変更を加える必要がありますか。|バインド ファイルを編集し、[パスワード] フィールドに変更を加えてください。 さらに、 `<Password vt="1">MySecretPassword</Password>`, 、**vt =「1」** null 値を示します。 変更する **vt =「8」**, 、文字列を示します。 以下に例を示します。<br /><br /> `<Password vt="8">MySecretPassword</Password>`<br /><br /> 詳細については、次を参照してください。 [http://msdn.microsoft.com/library/system.runtime.interopservices.varenum(v=vs.100).aspx](http://msdn.microsoft.com/library/system.runtime.interopservices.varenum\(v=vs.100\).aspx)|  
|ファイル パスの指定方法を教えてください。|通常、パスは `/folder/pathname` という形式で指定します。 ただし、サーバーの種類によっては別の形式になる場合や、先頭または末尾のスラッシュの有無が異なる場合があります。 そのため、次のように指定することもできます。<br /><br /> -                   `/folder/pathname`<br /><br /> -                   `/folder/pathname/`<br /><br /> -                   `folder/pathname`<br /><br /> -                   `folder/pathname/`|  
  

