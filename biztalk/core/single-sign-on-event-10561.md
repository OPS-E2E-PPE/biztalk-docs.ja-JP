---
title: 'シングル サインオン: イベント 10561 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5148633c7fffabe0ef4bb4789fe4ded58336c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270738"
---
# <a name="single-sign-on-event-10561"></a>シングル サインオン: イベント 10561
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10561|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_BACKUP_FAILED_MEDIA|  
|メッセージ テキスト|マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。%r<br /><br /> ファイル名: %1 %r<br /><br /> クライアント ユーザー: %2 %r<br /><br /> クライアント コンピューターの場合: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 FAT ファイルなどの無効なメディアを使用してバックアップしようとしました。 マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 メディアの形式を確認し、NTFS またはリムーバブル メディアであることを確認します。