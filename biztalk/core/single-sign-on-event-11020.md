---
title: シングル サインオン:イベント 11020 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa6a0d72-ece6-4094-9263-dbf69bb068c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb1b87404bff9223935f17fd67e02c32de1bd2a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266357"
---
# <a name="single-sign-on-event-11020"></a>シングル サインオン:イベント 11020
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                        エンタープライズ シングル サインオン                                                                                                                                                                        |
| 製品バージョン |                                                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    イベント ID     |                                                                                                                                                                                  11020                                                                                                                                                                                  |
|  イベント ソース   |                                                                                                                                                                                 ENTSSO                                                                                                                                                                                  |
|    コンポーネント    |                                                                                                                                                                                   なし                                                                                                                                                                                   |
|  シンボル名  |                                                                                                                                                          SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                           |
|  メッセージ テキスト   | Windows パスワードの変更が発生する別の Windows アカウント changed.%r を<br /><br /> この外部システムのアダプタで構成されているマッピング conflicts.%r を許可するため、これは許可します。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> Windows アカウント 1: % 4 %r<br /><br /> Windows アカウント 2: %5 |
  
## <a name="explanation"></a>説明  
 これは、Windows パスワードの変更が、別の Windows アカウントの変更ことを示す情報メッセージです。  
  
## <a name="user-action"></a>ユーザーの操作  
 確認してくださいすぐにこの変更は、サポート技術情報および承認しました。 場合は、アクションは必要ありません。 それ以外の場合は、変更が開始されると、システム内の安全な場所があることを確認します。