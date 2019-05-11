---
title: シングル サインオン:イベント 11017 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b28506409bb68190f7dfe07f025d19c99dc47c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267143"
---
# <a name="single-sign-on-event-11017"></a>シングル サインオン:イベント 11017
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                               エンタープライズ シングル サインオン                                                                                                                                |
| 製品バージョン |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    イベント ID     |                                                                                                                                         11017                                                                                                                                          |
|  イベント ソース   |                                                                                                                                         ENTSSO                                                                                                                                         |
|    コンポーネント    |                                                                                                                                          なし                                                                                                                                           |
|  シンボル名  |                                                                                                                           SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK                                                                                                                           |
|  メッセージ テキスト   | アプリケーションのアプリケーション ユーザー アカウントに Windows アカウントがないために、マッピングは無効です。 マッピングは deleted.%r 削除されました<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: %4 |
  
## <a name="explanation"></a>説明  
 指定された Windows アカウントがこのアプリケーションでのアプリケーション ユーザー アカウントの一部をされなかったか、それが一度に 1 つが変更または削除されました。 マッピングが削除されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 お使いのシステム パスワード同期アカウント情報を確認し、情報が有効かどうかを確認します。 次のマッピングを再作成します。 無効なマッピング情報のリスクを軽減. マッピングの作成ウィザードを使用することに注意してください。