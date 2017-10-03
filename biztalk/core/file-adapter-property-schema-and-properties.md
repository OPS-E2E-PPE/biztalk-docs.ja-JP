---
title: "ファイル アダプタ プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e1c6860b002b41555337a0bf7e8cb931f2c2bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-property-schema-and-properties"></a>ファイル アダプタ プロパティ スキーマおよびプロパティ
ファイル アダプタ プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**CopyMode**|xs:unsignedInt|ファイルにメッセージを書き込む際に使用するコピー モードを定義します。 有効な値は、<br /><br /> **(0) を追加します。** ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの末尾にメッセージを追加します。 ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。<br /><br /> **新しい (1) を作成します。** ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成し、そのファイルにメッセージを書き込みます。 ファイルが存在する場合は、ファイル送信ハンドラがエラーを報告し、送信ポートの通常のアダプタ再試行ロジックに従ってメッセージを処理します。 これはファイル送信ハンドラの既定のコピー モードです。<br /><br /> **(2) を上書きします。** ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの内容を上書きします。 ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。|  
|**AllowCacheOnWrite**|xs:Boolean|ファイルにメッセージを書き込む際にファイル アダプタでファイル システム キャッシュを使用するかどうかを定義します。|  
|**ReceivedFileName**|xs:string|ファイル アダプタがメッセージを読み取るファイルの完全な名前を定義します。|  
|**FileCreationTime**|xs:datetime|ファイル受信アダプタで監視されているフォルダにファイルが書き込まれた時間を定義します。|  
|**ユーザー名**|xs:string|ネットワーク共有にアクセスするために指定した代替資格情報で使用したアカウントのユーザー名を定義します。|  
|**Password**|xs:string|ネットワーク共有にアクセスするために指定した代替資格情報で使用したアカウントのパスワードを定義します。|  
  
## <a name="see-also"></a>参照  
 [ファイル アダプタを構成します。](../core/configure-the-file-adapter.md)