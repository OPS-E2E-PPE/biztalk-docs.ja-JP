---
title: ファイル アダプター構成プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- File adapters, code sample
- receive locations, adapters
- File adapters, send ports
- File adapters, receive locations
- File adapters, properties
- send ports, adapters
ms.assetid: 53f4fd17-95b9-4861-b433-772b619e90c7
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe578337d7137f3c9973ec4d57f195ead94ad908
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969872"
---
# <a name="file-adapter-configuration-properties"></a>ファイル アダプター構成プロパティ
次の表に、ファイル アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|RemoveReceivedFileRetryCount|VT_UI4|ファイル アダプターが読み取り、BizTalk Server に送信したファイルに対し、削除を再試行する回数を指定します。|有効な値は、0 ～ 100 です。|既定値は 5 です。|  
|RemoveReceivedFileMaxInterval|VT_UI4|ファイル アダプターが読み取り、BizTalk Server に送信したファイルに対し、削除を試行するまでに待機する初期間隔をミリ秒単位で指定します。|有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|FileMask|VT_BSTR|ファイルのマスクを指定します。|なし|既定値は *.xml です。|  
|BatchSizeInBytes|VT_UI4|BizTalk メッセージ ボックスに送信するファイルのバッチの最大合計バイト数を指定します。|有効な値は、1024 ~ 104857600 です。|既定値は、102400 です。|  
|PollingInterval|VT_UI4|ファイル アダプターが指定された場所をポーリングして新しいファイルを検索する間隔を、ミリ秒単位で指定します。|有効な値は、1000 ~ 3600000 です。|ポーリングを無効にするには 1 に設定します。|  
|BatchSize|VT_UI4|バッチ送信するメッセージの最大数を指定します。|有効な値は 1 ~ 256 です。|既定値は 20 です。|  
|FileNetFailRetryInt|VT_UI4|ネットワーク共有上の受信場所が一時的に使用できない場合に、アクセスを再試行する時間間隔を分単位で指定します。|有効な値は 0 ~ 4294967295 です。|既定値は 5 です。|  
|RemoveReceivedFileDelay|VT_UI4|ファイル アダプターが読み取り、BizTalk Server に送信したファイルに対し、削除を試行するまでに待機する初期間隔をミリ秒単位で指定します。|各再試行間隔の経過後、指定された再試行の最大間隔になるまで、この間隔が倍加されます。<br /><br /> 有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|RenameReceivedFiles|VT_BOOL|処理のためにファイルを取得する前にファイル名を変更するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 です。|  
|FileNetFailRetryCount|VT_UI4|ネットワーク共有上の受信場所が一時的に使用できない場合に、アクセスを試行する回数を指定します。|有効な値は 0 ~ 4294967295 です。|既定値は 5 です。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
```  
<CustomProps>  
<RemoveReceivedFileRetryCount vt="19">5</RemoveReceivedFileRetryCount>  
<RemoveReceivedFileMaxInterval vt="19">300000</RemoveReceivedFileMaxInterval>  
<FileMask vt="8">*.xml</FileMask>  
<BatchSizeInBytes vt="19">102400</BatchSizeInBytes>  
<PollingInterval vt="19">60000</PollingInterval>  
<BatchSize vt="19">20</BatchSize>  
<FileNetFailRetryInt vt="19">5</FileNetFailRetryInt>  
<RemoveReceivedFileDelay vt="19">10</RemoveReceivedFileDelay>  
<RenameReceivedFiles vt="11">0</RenameReceivedFiles>  
<FileNetFailRetryCount vt="19">5</FileNetFailRetryCount>  
</CustomProps>  
```  
  
 次の表に、ファイル アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Username|VT_BSTR|ネットワーク共有に対する必要な権限がファイル アダプターのホスト インスタンスにない場合に、代替資格情報を指定します。|なし|形式でユーザー名を指定する\<ドメイン\>\username です。|  
|UseTempFileOnWrite|VT_BOOL|ターゲット フォルダに書き込むときに一時ファイルを使用することを指定します。 ファイルの書き込みが終了すると、Filename プロパティで指定されている値に変更されます。|このプロパティは、CopyMode プロパティが値 2 (新規作成) に設定されている場合にのみ、-1 (true) に設定できます。<br /><br /> 有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|CopyMode|VT_UI4|ファイルにメッセージを書き込むときに使用するコピー モードを定義します。|有効な値は、<br /><br /> -0 (追加)<br />-1 (上書き)<br />-2 (新規作成)|既定値は 2 (新規作成) です。|  
|FileName|VT_BSTR|ファイル送信ハンドラーがメッセージを書き込む先のファイル名を指定します。|このプロパティの制限については、次を参照してください。[ファイル マスクおよびファイル名のプロパティに関する制限](http://msdn.microsoft.com/library/d8f5afd0-a61f-4c9b-8a57-4792e3054769)です。|既定値は %MessageID%.xml です。|  
|AllowCacheOnWrite|VT_BOOL|ファイルにメッセージを書き込む際にファイル システム キャッシュを使用するかどうかを指定します。|有効な値は、<br /><br /> -0 (キャッシュを使用しない)<br />--1 (キャッシュの使用)|既定値は 0 (キャッシュを使用しない) です。|  
|Password|VT_NULL|ネットワーク共有に対する必要な権限がファイル アダプターのホスト インスタンスにない場合に、Username プロパティと共に使用するパスワードを指定します。|バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|なし|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
```  
<CustomProps>  
<Username vt="8">Domainname\User</Username>  
<UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
<CopyMode vt="19">1</CopyMode>  
<FileName vt="8">%MessageID%.xml</FileName>  
<AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
<Password vt="1" />  
</CustomProps>  
```