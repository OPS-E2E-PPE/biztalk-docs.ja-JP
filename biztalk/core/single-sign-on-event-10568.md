---
title: シングル サインオン:イベント 10568 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52d5ec7ece58816afd10e44e2bf83d53a35895e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398768"
---
# <a name="single-sign-on-event-10568"></a>シングル サインオン:イベント 10568
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                  エンタープライズ シングル サインオン                                                                                                  |
| 製品バージョン |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    イベント ID     |                                                                                                            10568                                                                                                            |
|  イベント ソース   |                                                                                                           ENTSSO                                                                                                            |
|    コンポーネント    |                                                                                                             なし                                                                                                             |
|  シンボル名  |                                                                                              SSO_WARN_INVALID_APP_ADMIN_GROUP                                                                                               |
|  メッセージ テキスト   | アプリケーション管理者アカウントがアプリケーション update.%r のため無効です。<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション管理者: % 2 %r<br /><br /> 無効なアカウント: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 無効か、存在しないアプリケーション管理者アカウントを更新しようとしました。  
  
## <a name="user-action"></a>ユーザーの操作  
 アカウントの名前が正しいことを確認します。