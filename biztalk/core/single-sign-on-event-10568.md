---
title: 'シングル サインオン: イベント 10568 |Microsoft Docs'
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
ms.openlocfilehash: 8c94c99580b63c5dc6eede29b595435daa256115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010251"
---
# <a name="single-sign-on-event-10568"></a>シングル サインオン: イベント 10568
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                  エンタープライズ シングル サインオン                                                                                                  |
| 製品バージョン |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    イベント ID     |                                                                                                            10568                                                                                                            |
|  イベント ソース   |                                                                                                           ENTSSO                                                                                                            |
|    コンポーネント    |                                                                                                             なし                                                                                                             |
|  シンボル名  |                                                                                              SSO_WARN_INVALID_APP_ADMIN_GROUP                                                                                               |
|  メッセージ テキスト   | アプリケーション管理者アカウントがアプリケーションの更新について有効ではありません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション管理者: % 2 %r<br /><br /> 無効なアカウント: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 無効であるか、または存在しないアプリケーション管理者アカウントを更新しようとしました。  
  
## <a name="user-action"></a>ユーザーの操作  
 アカウントの名前が正しいことを確認します。