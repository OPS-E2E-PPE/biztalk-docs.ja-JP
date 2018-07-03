---
title: 'シングル サインオン: イベント 10561 |Microsoft Docs'
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
ms.openlocfilehash: 053b17fcb940383d58110378710aeb6bc8d3fbe6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992500"
---
# <a name="single-sign-on-event-10561"></a>シングル サインオン: イベント 10561
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                    エンタープライズ シングル サインオン                                                                                                    |
| 製品バージョン |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    イベント ID     |                                                                                                              10561                                                                                                              |
|  イベント ソース   |                                                                                                             ENTSSO                                                                                                              |
|    コンポーネント    |                                                                                                               なし                                                                                                               |
|  シンボル名  |                                                                                                  SSO_ERROR_BACKUP_FAILED_MEDIA                                                                                                  |
|  メッセージ テキスト   | マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。%r<br /><br /> ファイル名: %1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> クライアント コンピューターの場合: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 FAT ファイルなどの無効なメディアを使用してバックアップしようとしました。 マスター シークレットのバックアップのために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 メディアの形式を確認し、NTFS またはリムーバブル メディアであることを確認します。