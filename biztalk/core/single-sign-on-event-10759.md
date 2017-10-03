---
title: "シングル サインオン: イベント 10759 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ff42b71499df5848a55848b3dc1067adb830bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10759"></a>シングル サインオン: イベント 10759
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10759|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA|  
|メッセージ テキスト|マスター シークレットのバックアップまたは復元のために指定するファイルは、NTFS ファイル システムまたはリムーバブル メディア上に存在している必要があります。|  
  
## <a name="explanation"></a>説明  
 セキュリティで保護できるのは、NTFS ファイル システムまたはリムーバブル メディアのみです。  
  
## <a name="user-action"></a>ユーザーの操作  
 NTFS ファイル システムまたはリムーバブル メディアに切り替えて、マスター シークレットをバックアップします。