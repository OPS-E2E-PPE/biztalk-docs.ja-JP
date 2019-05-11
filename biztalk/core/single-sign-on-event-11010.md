---
title: シングル サインオン:イベント 11010 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b2bc9357644c48a7b17acc38582d8b386dd28e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306535"
---
# <a name="single-sign-on-event-11010"></a>シングル サインオン:イベント 11010
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                エンタープライズ シングル サインオン                                                                                |
| 製品バージョン |                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    イベント ID     |                                                                                          11010                                                                                          |
|  イベント ソース   |                                                                                         ENTSSO                                                                                          |
|    コンポーネント    |                                                                                           なし                                                                                           |
|  シンボル名  |                                                                               SSO_WARN_NOT_SSO_AFF_ADMIN                                                                                |
|  メッセージ テキスト   | クライアント ユーザーは SSO 関連管理者 account.%r のメンバーではありません。<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> SSO 関連管理者: %4 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは、SSO 関連管理者アカウントのメンバーではないです。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 状況を解決するには、クライアントのユーザーに SSO 関連管理者アカウントのメンバーを作成する必要があります。 この警告を今後表示しないを停止するには、監査レベルを下げることです。