---
title: 'シングル サインオン: イベント 10567 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac0bed16a9e80860b23738e175b2bdafb883283
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975931"
---
# <a name="single-sign-on-event-10567"></a>シングル サインオン: イベント 10567
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                         エンタープライズ シングル サインオン                                                                                         |
| 製品バージョン |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                         |
|    イベント ID     |                                                                                                   10567                                                                                                   |
|  イベント ソース   |                                                                                                  ENTSSO                                                                                                   |
|    コンポーネント    |                                                                                                    なし                                                                                                    |
|  シンボル名  |                                                                                      SSO_WARN_INVALID_APP_USER_GROUP                                                                                      |
|  メッセージ テキスト   | アプリケーション ユーザー アカウントがアプリケーションの更新について有効ではありません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション ユーザー: % 2 %r<br /><br /> 無効なアカウント: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 無効であるか、または存在しないアプリケーション ユーザー アカウントを更新しようとしました。  
  
## <a name="user-action"></a>ユーザーの操作  
 アカウントの名前が正しいことを確認します。