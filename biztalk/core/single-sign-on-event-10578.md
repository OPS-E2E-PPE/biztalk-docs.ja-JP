---
title: シングル サインオン:イベント 10578 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4693bc25-d4d5-4cc7-b9bd-42d3471b2b0c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcf04e49efa17d3e796905c45833a02ace81b1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398713"
---
# <a name="single-sign-on-event-10578"></a>シングル サインオン:イベント 10578
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                             エンタープライズ シングル サインオン                                                                                             |
| 製品バージョン |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                       10578                                                                                                       |
|  イベント ソース   |                                                                                                      ENTSSO                                                                                                       |
|    コンポーネント    |                                                                                                        なし                                                                                                        |
|  シンボル名  |                                                                                          SSO_INFO_CHANGED_APP_USER_GROUP                                                                                          |
|  メッセージ テキスト   | アプリケーションのユーザーを更新 account.%r<br /><br /> 新しいアプリケーション ユーザー: 1 %r<br /><br /> 古いアプリケーション ユーザー: % 2 %r<br /><br /> 追跡 ID: % 3 %r<br /><br /> クライアント ユーザー: % 4 %r<br /><br /> アプリケーション名: %5 |
  
## <a name="explanation"></a>説明  
 これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。 このメッセージは、更新されたアプリケーションのユーザー アカウントが更新されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。