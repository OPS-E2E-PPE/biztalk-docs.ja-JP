---
title: シングル サインオン:イベント 11013 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 450836dc-ddeb-4423-9966-69ad173f2c87
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9a59bb13c413489f3b950409fe886c7ddc2e0d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267288"
---
# <a name="single-sign-on-event-11013"></a>シングル サインオン:イベント 11013
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                      エンタープライズ シングル サインオン                                                                                       |
| 製品バージョン |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    イベント ID     |                                                                                                11013                                                                                                 |
|  イベント ソース   |                                                                                                ENTSSO                                                                                                |
|    コンポーネント    |                                                                                                 なし                                                                                                  |
|  シンボル名  |                                                                                        SSO_WARN_NOT_APP_USER                                                                                         |
|  メッセージ テキスト   | クライアント ユーザーがアプリケーション ユーザー account.%r のメンバーではありません。<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> アプリケーション名: % 4 %r<br /><br /> アプリケーション ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは、アプリケーション ユーザー アカウントのメンバーではないです。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 状況を解決するには、アプリケーション ユーザー アカウントのメンバー、クライアント ユーザーを作成する必要があります。 この警告を今後表示しないを停止するには、監査レベルを下げることです。