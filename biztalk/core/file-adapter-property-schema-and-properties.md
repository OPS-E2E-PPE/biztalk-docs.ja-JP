---
title: ファイル アダプタ プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5671243de2ec3d3f97c8edf80d0de94a547301fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388049"
---
# <a name="file-adapter-property-schema-and-properties"></a>ファイル アダプター プロパティ スキーマおよびプロパティ
次の表には、ファイル アダプター プロパティ スキーマのプロパティが含まれています。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/file-properties  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**CopyMode**|xs:unsignedInt|ファイルにメッセージを書き込むときに使用するコピー モードを定義します。 有効な値は、<br /><br /> **(0) を追加します。** ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの末尾にメッセージを追加します。 ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。<br /><br /> **新しい (1) を作成します。** ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成し、そのファイルにメッセージを書き込みます。 ファイルが存在する場合は、ファイル送信ハンドラがエラーを報告し、送信ポートの通常のアダプタ再試行ロジックに従ってメッセージを処理します。 これはファイル送信ハンドラの既定のコピー モードです。<br /><br /> **(2) を上書きします。** ファイルが存在する場合は、ファイル送信ハンドラがファイルを開き、ファイルの内容を上書きします。 ファイルが存在しない場合は、ファイル送信ハンドラが新しいファイルを作成します。|  
|**AllowCacheOnWrite**|xs:Boolean|ファイル システム キャッシュをファイルにメッセージを書き込むときに、ファイル アダプタが使用するかどうかを定義します。|  
|**ReceivedFileName**|xs:string|ファイル アダプターがメッセージを読み取るファイルの完全名を定義します。|  
|**FileCreationTime**|xs:datetime|ファイルが書き込まれた時刻を定義ファイルによって監視されているフォルダーには、受信アダプター。|  
|**ユーザー名**|xs:string|代替資格情報を指定するときにネットワーク共有にアクセスするために使用するアカウントのユーザー名を定義します。|  
|**Password**|xs:string|代替資格情報を指定するときにネットワーク共有にアクセスするために使用するアカウントのパスワードを定義します。|  
  
## <a name="see-also"></a>参照  
 [ファイル アダプターを構成します。](../core/configure-the-file-adapter.md)