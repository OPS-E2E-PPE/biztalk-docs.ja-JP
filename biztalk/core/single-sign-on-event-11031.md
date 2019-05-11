---
title: シングル サインオン:イベント 11031 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b0a8f424cc0b26e26b1006d6b1aca8be0339f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379862"
---
# <a name="single-sign-on-event-11031"></a>シングル サインオン:イベント 11031
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                |
| 製品バージョン |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    イベント ID     |                                                                                                                                          11031                                                                                                                                          |
|  イベント ソース   |                                                                                                                                         ENTSSO                                                                                                                                          |
|    コンポーネント    |                                                                                                                                           なし                                                                                                                                           |
|  シンボル名  |                                                                                                                         SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING                                                                                                                          |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントのマッピングが検出されましたが、valid.%r ではないために無視されます。<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 Windows アカウントが存在して有効ですが、アプリケーション ユーザー アカウントにない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 マッピングを削除し、再作成しようとしてください。