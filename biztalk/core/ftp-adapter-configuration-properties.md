---
title: FTP アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- FTP adapters, properties
- FTP adapters, code sample
- FTP adapters, send ports
- FTP adapters, receive locations
- send ports, adapters
ms.assetid: 88a2084e-cb26-4136-9077-8b9463062ccc
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae34d48585db6025a6270388a724faf2a45f511
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387882"
---
# <a name="ftp-adapter-configuration-properties"></a>FTP アダプター構成プロパティ
次の表の FTP アダプターに対して設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Uri|VT_BSTR|受信場所で監視する場所の完全なパスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|serverAddress|VT_BSTR|サーバー名または FTP サーバーの IP アドレスを指定します。|なし|なし|  
|serverPort|VT_BSTR|ターゲット FTP サーバーと通信するために、TCP ポートを指定します。|なし|なし|  
|userName|VT_BSTR|FTP サーバーへのアクセスに使用されるユーザー名を指定します。|なし|なし|  
|password|VT_BSTR|FTP サーバーへのアクセスに使用されるパスワードを指定します。|バインド ファイルをエクスポートするときにこの値は常にマスクされます。 このプロパティは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
|FileMask|VT_BSTR|ファイルの送信時に使用するファイル マスクのフィルタを指定します。|なし|なし|  
|targetFolder|VT_BSTR|FTP サーバーのポーリング場所を指定します。|なし|なし|  
|commandLogFilename|VT_BSTR|ログ ファイルのコピーを保存する場所を指定します。|なし|FTP アダプター経由でファイルを送受信するときにエラー状態を診断するのにには、このファイルを使用します。|  
|RepresentationType|VT_BSTR|FTP アダプターがデータを受信する方法を選択します。|有効な値は、<br /><br /> -バイナリ<br />ASCII|既定値はバイナリです。|  
|SpoolingFolder|VT_BSTR|FTP サーバー上の一時フォルダの場所を指定します。 これを使用するには、転送エラーからの復旧を保証します。|なし|なし|  
|receiveDataTimeOut|VT_BSTR|受信呼び出しを中止する前に、時間をミリ秒単位で指定します。 これは、低速のサーバーの受信場所のハングアップを防ぐために使用されます。|なし|既定値は、90000 です。|  
|maximumBatchSize|VT_BSTR|BizTalk Server のバッチあたりのバイト数の最大数を指定します。|なし|なし|  
|maximumNumberOfFiles|VT_BSTR|BizTalk Server のバッチごとのファイルの最大数を指定します。|なし|なし|  
|PassiveMode|VT_BSTR|アダプターが FTP サーバーに接続モードを指定します。|有効な値は、<br /><br /> -パッシブ<br />-アクティブ|既定値は、アクティブです。|  
|useNLST|VT_BSTR|既定のシステム定義のファイル一覧の代わりにのみのファイル名を取得するには、[はい] を指定します。|有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は [いいえ]|  
|beforeGet|VT_BSTR|ファイル GET 前に実行する FTP コマンドを指定します。|セミコロン (;) で個別のコマンド**に注意してください。** QUIT コマンドは、ファイルを取得する前にサポートされていません。|なし|  
|afterGet|VT_BSTR|ファイル GET の後に実行する FTP コマンドを指定します。|セミコロン (;) で個別のコマンド|なし|  
|firewallType|VT_BSTR|ファイアウォールの展開の種類を指定します。|有効な値は、<br /><br /> -None<br />[Socks 4]<br />Socks 5|既定値は、None です。|  
|firewallAddress|VT_BSTR|(DNS 名または IP アドレス) のファイアウォールのアドレスを指定します。|なし|なし|  
|firewallPort|VT_BSTR|ファイアウォールのポートを指定します。|有効な値は、1 から 65535 までの間は。|既定値は、21 です。|  
|firewallUserName|VT_BSTR|ファイアウォールのユーザー名を指定します。|なし|なし|  
|firewallPassword|VT_BSTR|ファイアウォールのパスワードを指定します。|なし|なし|  
|pollingUnitOfMeasure|VT_BSTR|PollingInterval プロパティの単位の種類を指定します。|有効な値は、<br /><br /> 秒数<br />-分<br />-時間<br />日|既定値は、秒です。|  
|PollingInterval|VT_BSTR|この場所のポーリング間隔の値を指定します。|なし|ポーリングが継続的に、この値を 0 に設定します。<br /><br /> 既定値は 60 です。|  
|redownloadInterval|VT_BSTR|過ぎた後 FTP アダプターがファイルを再度ダウンロード秒単位で間隔を指定します。|このプロパティは、deleteAfterDownload と enableTimeComparison プロパティの両方が [いいえ] に設定されている場合にのみ適用できます。|値-1 は、アダプターがファイルをもう一度ダウンロードしてしないことを示します。<br /><br /> 既定値は-1 です。|  
|ssoAffiliateApplication|VT_BSTR|シングル サインオン (SSO) 関連アプリケーションを指定します。|なし|なし|  
|ErrorThreshold|VT_BSTR|BizTalk Server が発生する可能性があるエラーの数を指定の場所が無効になります。|なし|既定値は 10 です。|  
|MaxFileSize|VT_BSTR|ダウンロード可能なファイルの最大サイズをメガバイト単位で指定します。|なし|値 0 は、ファイル サイズの制限がないことを示します。<br /><br /> 既定値は 100 です。|  
|UseSsl|VT_BSTR|場合は、FTP アダプターが FTPS サーバーと通信するときに SSL を使用する必要があります [はい] として指定します。|有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は [いいえ]|  
|UseDataProtection|VT_BSTR|[はい] 場合指定、FTP アダプターが FTPS サーバーとの間のファイルを送受信するときに、SSL 暗号化を使用する必要があります。|UseSsl プロパティが [はい] に設定されている場合、このプロパティは無効です。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は、Yes です。|  
|ftpsConnMode|VT_BSTR|FTPS サーバーに対する SSL 接続のモードを指定します。|有効な値は、<br /><br /> 明示的<br />暗黙的です|既定値は、Explicit です。|  
|clientCertificateHash|VT_BSTR|SSL ネゴシエーションで使用する必要があるクライアント証明書の SHA1 ハッシュを指定します。|なし|このハッシュに基づいて、クライアント証明書が取得される、BizTalk ホスト インスタンスが実行されているユーザー アカウントの個人用ストア。|  
|deleteAfterDownload|VT_BSTR|場合は、アダプターは、ダウンロードが完了した後に、FTP サーバーからのファイルを削除する必要があります [はい] として指定します。|有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は、Yes です。|  
|enableTimeComparison|VT_BSTR|アダプターする必要があります、ファイルを再度ダウンロード ファイルのタイムスタンプの変更がある場合に場合に、[はい] にこれを指定します。|DeleteAfterDownload が [いいえ] に設定されている場合にのみ、このプロパティは無効です。<br /><br /> ターゲット FTP サーバーでは、この機能の MDTM コマンドをサポートする必要があります。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は [いいえ]|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>ftp://localhost:21/in/*.xml</uri><serverAddress>localhost</serverAddress><serverPort>21</serverPort><userName>domain\testuser</userName><password>******</password><fileMask>*.xml</fileMask><targetFolder>in</targetFolder><commandLogFilename>c:\temp\realftplog.txt</commandLogFilename><representationType>binary</representationType><maximumBatchSize>0</maximumBatchSize><maximumNumberOfFiles>0</maximumNumberOfFiles><passiveMode>False</passiveMode><firewallType>NoFirewall</firewallType><firewallPort>21</firewallPort><pollingUnitOfMeasure>Seconds</pollingUnitOfMeasure><pollingInterval>5</pollingInterval><errorThreshold>10</errorThreshold><maxFileSize>5000</maxFileSize><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><deleteAfterDownload>True</deleteAfterDownload><enableTimeComparison>False</enableTimeComparison></Config></AdapterConfig></CustomProps>  
```  
  
 FTP アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Uri|VT_BSTR|データを送信する場所の完全なパスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|serverAddress|VT_BSTR|DNS 名または IP アドレス、ファイアウォールのアドレスを指定します。|なし|なし|  
|serverPort|VT_BSTR|FTP サーバーのポート アドレスを指定します。|なし|既定値は、21 です。|  
|userName|VT_BSTR|FTP サーバーにログオンするユーザー名を指定します。|なし|なし|  
|password|VT_BSTR|FTP サーバーにログオンするパスワードを指定します。|バインド ファイルをエクスポートするときにこの値は常にマスクされます。 このプロパティは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
|AccountName|VT_BSTR|FTP サーバーのアカウント名を指定します。|省略可|なし|  
|targetFolder|VT_BSTR|FTP サーバー上にファイルを移動する場所を指定します。|なし|なし|  
|TargetFileName|VT_BSTR|ファイルの代替名を指定します。 既定の名前を保持すると、送信されたメッセージごとの一意のメッセージ名が保証されます。|なし|既定値は、%messageid%.xml です。|  
|commandLogFilename|VT_BSTR|ログ ファイルのコピーを保存する場所を指定します。 FTP サーバー経由でファイルを送受信するときにエラー状態を診断するのにには、ログ ファイルを使用します。|なし|なし|  
|RepresentationType|VT_BSTR|バイナリまたは ASCII に FTP がデータを送信する方法を選択します。|有効な値は、<br /><br /> -バイナリ<br />ASCII|既定値はバイナリです。|  
|BeforePut|VT_BSTR|このコマンドは、PUT、FTP サーバー上の既定値を変更するコマンドなどのファイルの前に実行する FTP コマンドを指定します。|セミコロン (;) で個別のコマンド。 **注:** ファイル PUT の前に、QUIT コマンドはサポートされていません。|[開く] コマンドは必要ありません。|  
|AfterPut|VT_BSTR|ファイル PUT の後に実行する FTP コマンドを指定します。|セミコロン (;) で個別のコマンド。|なし|  
|AllocateStorage|VT_BSTR|レガシ ホスト システムの記憶域容量を割り当てるかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は [いいえ]|  
|SpoolingFolder|VT_BSTR|FTP サーバー上の一時フォルダの場所を指定します。 これを使用するには、転送モードがバイナリの場合、転送エラーからの復旧を保証します。 転送モードが ASCII の場合は、アダプターは、アップロードを再開します。|なし|なし|  
|connectionLimit|VT_BSTR|サーバーを開くことができる FTP の同時接続の最大数を指定します。|なし|値 0 は無制限を意味します。|  
|PassiveMode|VT_BSTR|アクティブ モードまたはパッシブ モードを使用するかどうかを指定します。|有効な値は、<br /><br /> True (パッシブ モード)<br />False (アクティブ モード)|既定値は False (アクティブ モードです)。|  
|firewallType|VT_BSTR|ファイアウォールの展開の種類を選択します。|有効な値は、<br /><br /> [Socks 4]<br />Socks 5<br />-None|既定値は、None です。|  
|firewallAddress|VT_BSTR|DNS 名または IP アドレス、ファイアウォールのアドレスを指定します。|なし|なし|  
|firewallPort|VT_BSTR|ファイアウォールのポートを指定します。|有効な値は、1 から 65535 までの間は。|既定値は、21 です。|  
|firewallUserName|VT_BSTR|ファイアウォールのユーザー名を指定します。|なし|なし|  
|firewallPassword|VT_BSTR|ファイアウォールのパスワードを指定します。|バインド ファイルをエクスポートするときにこの値は常にマスクされます。 このプロパティは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
|ssoAffiliateApplication|VT_BSTR|シングル サインオン (SSO) 関連アプリケーションを指定します。|なし|なし|  
|UseSsl|VT_BSTR|場合は、FTP アダプターが FTPS サーバーと通信するときに SSL を使用する必要があります [はい] として指定します。|有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は [いいえ]|  
|UseDataProtection|VT_BSTR|[はい] 場合指定、FTP アダプターが FTPS サーバーとの間のファイルを送受信するときに、SSL 暗号化を使用する必要があります。|このプロパティは、useSsL は、[はい] に設定されている場合に有効です。<br /><br /> 有効な値は、<br /><br /> -[はい]<br />-いいえ|既定値は、Yes です。|  
|ftpsConnMode|VT_BSTR|FTPS サーバーに対する SSL 接続のモードを指定します。|有効な値は、<br /><br /> 明示的<br />暗黙的です|既定値は、Explicit です。|  
|clientCertificateHash|VT_BSTR|SSL ネゴシエーションで使用する必要があるクライアント証明書の SHA1 ハッシュを指定します。|なし|このハッシュに基づいて、クライアント証明書が取得される、BizTalk ホスト インスタンスが実行されているユーザー アカウントの個人用ストア。|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><serverAddress>TestServer</serverAddress><serverPort>21</serverPort><userName>testuser</userName><password>******</password><accountName>testuser</accountName><targetFolder>output</targetFolder><targetFileName>%MessageID%.xml</targetFileName><commandLogFilename>c:\logfile\ftpsendlog.txt</commandLogFilename><representationType>binary</representationType><beforePut>CDW dir</beforePut><afterPut>CDUP </afterPut><allocateStorage>False</allocateStorage><spoolingFolder>tempfolder</spoolingFolder><connectionLimit>0</connectionLimit><passiveMode>False</passiveMode><firewallType>Socks4</firewallType><firewallAddress>TestServer</firewallAddress><firewallPort>21</firewallPort><firewallUserName>domain\testuser</firewallUserName><firewallPassword>******</firewallPassword><useSsl>False</useSsl><useDataProtection>True</useDataProtection><ftpsConnMode>Explicit</ftpsConnMode><clientCertificateHash>‎bc 32 2c a9 22 75 6a 3f e4 f7 a9 b1 b3 3a 24 20 23 53 68 49</clientCertificateHash><uri>ftp://TestServer:21/output/%MessageID%.xml</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  使用されるすべての名前/値ペアを格納する必要があります、アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに、 \<AdapterConfig\>要素。 以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。