---
title: シングル サインオン:イベント 10561 |Microsoft Docs
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
ms.openlocfilehash: ce91071578747053c1966cd208a9251d3fbe835e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398845"
---
# <a name="single-sign-on-event-10561"></a>シングル サインオン:イベント 10561
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                    エンタープライズ シングル サインオン                                                                                                    |
| 製品バージョン |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    イベント ID     |                                                                                                              10561                                                                                                              |
|  イベント ソース   |                                                                                                             ENTSSO                                                                                                              |
|    コンポーネント    |                                                                                                               なし                                                                                                               |
|  シンボル名  |                                                                                                  SSO_ERROR_BACKUP_FAILED_MEDIA                                                                                                  |
|  メッセージ テキスト   | マスタ シークレットのバックアップの指定されたファイルは、NTFS ファイル システムまたはリムーバブル media.%r にする必要があります。<br /><br /> ファイル名: %1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> クライアント コンピューターの場合: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 バックアップは、FAT ファイルなどの無効なメディアを使用しようとしました。 マスタ シークレットのバックアップの指定されたファイルは、NTFS ファイル システムまたはリムーバブル メディア上にある必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 メディア形式を確認し、NTFS であることを確認またはリムーバブルします。