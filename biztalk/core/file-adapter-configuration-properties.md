---
title: ファイル アダプター構成プロパティ |Microsoft Docs
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
ms.openlocfilehash: 1d9319aa135e7e7dfbc6106f4103700e2822b5fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388064"
---
# <a name="file-adapter-configuration-properties"></a>ファイル アダプター構成プロパティ
次の表のファイル アダプターに設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|RemoveReceivedFileRetryCount|VT_UI4|読み取り、BizTalk Server に送信するファイルを削除するファイル アダプターが試行する回数を指定します。|有効な値は 0 ~ 100 です。|既定値は 5 です。|  
|RemoveReceivedFileMaxInterval|VT_UI4|読み取り、BizTalk Server に送信するファイルを削除する前に、ファイル アダプターが待機するミリ秒単位で初期の間隔を指定します。|有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|FileMask|VT_BSTR|ファイルのマスクを指定します。|なし|既定値は、*.xml です。|  
|BatchSizeInBytes|VT_UI4|BizTalk メッセージ ボックスに送信されたファイルのバッチの最大合計バイト数を指定します。|有効な値は、1024 ~ 104857600 です。|既定値は|  
|PollingInterval|VT_UI4|ファイル アダプターが新しいファイルの指定した場所をポーリングするミリ秒単位で間隔を指定します。|有効な値は、1000 ~ 3600000 です。|1 に設定すると、ポーリングを無効にします。|  
|BatchSize|VT_UI4|バッチ送信するメッセージの最大数を指定します。|有効な値は、1 から 256 までの間は。|既定値は、20 です。|  
|FileNetFailRetryInt|VT_UI4|ネットワーク共有上の受信場所が一時的に使用できない場合に、アクセスを再試行する時間間隔を分単位で指定します。|有効な値は 0 ~ 4294967295 です。|既定値は 5 です。|  
|RemoveReceivedFileDelay|VT_UI4|読み取り、BizTalk Server に送信するファイルを削除する前に、ファイル アダプターが待機するミリ秒単位で初期の間隔を指定します。|指定した最大再試行間隔の値になるまでには、各再試行間隔後に、この間隔が倍加されます。<br /><br /> 有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|RenameReceivedFiles|VT_BOOL|処理のために取得する前にファイルの名前を変更するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 です。|  
|FileNetFailRetryCount|VT_UI4|ネットワーク共有上の受信場所が一時的に使用できない場合に、アクセスを試行する回数を指定します。|有効な値は 0 ~ 4294967295 です。|既定値は 5 です。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
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
  
 ファイル アダプターに設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Username|VT_BSTR|ファイル アダプターのホスト インスタンスがネットワーク共有に対する必要な権限を持っていない場合に、代替資格情報を指定します。|なし|形式でユーザー名を指定\<ドメイン\>\username します。|  
|UseTempFileOnWrite|VT_BOOL|ターゲット フォルダに書き込むときに、一時ファイルを使用することを指定します。 ファイルが完了するとは、Filename プロパティに指定された値に変更が書き込みます。|CopyMode プロパティが 2 (新規作成) の値に設定されている場合、このプロパティはのみを-1 (true) に設定できます。<br /><br /> 有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|CopyMode|VT_UI4|ファイルにメッセージを書き込むときに使用するコピー モードを定義します。|有効な値は、<br /><br /> -0 (追加)<br />-1 (上書き)<br />-2 (新規作成)|既定値は 2 (新規作成です)。|  
|FileName|VT_BSTR|メッセージ ファイル送信がハンドラーを書き込むファイルの名前を指定します。|このプロパティの制限については、次を参照してください。[ファイル マスクおよびファイル名のプロパティに関する制限事項](http://msdn.microsoft.com/library/d8f5afd0-a61f-4c9b-8a57-4792e3054769)します。|既定値は、%messageid%.xml です。|  
|AllowCacheOnWrite|VT_BOOL|ファイル システム キャッシュをファイルに、メッセージを書き込むときに使用するかどうかを指定します。|有効な値は、<br /><br /> -0 (キャッシュを使用しない)<br />--1 (キャッシュを使用)|既定値は、0 (キャッシュを使用しないです)。|  
|パスワード|VT_NULL|ファイル アダプターのホスト インスタンスがネットワーク共有に対する必要な権限を持っていない場合に、Username プロパティと組み合わせて使用するパスワードを指定します。|この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
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