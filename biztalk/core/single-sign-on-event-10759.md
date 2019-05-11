---
title: シングル サインオン:イベント 10759 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966cc847d442e61353ea862e908b12d7d4b4f3d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307478"
---
# <a name="single-sign-on-event-10759"></a>シングル サインオン:イベント 10759
## <a name="details"></a>詳細  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                             エンタープライズ シングル サインオン                                             |
| 製品バージョン |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    イベント ID     |                                                       10759                                                       |
|  イベント ソース   |                                                      ENTSSO                                                       |
|    コンポーネント    |                                                        なし                                                        |
|  シンボル名  |                                       ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA                                        |
|  メッセージ テキスト   | マスター シークレットのバックアップまたは復元に指定されたファイルは、NTFS ファイル システムまたはリムーバブル メディアでなければなりません。 |
  
## <a name="explanation"></a>説明  
 NTFS ファイル システムまたはリムーバブル メディアのみを保護することができます。  
  
## <a name="user-action"></a>ユーザーの操作  
 マスター シークレットをバックアップするリムーバブル メディアの NTFS ファイル システムをいずれかに切り替えます。