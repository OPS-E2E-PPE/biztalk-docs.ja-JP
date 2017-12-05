---
title: "FTP アダプター構成プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- FTP adapters, properties
- FTP adapters, code sample
- FTP adapters, send ports
- FTP adapters, receive locations
- send ports, adapters
ms.assetid: 88a2084e-cb26-4136-9077-8b9463062ccc
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29124c17603abbc9b38a078238d13cdfb1c992e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="ftp-adapter-configuration-properties"></a>FTP アダプター構成プロパティ
次の表に、FTP アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|受信場所で監視する場所の完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|serverAddress|VT_BSTR|FTP サーバーの名前または IP アドレスを指定します。|なし|なし|  
|serverPort|VT_BSTR|接続先の FTP サーバーとの通信に使用する TCP ポートを指定します。|なし|なし|  
|userName|VT_BSTR|FTP サーバーへのアクセスに使用されるユーザー名を指定します。|なし|なし|  
|パスワード|VT_BSTR|FTP サーバーへのアクセスに使用するパスワードを指定します。|バインド ファイルをエクスポートする場合、この値は常にマスクされます。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このプロパティにパスワードを手動で設定する必要があります。|なし|  
|fileMask|VT_BSTR|ファイルの送信時に使用するファイル マスクのフィルタを指定します。|なし|なし|  
|targetFolder|VT_BSTR|FTP サーバーのポーリング場所を指定します。|なし|なし|  
|commandLogFilename|VT_BSTR|ログ ファイルのコピーを保存する場所を指定します。|なし|このファイルは、FTP アダプター経由でファイルを送受信する際のエラー状況の診断に使用します。|  
|representationType|VT_BSTR|FTP アダプターがデータを受け取る方法を選択します。|有効な値は、<br /><br /> -バイナリ<br />ASCII|既定値はバイナリです。|  
|spoolingFolder|VT_BSTR|FTP サーバー上の一時フォルダの場所を指定します。 このフォルダーは、転送エラーの修復に使用されます。|なし|なし|  
|receiveDataTimeOut|VT_BSTR|受信呼び出しを中止するまでの時間をミリ秒単位で指定します。 低速なサーバーによる受信場所のハングアップを防ぐために使用します。|なし|既定値は、90000 です。|  
|maximumBatchSize|VT_BSTR|BizTalk Server のバッチごとの最大バイト数を指定します。|なし|なし|  
|maximumNumberOfFiles|VT_BSTR|BizTalk Server のバッチごとの最大ファイル数を指定します。|なし|なし|  
|passiveMode|VT_BSTR|アダプタから FTP サーバーへの接続モードを指定します。|有効な値は、<br /><br /> -パッシブ<br />-アクティブ|既定値は [アクティブ] です。|  
|useNLST|VT_BSTR|既定のシステム定義ファイル一覧の代わりにファイル名のみ取得する場合は [はい] に指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [いいえ] です。|  
|beforeGet|VT_BSTR|ファイル GET コマンドの前に実行する FTP コマンドを指定します。|セミコロン (;) で個別のコマンド**注:** QUIT コマンドは、ファイルを取得する前にサポートされていません。|なし|  
|afterGet|VT_BSTR|ファイル GET コマンドの後に実行する FTP コマンドを指定します。|複数のコマンドを区切るにはセミコロン (;) を使用します|なし|  
|firewallType|VT_BSTR|展開するファイアウォールの種類を指定します。|有効な値は、<br /><br /> -なし<br />Socks 4<br />Socks 5|既定値は None です。|  
|firewallAddress|VT_BSTR|(DNS 名または IP アドレス) のファイアウォールのアドレスを指定します。|なし|なし|  
|firewallPort|VT_BSTR|ファイアウォールのポートを指定します。|有効な値は 1 から 65535 までです。|既定値は 21 です。|  
|firewallUserName|VT_BSTR|ファイアウォールのユーザー名を指定します。|なし|なし|  
|firewallPassword|VT_BSTR|ファイアウォールのパスワードを指定します。|なし|なし|  
|pollingUnitOfMeasure|VT_BSTR|pollingInterval プロパティの単位の種類を指定します。|有効な値は、<br /><br /> 秒数<br />-(分)<br />-時間<br />日|既定値は、[秒] です。|  
|pollingInterval|VT_BSTR|この場所のポーリングを行う間隔を示す値を指定します。|なし|継続してポーリングを行うには、この値を 0 に設定します。<br /><br /> 既定値は 60 です。|  
|redownloadInterval|VT_BSTR|FTP アダプターでファイルをダウンロードする間隔を秒単位で指定します。|deleteAfterDownload と enableTimeComparison properties プロパティが両方とも [いいえ] に設定されている場合のみ、このプロパティは適用できます。|値 -1 は、アダプターでファイルを再度ダウンロードしないことを示します。<br /><br /> 既定値は、-1 です。|  
|ssoAffiliateApplication|VT_BSTR|シングル サインオン (SSO) 関連のアプリケーションを指定します。|なし|なし|  
|errorThreshold|VT_BSTR|BizTalk Server が発生する可能性があるエラーの数を指定する場所が無効になります。|なし|既定値は 10 です。|  
|maxFileSize|VT_BSTR|ダウンロード可能なファイル サイズの最大値を、MB (メガバイト) 単位で指定します。|なし|制限しない場合は、値 0 を指定します。<br /><br /> 既定値は 100 です。|  
|useSsl|VT_BSTR|FTPS サーバーとの通信時に FTP アダプターが SSL を使用する必要がある場合は、この値に [はい] を指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [いいえ] です。|  
|useDataProtection|VT_BSTR|FTPS サーバーとの間でファイルの送受信を行う際に FTP アダプターが SSL を使用する必要がある場合は、この値に [はい] を指定します。|このプロパティは、useSsl プロパティが [はい] に設定されている場合にのみ有効です。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [はい] です。|  
|ftpsConnMode|VT_BSTR|FTPS サーバーに対して行う SSL 接続のモードを指定します。|有効な値は、<br /><br /> 明示的<br />暗黙的です|既定値は [明示] です。|  
|clientCertificateHash|VT_BSTR|SSL ネゴシエーションで使用する必要のあるクライアント証明書の SHA1 ハッシュを指定します。|なし|このハッシュに基づいて、BizTalk ホスト インスタンスを実行しているユーザー アカウントの個人ストアからクライアント証明書が取得されます。|  
|deleteAfterDownload|VT_BSTR|ダウンロード完了後にアダプターで FTP サーバーからファイルを削除する必要がある場合、[はい] を指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [はい] です。|  
|enableTimeComparison|VT_BSTR|ファイルのタイムスタンプが変更されている場合、アダプターでファイルを再度ダウンロードする必要があれば、[はい] を指定します。|このプロパティは、deleteAfterDownload が [いいえ] に設定されている場合にのみ有効です。<br /><br /> ターゲット FTP サーバーではこの機能用の MDTM コマンドをサポートしている必要があります。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [いいえ] です。|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>ftp://localhost:21/in/*.xml</uri><serverAddress>localhost</serverAddress><serverPort>21</serverPort><userName>domain\testuser</userName><password>******</password><fileMask>*.xml</fileMask><targetFolder>in</targetFolder><commandLogFilename>c:\temp\realftplog.txt</commandLogFilename><representationType>binary</representationType><maximumBatchSize>0</maximumBatchSize><maximumNumberOfFiles>0</maximumNumberOfFiles><passiveMode>False</passiveMode><firewallType>NoFirewall</firewallType><firewallPort>21</firewallPort><pollingUnitOfMeasure>Seconds</pollingUnitOfMeasure><pollingInterval>5</pollingInterval><errorThreshold>10</errorThreshold><maxFileSize>5000</maxFileSize><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><deleteAfterDownload>True</deleteAfterDownload><enableTimeComparison>False</enableTimeComparison></Config></AdapterConfig></CustomProps>  
```  
  
 次の表に、FTP アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|データの送信先の完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|serverAddress|VT_BSTR|ファイアウォールのアドレスとして、DNS 名または IP アドレスを指定します。|なし|なし|  
|serverPort|VT_BSTR|FTP サーバーのポート アドレスを指定します。|なし|既定値は 21 です。|  
|userName|VT_BSTR|FTP サーバーにログオンするユーザー名を指定します。|なし|なし|  
|パスワード|VT_BSTR|FTP サーバーにログオンするためのパスワードを指定します。|バインド ファイルをエクスポートする場合、この値は常にマスクされます。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このプロパティにパスワードを手動で設定する必要があります。|なし|  
|accountName|VT_BSTR|FTP サーバーのアカウント名を指定します。|省略可|なし|  
|targetFolder|VT_BSTR|FTP サーバー上のファイルの移動先を指定します。|なし|なし|  
|targetFileName|VT_BSTR|ファイルの代替名を指定します。 既定の名前を使用すれば、送信される各メッセージの名前が確実に一意になります。|なし|既定値は %MessageID%.xml です。|  
|commandLogFilename|VT_BSTR|ログ ファイルのコピーを保存する場所を指定します。 このログ ファイルは、FTP サーバー経由でファイルを送受信する際のエラー状況を診断するために使用できます。|なし|なし|  
|representationType|VT_BSTR|バイナリまたは ASCII に FTP が、データを送信する方法を選択します。|有効な値は、<br /><br /> -バイナリ<br />ASCII|既定値は [バイナリ] です。|  
|beforePut|VT_BSTR|ファイル PUT コマンド (FTP サーバーの既定値を変更するコマンドなど) の前に実行する FTP コマンドを指定します。|コマンドの区切りにはセミコロン (;) を使用します。 **注:** QUIT コマンドは、ファイルを配置する前にサポートされていません。|ファイルを開くコマンドは必要ありません。|  
|afterPut|VT_BSTR|ファイル PUT コマンドの後に実行する FTP コマンドを指定します。|コマンドの区切りにはセミコロン (;) を使用します。|なし|  
|allocateStorage|VT_BSTR|レガシ ホスト システムに記憶域スペースを割り当てるかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [いいえ] です。|  
|spoolingFolder|VT_BSTR|FTP サーバー上の一時フォルダの場所を指定します。 送信モードがバイナリである場合、このフォルダーは転送エラーの修復に使用されます。 送信モードが ASCII である場合、アダプターはアップロードを再開します。|なし|なし|  
|connectionLimit|VT_BSTR|サーバーに対して開くことができる FTP の同時接続の最大数を指定します。|なし|値 0 を指定した場合、接続は制限されません。|  
|passiveMode|VT_BSTR|パッシブ モードまたはアクティブ モードのどちらを使用するかを指定します。|有効な値は、<br /><br /> True (パッシブ モード)<br />False (アクティブ モード)|既定値は [False] (アクティブ モード) です。|  
|firewallType|VT_BSTR|展開するファイアウォールの種類を選択します。|有効な値は、<br /><br /> Socks 4<br />Socks 5<br />-なし|既定値は None です。|  
|firewallAddress|VT_BSTR|ファイアウォールのアドレスとして、DNS 名または IP アドレスを指定します。|なし|なし|  
|firewallPort|VT_BSTR|ファイアウォールのポートを指定します。|有効な値は 1 から 65535 までです。|既定値は 21 です。|  
|firewallUserName|VT_BSTR|ファイアウォールのユーザー名を指定します。|なし|なし|  
|firewallPassword|VT_BSTR|ファイアウォールのパスワードを指定します。|バインド ファイルをエクスポートする場合、この値は常にマスクされます。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このプロパティにパスワードを手動で設定する必要があります。|なし|  
|ssoAffiliateApplication|VT_BSTR|シングル サインオン (SSO) 関連のアプリケーションを指定します。|なし|なし|  
|useSsl|VT_BSTR|FTPS サーバーとの通信時に FTP アダプターが SSL を使用する必要がある場合は、この値に [はい] を指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [いいえ] です。|  
|useDataProtection|VT_BSTR|FTPS サーバーとの間でファイルの送受信を行う際に FTP アダプターが SSL を使用する必要がある場合は、この値に [はい] を指定します。|このプロパティは、useSsL プロパティが [はい] に設定されている場合にのみ有効です。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-なし|既定値は [はい] です。|  
|ftpsConnMode|VT_BSTR|FTPS サーバーに対して行う SSL 接続のモードを指定します。|有効な値は、<br /><br /> 明示的<br />暗黙的です|既定値は [明示] です。|  
|clientCertificateHash|VT_BSTR|SSL ネゴシエーションで使用する必要があるクライアント証明書の SHA1 ハッシュを指定します。|なし|このハッシュに基づいて、BizTalk ホスト インスタンスを実行しているユーザー アカウントの個人ストアからクライアント証明書が取得されます。|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><serverAddress>TestServer</serverAddress><serverPort>21</serverPort><userName>testuser</userName><password>******</password><accountName>testuser</accountName><targetFolder>output</targetFolder><targetFileName>%MessageID%.xml</targetFileName><commandLogFilename>c:\logfile\ftpsendlog.txt</commandLogFilename><representationType>binary</representationType><beforePut>CDW dir</beforePut><afterPut>CDUP </afterPut><allocateStorage>False</allocateStorage><spoolingFolder>tempfolder</spoolingFolder><connectionLimit>0</connectionLimit><passiveMode>False</passiveMode><firewallType>Socks4</firewallType><firewallAddress>TestServer</firewallAddress><firewallPort>21</firewallPort><firewallUserName>domain\testuser</firewallUserName><firewallPassword>******</firewallPassword><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><uri>ftp://TestServer:21/output/%MessageID%.xml</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  使用されるすべての名前/値ペアを格納する必要があります、アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定する場合、 \<AdapterConfig\>要素。 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。