---
title: シングル サインオン:イベント 11023 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feeb4ede-6045-46bf-9f2b-65062c583faa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 525c2bd0759aa24c191991e075276bd75233d6d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266540"
---
# <a name="single-sign-on-event-11023"></a>シングル サインオン:イベント 11023
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                 エンタープライズ シングル サインオン                                                                                                                                  |
| 製品バージョン |                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                 |
|    イベント ID     |                                                                                                                                           11023                                                                                                                                            |
|  イベント ソース   |                                                                                                                                           ENTSSO                                                                                                                                           |
|    コンポーネント    |                                                                                                                                            なし                                                                                                                                             |
|  シンボル名  |                                                                                                                             SSO_WARN_WINDOWS_PASSWORD_DELETED                                                                                                                              |
|  メッセージ テキスト   | アカウントのロックアウトを防ぐために、SSO データベースの無効な Windows パスワードを削除しました。%r<br /><br /> SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: %3 |
  
## <a name="explanation"></a>説明  
 無効な Windows パスワードを削除しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO 管理ツールを使用して、この Windows アカウントの外部資格情報を設定します。 詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。